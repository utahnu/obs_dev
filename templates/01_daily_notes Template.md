[*created*:: {{date:YYYY-MM-DD}}] #dailynote
# Notes Created This Day:

```dataview
TABLE created AS Created, file.folder AS Folder, file.tags AS Tags
WHERE created = this.file.day
```
***
# Outstanding Tasks:

```dataview
TASK
	FROM -"templates"
	WHERE !completed
	GROUP by file.link
```
***
# Notes:

