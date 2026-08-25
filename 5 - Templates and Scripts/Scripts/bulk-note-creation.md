<%*
// 1. Abfrage der Namensliste
const input = await tp.system.prompt("Gib die Namen ein (kommagetrennt oder pro Zeile):");

if (input) {
    // 2. Input bereinigen und aufteilen
    const names = input.split(/,|\n/).map(name => name.trim()).filter(name => name.length > 0);
    const timestamp = tp.date.now("YYYYMMDDHHmm");
    const dirName = "1 - Rough Notes";
    
    // 3. Schleife für die Notizerstellung über den Obsidian Vault-Schnittstelle
    for (const name of names) {
        const fileName = `${timestamp} - ${name}`;
        
        try {
            // app.vault.create benötigt: "Pfad/Dateiname.md", "Inhalt der Datei"
            // "" am Anfang bedeutet, dass sie im Root-Verzeichnis deines Vaults erstellt wird
            await app.vault.create(`${dirName}/${fileName}.md`, "");
        } catch (error) {
            console.error(`Fehler beim Erstellen von ${fileName}:`, error);
        }
    }
    
    new Notice(`${names.length} Notizen erfolgreich im Ordner \" ${dirName}/\" erstellt!`);
} else {
    new Notice("Abgebrochen: Keine Namen eingegeben.");
}
-%>