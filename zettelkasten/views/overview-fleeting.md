```dataview
table file.name as "Nota", created, file.path
from "fleeting_notes"
where note-type = "fleeting_note"
sort created desc
```

