# Notes Created This Day:

```dataview
TABLE file.ctime as "Created"
	WHERE file.cday = this.file.day
	SORT file.ctime ASC
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

