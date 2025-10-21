# Obsidian Template README

Welcome to a simple and efficient template for Obsidian! This template is designed to help you get started quickly with a structured and efficient note-taking system. Below you will find detailed instructions on how to use and customize this template.

The template is based on this [Video from Odysseas](https://www.youtube.com/watch?v=hSTy_BInQs8&list=PLCPVAsJ6prFeROROzCeEIVfWGMRq1ImT5)

---

## Installation

1. **Download the Template**: Clone or download the repository containing this template.
- [click me to download repo](https://github.com/benjaminkost/obsidian_template_en/archive/refs/heads/master.zip)
2. **Rename folder**: Rename the folder that was downloaded according to your needs
3. **Move folder**: Move the downloaded folder into your desired location on your file system
4. **Open in Obsidian**: Open the Obsidian program on your desktop and select open vault and there you navigate to the place where you moved the downloaded folder and select open
4. **Enable Core Plugins**: Activate all "Core Plugins" like "Templates" in Obsidian settings if they’re not already enabled.
5. **Enable Community Plugin**: Activate "Dataview" Plugin in the settings under section "Community Plugins"

---

## Folder Structure

```plaintext
┌— [Your Vault Name]
 ├── 1 - Rough Notes
 ├── 2 - Source Material
 ├── 3 - Tags
 ├── 4 - Indexes
 ├── 5 - Templates
 ├── 6 - Atomic Notes
```

- **Rough Notes**: For unstructured Notes can serve as Content to create Atomic Notes from
- **Source Material**: All external resources, that where created by someone else like: slides, papers, images, videos etc.
- **Tags**: Notes that serve as categories (is a best pratice - closer decribed in section 'Design Choses')
- **Indexes**: Tags that where linked by alot of Notes (is a best pratice - closer decribed in section 'Design Choses')
- **Templates**: For common structures for Notes like Definitions, Experiments etc.
- **Atomic Notes**: For Notes that contain the actual content and optimally are split in very small pieces (atomic way)

---

## Getting Started

### 1. Create a new Note

- press the button on the top left to create a new Note
- Give it a name and write something in it
- Move the Note to the "1 - Rough Notes" folder

### 2. Add some resources to your vault

- go to your file system and select some pdf document
- drag this file into the best fitting subfolder under the "2 - Source Material" folder

### 3. Use the newly added resource

- create new Note (like described in step 1. of Getting Started)
- now tip in ![[--And here the comes the name of the resource file--]]

## Dive in deeper

### Configure Your Templates

- Navigate to the `Templates` folder.
- Edit the `.md` files to customize them to your workflow.
- In Obsidian settings, link the "Templates" plugin to the `Templates` folder.

### Utilize Metadata

Add metadata to your notes using YAML front matter, for example:

```yaml
---
tags: [project, meeting]
date: 2024-12-23
status: in-progress
---
```

### Explore Integrations

Leverage plugins like Kanban and Dataview for advanced functionality:

- **Templater**: Use scripts for more complex templates.
- **Dataview**: Query your notes and create dynamic views of your data.
- **Others**: Latex Suite, Copilot, Smart Connections, Spaced Repetition, Excel, QuickAdd, Zotero Integration, Code Emitter

-> [Here you can find some interesting Videos for using additional plugins](https://www.youtube.com/watch?v=hSTy_BInQs8&list=PLCPVAsJ6prFeROROzCeEIVfWGMRq1ImT5&index=1)
---

## Customization

Feel free to customize the folder structure, templates, or metadata to suite your workflow. Here are a few ideas:

- Add more folders, such as `Work` or `Planning` or `Spaced Repetition`, based on your needs.
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



