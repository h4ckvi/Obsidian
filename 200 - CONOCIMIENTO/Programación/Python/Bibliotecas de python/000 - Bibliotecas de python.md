Volver a [[MOC - Learning python]]

```dataview
table without id categoria as "Categoría", rows.file.link as "Temario"
from "200 - CONOCIMIENTO/Programación/Python/Bibliotecas de python"
where !contains(file.name, "000 - ")
group by categoria
sort file.ctime
```