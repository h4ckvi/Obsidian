---
aliases: 
link: 
tags: 
categoria:
  - Manipulación de datos
subcategoria:
---

> [!hey] Todos los métodos de cadenas devuelven nuevos valores, no modifican el original.

Con la función `DIR` podemos ver una lista de todos los atributos válidos para el objeto que estamos pasando:

```python
cadena1 = "Hola soy Alvaro" 
cadena2 = "bienvenido crack"

print(dir(cadena1))
```

En este caso nos devuelve lo siguiente, que significa que a “cadena1” podemos pasarle todos esos atributos:

	['__add__', '__class__', '__contains__', '__delattr__', '__dir__', '__doc__', '__eq__', '__format__', '__ge__', '__getattribute__', '__getitem__', '__getnewargs__', '__getstate__', '__gt__', '__hash__', '__init__', '__init_subclass__', '__iter__', '__le__', '__len__', '__lt__', '__mod__', '__mul__', '__ne__', '__new__', '__reduce__', '__reduce_ex__', '__repr__', '__rmod__', '__rmul__', '__setattr__', '__sizeof__', '__str__', '__subclasshook__', 'capitalize', 'casefold', 'center', 'count', 'encode', 'endswith', 'expandtabs', 'find', 'format', 'format_map', 'index', 'isalnum', 'isalpha', 'isascii', 'isdecimal', 'isdigit', 'isidentifier', 'islower', 'isnumeric', 'isprintable', 'isspace', 'istitle', 'isupper', 'join', 'ljust', 'lower', 'lstrip', 'maketrans', 'partition', 'removeprefix', 'removesuffix', 'replace', 'rfind', 'rindex', 'rjust', 'rpartition', 'rsplit', 'rstrip', 'split', 'splitlines', 'startswith', 'strip', 'swapcase', 'title', 'translate', 'upper', 'zfill']  

# Cómo ejecutar métodos

## Ejecutar métodos, opción 1

```python
cadena1 = "Hola soy Alvaro" 
cadena2 = "bienvenido crack"

print(cadena1.upper()) # Opción 1
```

## Ejecutar métodos, opción 2

```python
cadena1 = "Hola soy Alvaro" 
cadena2 = "bienvenido crack"

resultado = cadena1.upper()
print(resultado) # Opción 2
```

# Ejemeplos con algunos métodos:


## replace() y split()

```python
cadena1 = "Buenas, soy, Álvaro" 
cadena2 = "bienvenido crack"

# Reemplaza un pedazo de la cadena dada por otra
# Se reemplaza el primer valor (si lo encuentra) por el segundo valor
# Si no lo encuentra, no hace nada. es CASESENSITIVE como todo python

cadena_nueva = cadena1.replace("soy", "eres")
print(cadena_nueva)

cadena_nueva = cadena1.replace("Soy", "eres")
print(cadena_nueva)

# Separar cadenas con la cadena que le pasemos
# Esto creará una lista con las separaciones que haga

cadena_separada = cadena1.split(",")
print(cadena_separada)
```


## upper(), lower(), capitalize()

```python
cadena1 = "Hola soy Alvaro" 
cadena2 = "bienvenido crack"


# Convierte a mayúsculas
print("Hola".upper())

# Convierte a minúsculas
print(cadena1.lower())

# Primera letra mayúscula
print(cadena2.capitalize())
```

## find() e index()

find → En caso de no encontrar nada devuelve `-1`.
Index → En caso de no encontrar nada nos devuelve una excepción.

```python
cadena1 = "Hola soy Alvaro" 
cadena2 = "bienvenido crack"


# Buscamos una cadena en otra cadena
busqueda_find = cadena1.find("Hola")
busqueda_find2 = cadena1.find("A")
busqueda_find3 = cadena1.index("z")
 

print(busqueda_find)
print(busqueda_find2)
print(busqueda_find3)
```

![[Pasted image 20240311193416.png|500]]

## isnumeric() e isalpha()

```python
cadena1 = "123" 
cadena2 = "bienvenido crack"

# Si es numérico, devuelve true, si no, devuelve false.
# SOLO detecta si es un número, en cuanto detecta algo más devuelve false

es_numerico = cadena1.isnumeric()
print(es_numerico)

# Si es alfanumérico devuelve true, si no, false
# SOLAMENTE detecta caracteres de la a-z, sin contar caracteres especiales, espacios, comas, etc.

es_alpha_numerico = cadena1.isalpha()
print(es_alpha_numerico)
```

