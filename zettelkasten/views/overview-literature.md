```dataview
table file.name as "Nota", source, created
from "literature_notes"
where note-type = "literature_note"
sort created desc
```
