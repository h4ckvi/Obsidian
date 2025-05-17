---
aliases: 
tags:
  - Programación
categoria:
  - Manejo de datos en Python
subcategoria: 
nivel:
---

> [!NOTE] ¿Qué es un JSON?
> - JSON es una <u>sintaxis para almacenar e intercambiar datos</u>.
> - JSON es texto, escrito con notación de objetos JavaScript.
 

Estos métodos se complementan entre sí:

- dump() → Guarda JSON en un archivo.
- dumps() → Convierte a JSON en forma de str.
- load() → Carga JSON desde un archivo.
- loads() → Carga JSON desde un str.


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

# Cargar un JSON desde un archivo y convertirlo a objeto

• **Carga** un JSON desde un archivo y lo convierte en un objeto de Python.

```python
with open("datos.json", "r") as archivo:
    data_cargada = json.load(archivo)

print(data_cargada)
```

# Convertir de JSON a Python

Si tienes una cadena JSON, puedes parsearla usando el método `json.loads().`

El resultado será un [[Python - Listas, Tuplas, Diccionarios, conjuntos#5. Diccionarios|diccionario de python]] 

```python
import json  
  
# some JSON:  
x =  '{ "name":"John", "age":30, "city":"New York"}'  
  
# parse x:  
y = json.loads(x)  
  
# the result is a Python dictionary:  
print(y["age"])
```

	30

# Convertir de Pyhton a JSON

Si tienes un objeto Python, puedes convertirlo en una cadena JSON utilizando el método json.dumps().

```python
import json  
  
# a Python object (dict):  
x = {  
  "name": "John",  
  "age": 30,  
  "city": "New York"  
}  
  
# convert into JSON:  
y = json.dumps(x)  
  
# the result is a JSON string:  
print(y)
```

	{"name": "John", "age": 30, "city": "New York"}

> [!NOTE] Puedes convertir objetos Python de los siguientes tipos, en cadenas JSON:
> 
> - dict
> - list
> - tuple
> - string
> - int
> - float
> - True
> - False
> - None

```python
# Convierte estos objetos de python en cadenas y printea los valores:

import json  
  
print(json.dumps({"name": "John", "age": 30}))  
print(json.dumps(["apple", "bananas"]))  
print(json.dumps(("apple", "bananas")))  
print(json.dumps("hello"))  
print(json.dumps(42))  
print(json.dumps(31.76))  
print(json.dumps(True))  
print(json.dumps(False))  
print(json.dumps(None))
```

	{"name": "John", "age": 30}  
	["apple", "bananas"]  
	["apple", "bananas"]  
	"hello"  
	42  
	31.76  
	true  
	false  
	null

# Tabla de equivalencias de objetos entre Python y JSON

Al convertir de Python a JSON, los objetos Python se convierten en su equivalente JSON (JavaScript):

| Python | JSON   |
|--------|--------|
| dict   | Object |
| list   | Array  |
| tuple  | Array  |
| str    | String |
| int    | Number |
| float  | Number |
| True   | true   |
| False  | false  |
| None   | null   |

```python
# Convierte un objeto Python que contiene todos los tipos de datos legales:

import json  
  
x = {  
  "name": "John",  
  "age": 30,  
  "married": True,  
  "divorced": False,  
  "children": ("Ann","Billy"),  
  "pets": None,  
  "cars": [  
    {"model": "BMW 230", "mpg": 27.5},  
    {"model": "Ford Edge", "mpg": 24.1}  
  ]  
}  
  
print(json.dumps(x))
```

	{"name": "John", "age": 30, "married": true, "divorced": false, "children": ["Ann","Billy"], "pets": null, "cars": [{"model": "BMW 230", "mpg": 27.5}, {"model": "Ford Edge", "mpg": 24.1}]}

## Formatear el resultado de un JSON para mejor legibilidad

El ejemplo anterior imprime una cadena JSON, pero no es muy fácil de leer, sin sangrías ni saltos de línea.

El método `json.dumps()` tiene parámetros para facilitar la lectura del resultado, como `indent`:

```python
import json

x = {
  "name": "John",
  "age": 30,
  "married": True,
  "divorced": False,
  "children": ("Ann","Billy"),
  "pets": None,
  "cars": [
    {"model": "BMW 230", "mpg": 27.5},
    {"model": "Ford Edge", "mpg": 24.1}
  ]
}

# use four indents to make it easier to read the result:
print(json.dumps(x, indent=4))
```

	
	{  
	    "name": "John",  
	    "age": 30,  
	    "married": true,  
	    "divorced": false,  
	    "children": [  
	        "Ann",  
	        "Billy"  
	    ],  
	    "pets": null,  
	    "cars": [  
	        {  
	            "model": "BMW 230",  
	            "mpg": 27.5  
	        },  
	        {  
	            "model": "Ford Edge",  
	            "mpg": 24.1  
	        }  
	    ]  
	}