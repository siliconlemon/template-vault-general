---
banner: photo-1768597795859-828bb2b19915.jpg
banner_position: 50
repo:
wiki:
locally:
cssclasses:
  - cards
---
*Replace this with the project's description, key environments, and staging links.*

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

## Repos

- `[< RepoName >](< URL >) (< description >)`

## Docs

- `[< DocName >](< URL >) (< description >)`
