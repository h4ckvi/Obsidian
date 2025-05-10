Volver a [[MOC - Learning python]] 

```dataview
table without id categoria as "Categoría", rows.file.link as "Concepto"
from "200 - CONOCIMIENTO/Programación/Python/Conceptos de python"
where !contains(file.name, "000 - ")
sort file.ctime asc
group by categoria
```

