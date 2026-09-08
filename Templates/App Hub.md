---
banner: photo-1657056852174-4d0e8a3f61ac.jpg
parent: "[[Templates - HUB]]"
tags:
wiki:
repo:
locally:
cssclasses:
  - cards
---
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

## Issues
```dataview
TABLE WITHOUT ID 
	file.link AS "Note",
	join(filter(file.tags, (t) => contains(list("#open", "#closed", "#Open", "#Closed"), t))) AS "Status"
FROM ""
WHERE contains(parent, this.file.link)
AND (
  contains(file.etags, "#BUG") OR
  contains(file.etags, "#FEAT") OR
  contains(file.etags, "#REFACT") OR
  contains(file.etags, "#CHORE")
)
SORT file.name ASC
```