## count() y len()

`len` no se puede poner como atributo de str, se debe poner como una función

```python
cadena1 = "Buenas, soy Álvaro" 
cadena2 = "bienvenido crack"

# Contamos las coincidencias de una cadena dentro de otra cadena, devuelve la cantidad de coincidencias
contar_coincidencias = cadena1.count("a")
print(contar_coincidencias)

# Contamos cuantos caracteres tiene una cadena
contar_caracteres = len(cadena1)
print(contar_caracteres)
```

## startswith() y endswith()

```python
cadena1 = "Buenas, soy Álvaro" 
cadena2 = "bienvenido crack"

# Verificamos si una cadena empieza con otra cadena dada, si es así devuelve true

empieza_con = cadena1.startswith("Bue")
print(empieza_con) # Devuelve true
empieza_con = cadena1.startswith("bue")
print(empieza_con) # Devuelve false


# Verificamos que la cadena termine con el el parámetro que le pasemos

termina_con = cadena1.endswith("ro")
print(termina_con) # Devuelve true
termina_con = cadena1.endswith("ar0")
print(termina_con) # Devuelve false
```


# 💡 Lista de métodos más usados:

| Method         | Description                                                                                   |
|----------------|-----------------------------------------------------------------------------------------------|
| capitalize()   | Converts the first character to upper case                                                    |
| casefold()     | Converts string into lower case                                                               |
| center()       | Returns a centered string                                                                     |
| count()        | Returns the number of times a specified value occurs in a string                              |
| encode()       | Returns an encoded version of the string                                                      |
| endswith()     | Returns true if the string ends with the specified value                                      |
| expandtabs()   | Sets the tab size of the string                                                               |
| find()         | Searches the string for a specified value and returns the position of where it was found      |
| format()       | Formats specified values in a string                                                          |
| format_map()   | Formats specified values in a string                                                          |
| index()        | Searches the string for a specified value and returns the position of where it was found      |
| isalnum()      | Returns True if all characters in the string are alphanumeric                                 |
| isalpha()      | Returns True if all characters in the string are in the alphabet                              |
| isascii()      | Returns True if all characters in the string are ascii characters                             |
| isdecimal()    | Returns True if all characters in the string are decimals                                     |
| isdigit()      | Returns True if all characters in the string are digits                                       |
| isidentifier() | Returns True if the string is an identifier                                                   |
| islower()      | Returns True if all characters in the string are lower case                                   |
| isnumeric()    | Returns True if all characters in the string are numeric                                      |
| isprintable()  | Returns True if all characters in the string are printable                                    |
| isspace()      | Returns True if all characters in the string are whitespaces                                  |
| istitle()      | Returns True if the string follows the rules of a title                                       |
| isupper()      | Returns True if all characters in the string are upper case                                   |
| join()         | Joins the elements of an iterable to the end of the string                                    |
| ljust()        | Returns a left justified version of the string                                                |
| lower()        | Converts a string into lower case                                                             |
| lstrip()       | Returns a left trim version of the string                                                     |
| maketrans()    | Returns a translation table to be used in translations                                        |
| partition()    | Returns a tuple where the string is parted into three parts                                   |
| replace()      | Returns a string where a specified value is replaced with a specified value                   |
| rfind()        | Searches the string for a specified value and returns the last position of where it was found |
| rindex()       | Searches the string for a specified value and returns the last position of where it was found |
| rjust()        | Returns a right justified version of the string                                               |
| rpartition()   | Returns a tuple where the string is parted into three parts                                   |
| rsplit()       | Splits the string at the specified separator, and returns a list                              |
| rstrip()       | Returns a right trim version of the string                                                    |
| split()        | Splits the string at the specified separator, and returns a list                              |
| splitlines()   | Splits the string at line breaks and returns a list                                           |
| startswith()   | Returns true if the string starts with the specified value                                    |
| strip()        | Returns a trimmed version of the string                                                       |
| swapcase()     | Swaps cases, lower case becomes upper case and vice versa                                     |
| title()        | Converts the first character of each word to upper case                                       |
| translate()    | Returns a translated string                                                                   |
| upper()        | Converts a string into upper case                                                             |
| zfill()        | Fills the string with a specified number of 0 values at the beginning                         |


Para poder ejecutar un método, debemos ponerle un punto justo después del objeto. De la siguiente forma: `DATO.METODO()`

# Formateo de cadenas en python

