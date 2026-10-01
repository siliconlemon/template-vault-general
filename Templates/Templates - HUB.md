---
banner: photo-1768597795859-828bb2b19915.jpg
cssclasses:
  - cards
---
## Templates
```dataview
TABLE WITHOUT ID 
	file.link AS "Note"
FROM ""
WHERE parent AND contains(parent, this.file.link)
SORT file.name ASC
```
