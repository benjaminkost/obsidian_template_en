# Obsidian Template README

Welcome to a simple and efficient template for Obsidian! This template is designed to help you get started quickly with a structured and efficient note-taking system. Below you will find detailed instructions on how to use and customize this template.

The template is based on this [Video from Odysseas](https://www.youtube.com/watch?v=hSTy_BInQs8&list=PLCPVAsJ6prFeROROzCeEIVfWGMRq1ImT5)

---

## Installation

1. **Download the Template**: [click me to download repo](https://github.com/benjaminkost/obsidian_template_en/archive/refs/heads/master.zip)
2. **Rename folder**: Rename the folder that was downloaded according to your needs
e.g.
```plaintext
obsidian_template_en -> My Vault
```
3. **Move folder**: Move the downloaded folder into your desired location on your file system
e.g.
```plaintext
Downloads -> Documents
```
4. **Open in Obsidian**: Open the Obsidian program on your desktop and select open vault and there you navigate to the place where you moved the downloaded folder and select open
e.g. open
```plaintext
Documents/My Vault
```
5. **Core Plugins**: In Settings navigate to "Core Plugins" and disable "Templates" and enable "Unique Note creator"
6. **Enable Community Plugin**: Activate "Dataview", "Templater", "Media Extended" and "Breadcrumbs" Plugin in the settings under section "Community Plugins"

---

## Folder Structure

```plaintext
┌— [Your Vault Name]
 ├── 1 - Rough Notes
 ├── 2 - Source Material
 ├── 3 - My Tags
 ├── 4 - Indexes
 ├── 5 - Templates and Scripts
 ├── 6 - Wiki
 ├── 7 - Work
 ├── 8 - Planing 
```

- **Rough Notes**: For unstructured notes can serve as content to create notes for the `Wiki` folder
- **Source Material**: All external resources like: slides, papers, images, videos etc.
- **My Tags**: Notes that serve as overview of overarching topics/themes (is a best pratice - closer described in section 'Design Choses')
- **Indexes**: Notes like `My Tags` that where linked by a lot of notes (is a best pratice - closer described in section 'Design Choses')
- **Templates and Scripts**: 
	- *Templates*: For common structures for Notes like Definitions, Experiments etc.
	- *Scripts*: Functions that can be executed in the folder/vault to do certain actions like deleting the occurrence of a specific word in all files
- **Wiki**: For Notes that contain the actual content and optimally are split in very small pieces (atomic way)
- **Work**: Content created by yourself that is not directly a definition out of a source
- **Planing**: Scheduling and Planing

---

## Getting Started
**Hint:** If any of the following commands do not work try `Command + P` instead and look for a function that makes sense in the context

### 1. Create a new Note
- press `Command + N`
- Important: There is a timestamp and to search properly you need to name the file accordingly "TIMESTAMP - {Name of your note}"
  - This will add the name behind the `-` to the `aliases` section in the metadata so you can find it with the normal search	

### 2. Insert template
- press `Command + Q`
- Choose `Template - Atomic Notes`
- Hint: See that in the metadata `aliases` the name without the timestamp is written

### 3. Add some source material to your vault
- go to your file system and select some pdf document
- drag this file into the best fitting subfolder under the "2 - Source Material" folder

### 4. Use the newly added resource
- now tip in `![[--And here the comes the name of the resource file--]]`

### 5. Add footnote for source
- a best practice is to always cite your sources as a footnote
- Put the cursor beneath the added resource from `3.`
- Press `Command + D`
- tip in url where the pdf came from
# Dive in deeper

### Configure Your Templates

- Navigate to the `Templates` folder.
- Edit the `.md` files to customize them to your workflow.
### Use existing plugins
- **[Dataview](https://blacksmithgu.github.io/obsidian-dataview/)**: Is used to query notes with specific metadata or name
- **[Templater](https://silentvoid13.github.io/Templater/introduction.html)**: Add complex templates to notes or execute scripts
- **[Breadcrumbs](https://publish.obsidian.md/breadcrumbs-docs/Home)**: Is used to create hierarchical structure with metadata tags like: `up`, `down`, `parent` etc.
- **[Media Extended](https://community.obsidian.md/plugins/media-extended)**: Manage material like videos or pdfs to make timestamps or give them metadata 

### Explore more plugins

Leverage plugins for advanced functionality:

- **Recommanded**: Latex Suite, Copilot, Excel, QuickAdd, Spaced Repetition, Zotero Integration, Code Emitter
### Structure Notes
To a structure of types of relation between notes, there needs to be different metadata fields, because just having a backlink will not tell you if the topic is the subtop or a overarching topic or something else.
For that we use Breadcrumbs metadata fields:

| **Group / Relation Type**      | **Field**     | **Definition & Use Case**                                                                                                      |
| ------------------------------ | ------------- | ------------------------------------------------------------------------------------------------------------------------------ |
| **Hierarchical (Ontological)** | `up`          | Defines the physical or structural container (e.g., the index note, MOC, or overarching folder/unit note).                     |
|                                | `down`        | Points to internal subdivisions, specific sections, or child indices directly contained within the current note.               |
| **Sequential (Horizontal)**    | `prev`        | Links to the directly preceding note in an ordered sequence, chapter flow, lecture list, or timeline.                          |
|                                | `next`        | Links to the directly succeeding note in an ordered sequence, tutorial step, or timeline.                                      |
| **Peer / Associative**         | `same`        | Connects non-sequential notes sharing the same hierarchical level or parent topic (e.g., related algorithms or peer concepts). |
| **Dependency / Prerequisite**  | `requires`    | Identifies prerequisite notes, concepts, or modules that must be learned or completed before understanding the current note.   |
|                                | `required_by` | Identifies notes, advanced topics, or courses that depend on the mastery or completion of the current note.                    |

### Utilize Metadata

Add metadata to your notes using YAML front matter, for example:

```yaml
---
grade: 1.3
status: in-progress
---
```

---

## Customization

Feel free to customize the folder structure, templates, or metadata to suit your workflow. Here are a few ideas:

- Add more folders, such as `Work` or `Planning`, based on your needs.
- Create additional templates for recurring note types.
- Adjust metadata fields to better align with your projects.

---
## Design Choses
- New Notes (connected with Links) for tags focusing on content
   -> These Notes can later be used as an index (or a [MoC](https://forum.obsidian.md/t/what-is-a-moc/58423/11)) to structure your Notes  
- The actual [Tags from Obsidian](https://help.obsidian.md/Editing+and+formatting/Tags) are used for [status, types (book, paper, website, etc.)](https://forum.obsidian.md/t/a-guide-on-links-vs-tags-in-obsidian/28231/4?u=benboomer) [here is a video about it](https://www.youtube.com/watch?v=fwO8LzH9q3I)

---

## Support

If you encounter any issues or have suggestions for improvement, feel free to open an issue or contribute to the repository.

---

Thank you for using my obsidian template! I hope it helps streamline your Obsidian workflow.
