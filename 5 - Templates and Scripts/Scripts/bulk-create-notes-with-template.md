<%*
// 1. KONFIGURATION: Wo liegen deine Templates standardmäßig?
const templateFolder = "5 - Templates and Scripts/Template Notes";

// 2. Alle Templates im Ordner (inkl. Unterordner) finden
const templateFiles = app.vault.getMarkdownFiles()
    .filter(f => f.path.startsWith(templateFolder + "/"));

if (templateFiles.length === 0) {
    new Notice(`❌ Keine Templates in '${templateFolder}' gefunden!`);
    return;
}

// Anzeige-Namen relativ zum Templateordner (zeigt Unterordner mit an)
const displayNames = templateFiles.map(f =>
    f.path.slice(templateFolder.length + 1).replace(/\.md$/, "")
);

// 3. ERSTE ABFRAGE: Auswahl per Suggester
const templateFile = await tp.system.suggester(displayNames, templateFiles, false, "Welches Template möchtest du nutzen?");

// 4. ZWEITE ABFRAGE: Auswahl zu welchem Oberthema, die erstellten Notes zugeordnet werden sollen
const allNotes = app.vault.getMarkdownFiles();
const displayAllNotes = allNotes.map(f => f.basename);

const upTopic = await tp.system.suggester(displayAllNotes, allNotes, false, "Welchem Oberthema sollen die erstellten Notes zugeordnet werden sollen");

if (templateFile) {
    const templateName = templateFile.basename;

    // Inhalt der Vorlage auslesen
    const templateContent = await app.vault.read(templateFile);

    // 5. ZWEITE ABFRAGE: Die Namensliste für die neuen Notizen
    const input = await tp.system.prompt(`Template '${templateName}' geladen. Gib jetzt die neuen Notiz-Namen ein:`);

    if (input) {
        // Aufteilen nach Zeilenumbruch
        const cleanInput = input.replaceAll(String.fromCharCode(10), ",");
        const names = cleanInput.split(",").map(name => name.trim()).filter(name => name.length > 0);

        const timestamp = tp.date.now("YYYYMMDDHHmm");
        const currentDate = tp.date.now("DD.MM.YYYY HH:mm");

        // Trick: Wir bauen die Such-Strings aus Einzelteilen zusammen,
        // damit der Templater-Parser das schliessende Tag im Code nicht faelschlich als Block-Ende erkennt!
        const startTag = "<" + "%";
        const endTag = "%" + ">";

        const searchTitle1 = startTag + " tp.file.title " + endTag;
        const searchTitle2 = startTag + "tp.file.title" + endTag;
        const searchDate1 = startTag + ' tp.date.now("DD.MM.YYYY HH:mm") ' + endTag;
        const searchDate2 = startTag + 'tp.date.now("DD.MM.YYYY HH:mm")' + endTag;
        const searchDate3 = startTag + " tp.date.now('DD.MM.YYYY HH:mm') " + endTag;
        const searchDate4 = startTag + "tp.date.now('DD.MM.YYYY HH:mm')" + endTag;

        // 6. Schleife für die Notizerstellung
        for (const name of names) {
            const fileName = `${timestamp} - ${name}`;
            let finalContent = templateContent;

            // Text-Ersetzung mit den zerlegten Strings
            finalContent = finalContent.replaceAll(searchTitle1, fileName);
            finalContent = finalContent.replaceAll(searchTitle2, fileName);
            finalContent = finalContent.replaceAll(searchDate1, currentDate);
            finalContent = finalContent.replaceAll(searchDate2, currentDate);
            finalContent = finalContent.replaceAll(searchDate3, currentDate);
            finalContent = finalContent.replaceAll(searchDate4, currentDate);

			const aliasOfNote = upTopic.basename.split(" - ").at(-1) ?  "|"+ upTopic.basename.split(" - ").at(-1) : "";
	        const noteNameWithAlias = upTopic.basename + aliasOfNote;
            finalContent = finalContent.replaceAll("up: ", `up: \n- "[[${noteNameWithAlias}]]"`);

            try {
                await app.vault.create(`${fileName}.md`, finalContent);
            } catch (error) {
                console.error(`Fehler beim Erstellen von ${fileName}:`, error);
            }
        }

        new Notice(`${names.length} Notizen basierend auf '${templateName}' erstellt!`);
    } else {
        new Notice("Abgebrochen: Keine Namen eingegeben.");
    }
} else {
    new Notice("Abgebrochen: Kein Template ausgewählt.");
}
-%>