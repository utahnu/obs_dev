# obs_dev


## *This repository is the entirety of my notes vault for the Winter 2023 semester.*

# Contents of obs_dev

- Daily notes:
	- This folder contains .md files that correspond to that daily note. The daily note will contain links to the notes created that day, and will centralize all outstanding tasks. 
		- *Daily notes contain Obsidian dataview query scripts that do not execute outside of obsidian.*
- Class folders (ex. cs235)
	- These will organize the markdown files themselves. Each note will have a heading that contains the date created, and an Obsidian link to the corresponding daily note.
		- *Each file also has as tag in the heading that identifies the category of that note.*
- Templates
	- This folder contains all templates for creating new notes. In Obsidian, they contain variables that are filled out automatically for the metadata and such, but in other environments it is necessary to fill them out manually. 
		- More information in [Technical Notes].
- .obsidian
	- Contains program information for Obsidian.
- README
	- duh, you're reading me right now

## How to find notes in the repo

You should be able to find what you're looking for by navigating the directories (folders). Find the course name, and look through the notes in that folder.


***

# Technical Notes

## Metadata & Templates

Metadata for my notes, which includes the date created and tags, are added at the top of the markdown page, and are consistent with a template that is present in the templates folder. 

The daily note has a standard format, while regular notes just have a uniform heading that includes YAML data under the key "created" with the date created, and an Obsidian link to the daily note of the corresponding day.

**Each note should be created using the corresponding template for proper organization**. The YAML data is required to query specific notes reliably and across multiple platforms.

## Remote repository/version control

This vault is attached to a local repository and a github repository. The Obsidian plugin, Obsidian Git, allows for git commands from the Obsidian command palette.
I commit all changes to a single branch on my local repository, and a single remote branch.

#### Creating notes in a remote environment:

Notes created outside of Obsidian require that the templates for metadata are completed manually. This is a bit of a drag, but the heading can be inserted after the fact in Obsidian later.

The daily note similarly cannot be created automatically outside of Obsidian. (maybe I will program a script for this later.) Manually filling out the template is serviceable, but this feature is probably reserved [for now] in Obsidian.

#### Codespaces:
I also have the option of editing my notes on the web with a codespace (rocky). Metadata is handled with templates in the templates folder. 

## CSS Snippets (the theme)

The only alteration I have made to the theme of Obsidian is the colors. The colors come from the theme *primary*. The section of code that defines each color variable has been copied, altered somewhat to account for missing the rest of the code, and enabled. 
Only the colors of the theme have been transferred into the CSS snippet., No other element is changed from the default Obsidian theme.
The file `color.css` is the CSS snippet that is currently active.

## Plugins

#### from Core Plugins:
- backlinks
- command palette
- daily notes
- file recovery
- note composer
- page preview
- quick switcher
- templates
#### from Community Plugins:
- advanced tables
- auto link title
- calendar
- dataview
- excalidraw
- local images
- note refactor
- obsidian git
- timeline


