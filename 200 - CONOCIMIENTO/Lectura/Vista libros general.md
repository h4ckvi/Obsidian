---
cssclasses:
  - cards
---

⭐6 → Obra de arte
⭐5 → Muy bueno
⭐4 → Bueno
⭐3 → Mediocre

<br>

# Leídos

```dataview
TABLE without id ("![|100](" + cover +")"), file.name, rating as "Valoración personal", autor, paginas, tematica
FROM "200 - CONOCIMIENTO/Lectura/Libros"
WHERE leido = true
SORT rating desc
```


<br>

# Comprados no leídos

```dataview
TABLE without id ("![|100](" + cover +")") as portada, file.name, autor, tematica, paginas
FROM "200 - CONOCIMIENTO/Lectura/Libros"
WHERE comprado = true and (leido = false or leido = empty)
SORT tematica asc
```



<br>

# No comprados

```dataview
TABLE without id ("![|100](" + cover +")") as portada, file.name, autor, tematica, paginas, precio_kindle as "Precio Kindle", precio_fisico as "Tapa dura"
FROM "200 - CONOCIMIENTO/Lectura/Libros"
WHERE comprado = false or comprado = empty
SORT tematica asc
```