---
banner: photo-1768597795859-828bb2b19915.jpg
banner_position: 50
cssclasses:
  - cards
---
Miscellaneous notes, tool guides, and developer references.

## Children
```dataview
TABLE WITHOUT ID 
	file.link AS "Note"
FROM ""
WHERE contains(parent, this.file.link)
AND !contains(file.etags, "#BUG")
AND !contains(file.etags, "#FEAT")
AND !contains(file.etags, "#REFACT")
AND !contains(file.etags, "#CHORE")
SORT file.name ASC
```