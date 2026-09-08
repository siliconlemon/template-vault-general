---
parent: "[[README]]"
tags:
  - TopLevel
---
## Vault-wide task lookup

Centralized view of all open `#todo`, `#review`, and `#suggestion` checkboxes across the vault, used for delayed revisits and peer reviews. 
All tags are hidden from the views below for better readability, but the respective tag is required for this to work.
The tags purposefully overlap with those displayed in card views, so that another tag can appear alongside `#review` or `#closed`.
This way, leftover tasks won't get forgotten.

* **To add an item:** Add `- [ ] #todo <note>` / `- [ ] #review <note>` / `- [ ] #suggestion <note>` anywhere in any file.
* **To resolve:** Check the box - both the view and source note get updated at once.
* *Standalone tags without a checkbox are excluded.*

---
### TODO (open)
```tasks
not done
tags include #todo
group by filename
hide edit button
hide toolbar
hide tags
```

### TODO (closed)
```tasks
done
tags include #todo
group by filename
hide edit button
hide toolbar
hide tags
```

---
### Review (open)
```tasks
not done
tags include #review
group by filename
hide edit button
hide toolbar
hide tags
```

### Review (closed)
```tasks
done
tags include #review
group by filename
hide edit button
hide toolbar
hide tags
```

---
### Suggestions (open)
```tasks
not done
tags include #suggestion
group by filename
hide edit button
hide toolbar
hide tags
```

### Suggestions (closed)
```tasks
done
tags include #suggestion
group by filename
hide edit button
hide toolbar
hide tags
```

---
