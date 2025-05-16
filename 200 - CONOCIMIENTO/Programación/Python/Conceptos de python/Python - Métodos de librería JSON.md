---
aliases: 
tags:
  - Programación
categoria:
  - Manejo de datos en Python
subcategoria: 
nivel:
---

JSON es una sintaxis para almacenar e intercambiar datos.

JSON es texto, escrito con notación de objetos JavaScript.

# **json.dump()**

json.dump() es un método de la librería estándar json de Python que **convierte un objeto de Python en JSON y lo escribe en un archivo**. Se usa cuando necesitas almacenar datos estructurados en formato JSON en un archivo.

```python
import json

json.dump(obj, fp, *, skipkeys=False, ensure_ascii=True, indent=None, separators=None, default=None, sort_keys=False)
```

**Parámetros principales:**

• obj: el objeto de Python que quieres convertir a JSON.

• fp: el archivo en el que se escribirá el JSON (debe estar abierto en modo escritura 'w' o 'a').

• indent: número de espacios para formatear el JSON (opcional).

• sort_keys: si es True, ordena las claves alfabéticamente.

• ensure_ascii: si es True, convierte todos los caracteres a ASCII (útil para evitar caracteres especiales).


**Ejemplo de uso:**

```python
import json

data = {"nombre": "Álvaro", "edad": 27, "ciudad": "Madrid"}

with open("datos.json", "w") as archivo:
    json.dump(data, archivo, indent=4)  # Guarda los datos en formato JSON con indentación
```
  

# **json.dumps()**

• Similar a json.dump(), pero en lugar de escribir en un archivo, **retorna el JSON como una cadena (str)**.

```python
json_string = json.dumps(data, indent=4)
print(json_string)
```

# Perse JSON - Convertir de JSON a Python

Si tienes una cadena JSON, puedes parsearla usando el método `json.loads().`

El resultado será un [[Python - Listas, Tuplas, Diccionarios, conjuntos#5. Diccionarios|diccionario de python]] 

• **Carga** un JSON desde un archivo y lo convierte en un objeto de Python.

```python
with open("datos.json", "r") as archivo:
    data_cargada = json.load(archivo)

print(data_cargada)
```

# **json.loads()**

• Similar a json.load(), pero en lugar de leer desde un archivo, **carga JSON desde una cadena**.
```python
json_string = '{"nombre": "Álvaro", "edad": 27, "ciudad": "Madrid"}'
data = json.loads(json_string)
print(data)
```

Estos métodos se complementan entre sí:

• dump() → Guarda JSON en un archivo.

• dumps() → Convierte a JSON en forma de str.

• load() → Carga JSON desde un archivo.

• loads() → Carga JSON desde un str.
