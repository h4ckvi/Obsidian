---
aliases:
  - RegEx
tags:
  - Programación
categoria:
  - Manipulación de datos
subcategoria: 
nivel: []
---

<!--INDICE-->
# Índice

- [[#1. Índice]]
- [[#2. ¿Qué son las expresiones regulares?]]
  - [[#2.1. ¿Por qué se usa r delante de una regex?]]
- [[#3. Funciones de RegEx en Python]]
- [[#4. Metacaracteres]]
- [[#5. Flags]]
- [[#6. Secuencias especiales]]
- [[#7. Conjuntos de caracteres  (sets)]]
- [[#8. El objeto Match]]
  - [[#8.1. Coincidencia exacta encontrada]]
  - [[#8.2. Posición donde comienza la coincidencia]]
  - [[#8.3. Posición donde termina la coincidencia]]
  - [[#8.4. Rango donde se encuentra la conicidencia]]
  - [[#8.5. Devolver la cadena en la que se encuentra la coincidencia]]
- [[#9. Algunos ejemplos:]]
  - [[#9.1. Iterar sobre coincidencias]]
  - [[#9.2. Diferenciar entre mayúsculas y minúsculas]]
  - [[#9.3. Reemplazar texto]]
  - [[#9.4. Buscar dígitos]]
  - [[#9.5. Busca letras, números y guiones bajos.]]
  - [[#9.6. Espacios en blanco en Python (\s)]]
  - [[#9.7. Validación de cadenas en Python]]
  - [[#9.8. Validación del final de una cadena]]
  - [[#9.9. Coincidencias con opciones]]
  - [[#9.10. Cuantificadores en Regex]]
  - [[#9.11. Contando ocurrencias en Regex]]
  - [[#9.12. Sets y corchetes en Regex]]
  - [[#9.13. Coincidencia negada]]
<!--/INDICE-->


# 2. ¿Qué son las expresiones regulares?

Una RegEx, o Expresión Regular, es una secuencia de caracteres que forma un patrón de búsqueda.

RegEx puede utilizarse para comprobar si una cadena contiene el patrón de búsqueda especificado.

En Python, las regex se manejan con el módulo `re`.

```python
import re  # Importamos el módulo de expresiones regulares
```


## 2.1. ¿Por qué se usa r delante de una regex?

La r** convierte la cadena en “raw string” (cadena sin procesar), evitando que Python interprete \ como caracteres de escape.

```python
# Sin r
print("\n")  # Salto de línea

# Con r
print(r"\n")  # Imprime \n literalmente
```

==Siempre usa r"" al definir regex en Python.==

# 3. Funciones de RegEx en Python


| Función                | Descripción                                                                                       | 
| ---------------------- | ------------------------------------------------------------------------------------------------- |
| re.search(pat, txt)    | Busca el primer match** en cualquier parte del texto. Devuelve un objeto Match o None.          |
| re.match(pat, txt)     | Busca un match **solo al principio** del texto. Devuelve un objeto Match o None.                  |
| re.fullmatch(pat, txt) | Devuelve un Match **solo si TODO el texto coincide** con el patrón.                               |
| re.findall(pat, txt)   | Devuelve **todas las coincidencias** como una lista de strings.                                   |
| re.finditer(pat, txt)  | Igual que findall pero devuelve **un iterador** de objetos Match.                                 |
| re.sub(pat, rep, txt)  | Reemplaza todas las coincidencias del patrón con rep en el texto.                                 |
| re.split(pat, txt)     | Divide el texto usando el patrón como separador. Devuelve una lista.                              |
| re.compile(pat)        | Compila un patrón en un objeto RegEx reutilizable. Mejora el rendimiento si lo usas muchas veces. |

```python
import re

texto = "El número de teléfono es 123-456-789"
patron = r"\d{3}-\d{3}-\d{3}"

resultado = re.search(patron, texto)

if resultado:
    print("Teléfono encontrado:", resultado.group())  # 123-456-789
```

---

# 4. Metacaracteres

| **Metacarácter**                                     | **Significado breve**                                  | **Ejemplo**    | **Coincide con…**          |
| ---------------------------------------------------- | ------------------------------------------------------ | -------------- | -------------------------- |
| .                                                    | Cualquier carácter salvo salto de línea                | a.c            | abc, a7c                   |
| ^                                                    | Inicio de línea (o texto con re.M)                     | ^Hola          | Solo si empieza por “Hola” |
| $                                                    | Fin de línea (o texto con re.M)                        | fin$           | Solo si termina en “fin”   |
| *                                                    | 0 o más repeticiones                                   | ab*c           | ac, abc, abbbc             |
| +                                                    | 1 o más repeticiones                                   | ab+c           | abc, abbbc                 |
| ?                                                    | 0 o 1 repetición / cuantificador no‐codicioso (*?, +?) | colou?r        | color, colour              |
| {m,n}                                                | Entre _m_ y _n_ repeticiones                           | \d{2,4}        | 2‑4 dígitos                |
| []                                                   | **Set**: cualquiera de los caracteres dentro           | [aeiou]        | vocal minúscula            |
| `|`                                                  | OR lógico                                              | `perro         |                            |
| ()                                                   | Grupo y captura                                        | (ab)+          | “ab”, “abab”…              |
| (?P<nom>…)                                           | Grupo con nombre                                       | (?P<dia>\d{2}) | Captura “dia”              |
| \|Escapa metacaracter o introduce secuencia especial | \.                                                     | punto literal  |                            |

# 5. Flags

Puede añadir indicadores al patrón cuando utilice expresiones regulares.

| Flag          | Shorthand | Description                                                                                                        |
| ------------- | --------- | ------------------------------------------------------------------------------------------------------------------ |
| re.ASCII      | re.A      | Returns only ASCII matches                                                                                         |
| re.DEBUG      |           | Returns debug information                                                                                          |
| re.DOTALL     | re.S      | Makes the . character match all characters (including newline character)                                           |
| re.IGNORECASE | re.I      | Case-insensitive matching                                                                                          |
| re.MULTILINE  | re.M      | Returns only matches at the beginning of each line                                                                 |
| re.NOFLAG     |           | Specifies that no flag is set for this pattern                                                                     |
| re.UNICODE    | re.U      | Returns Unicode matches. This is default from Python 3. For Python 2: use this flag to return only Unicode matches |
| re.VERBOSE    | re.X      | Allows whitespaces and comments inside patterns. Makes the pattern more readable                                   |

# 6. Secuencias especiales

Una secuencia especial es un \ seguido de uno de los caracteres de la lista siguiente, y tiene un significado especial:

| **Secuencia** | **Qué hace**                         | **Ejemplo útil**               |
| ------------- | ------------------------------------ | ------------------------------ |
| \A            | Inicio **absoluto** del texto        | \Ahttps?://                    |
| \Z            | Fin **absoluto** del texto           | \.txt\Z                        |
| \b            | Límite de palabra                    | \bcat\b (palabra entera “cat”) |
| \B            | No límite de palabra                 | \Bcat\B (“concatenate”)        |
| (?=pat)       | **Look‑ahead** positivo (no consume) | \d(?=%) (dígito seguido de %)  |
| (?!pat)       | Look‑ahead negativo                  | foo(?!bar)                     |
| (?<=pat)      | **Look‑behind** positivo             | (?<=USD)\d+                    |
| (?<!pat)      | Look‑behind negativo                 | (?\<!USD)\d+                    |

# 7. Conjuntos de caracteres  (sets)

Un conjunto es un conjunto de caracteres dentro de un par de corchetes [] con un significado especial:

| **Sintaxis** | **Significado**                      | **Coincide con…**             |
| ------------ | ------------------------------------ | ----------------------------- |
| [abc]        | a **o** b **o** c                    | cualquiera de esos caracteres |
| [^abc]       | Cualquier carácter **salvo** a, b, c | exclusión                     |
| [a-z]        | Rango                                | cualquier minúscula           |
| [A-Za-z0-9_] | Múltiples rangos                     | letra o dígito o “_”          |
| \d           | **Atajo** = [0-9]                    | dígito                        |
| \D           | **Negado** = [^0-9]                  | no dígito                     |
| \w           | [A-Za-z0-9_]                         | carácter “word”               |
| \W           | [^A-Za-z0-9_]                        | no “word”                     |
| \s           | [ \t\r\n\f\v]                        | espacio en blanco             |
| \S           | [^ \t\r\n\f\v]                       | no blanco                     |


# 8. El objeto Match

Cuando usamos `re.search()` o `re.match()`, obtenemos un objeto `Match`. Un Match Object es un objeto que contiene información sobre la búsqueda y el resultado.

El objeto Match tiene propiedades y métodos utilizados para obtener información sobre la búsqueda y el resultado:

- `.span()` devuelve una tupla que contiene las posiciones inicial y final de la coincidencia.
- `.string` devuelve la cadena introducida en la función
- `.group()` devuelve la parte de la cadena en la que se ha encontrado una coincidencia.

## 8.1. Coincidencia exacta encontrada

Devuelve la coincidencia exacta encontrada en la búsqueda.

```python
import re

texto = "Mi número es 4567"
patron = r"\d+"

match = re.search(patron, texto)

if match:
    print(match.group())
```

	4567

```python
# Imprime la parte de la cadena que tiene la coincidencia
# La Regex busca cualquier palabra que empiece por "S" mayúscula:


import re  
  
txt = "The rain in Spain"  
x = re.search(r"\bS\w+", txt)  
print(x.group())
```

	Spain


## 8.2. Posición donde comienza la coincidencia

Devuelve la posición **donde comienza** la coincidencia en la cadena.

```python
match = re.search(r"\d+", "Mi número es 4567")

if match:
    print(match.start())  # 12
```

	En "Mi número es 4567", la primera coincidencia (4567) empieza en el índice 12 (contando desde 0).

## 8.3. Posición donde termina la coincidencia

Devuelve la posición **donde termina** la coincidencia (justo después del último carácter coincidente).

```python
match = re.search(r"\d+", "Mi número es 4567")

if match:
    print(match.end())  # 16
```

La cadena "4567" termina en el índice 16 (excluyendo este índice).

## 8.4. Rango donde se encuentra la conicidencia

Devuelve una tupla (start, end), que indica el rango donde se encuentra la coincidencia.

```python
match = re.search(r"\d+", "Mi número es 4567")

if match:
    print(match.span())
```

	(12, 16)

```python

# Imprime la posición (inicial y final) de la primera coincidencia.

# La expresión regular busca cualquier palabra que empiece por "S" mayúscula:

import re

#Search for an upper case "S" character in the beginning of a word, and print its position:

txt = "The rain in Spain"
x = re.search(r"\bS\w+", txt)
print(x.span())
```

	(12, 17)

## 8.5. Devolver la cadena en la que se encuentra la coincidencia

```python
# Imprime la cadena pasada a la función:

import re

txt = "La lluvia en España"
x = re.search(r"\bS\w+", txt)
print(x.string)
```

	The rain in Spain


# 9. Algunos ejemplos:

## 9.1. Iterar sobre coincidencias

Este método devuelve un iterador con todas las coincidencias en el texto.

```python
texto = "abc 123 def 456 ghi 789"
patron = r"\d+"

for match in re.finditer(patron, texto):
    print(match.group())  # Imprime 123, 456, 789
```

```python
import re

texto = "Códigos: 123, 456 y 789"
patron = r"\d+"

for match in re.finditer(patron, texto):
    print(f"Coincidencia: {match.group()}, Posición: {match.span()}")
```

	Coincidencia: 123, Posición: (9, 12)
	Coincidencia: 456, Posición: (14, 17)
	Coincidencia: 789, Posición: (20, 23)
  
## 9.2. Diferenciar entre mayúsculas y minúsculas

  

Por defecto, las búsquedas en re distinguen entre mayúsculas y minúsculas. Para hacerlas insensibles a esto, usamos re.IGNORECASE o re.I.

```python
texto = "Hola Mundo, hola Python"
patron = r"hola"

coincidencias = re.findall(patron, texto, re.IGNORECASE)
print(coincidencias)  # ['Hola', 'hola']
```

## 9.3. Reemplazar texto

Usamos re.sub() para reemplazar coincidencias en un texto.

```python
texto = "El color favorito es el color azul"
nuevo_texto = re.sub(r"color", "tono", texto)

print(nuevo_texto)  # "El tono favorito es el tono azul"
```


## 9.4. Buscar dígitos
  
Para encontrar números en un texto:

```python
texto = "Hay 3 gatos y 5 perros"
patron = r"\d+"  # Encuentra dígitos

print(re.findall(patron, texto))  # ['3', '5']
```

## 9.5. Busca letras, números y guiones bajos.

```python
texto = "Python3_rocks!"
patron = r"\w+"  # Encuentra palabras alfanuméricas

print(re.findall(patron, texto))  # ['Python3_rocks']
```

## 9.6. Espacios en blanco en Python (\s)

Para encontrar espacios, tabulaciones o saltos de línea.

```python
texto = "Hola\tMundo\nPython"
patron = r"\s"

print(re.findall(patron, texto))  # ['\t', '\n']
```

## 9.7. Validación de cadenas en Python

Podemos usar re.fullmatch() para validar una cadena completa.

```python
texto = "Python123"
patron = r"[A-Za-z]+\d+"  # Letras seguidas de números

print(bool(re.fullmatch(patron, texto)))  # True
```

## 9.8. Validación del final de una cadena

  

Ejemplo: comprobar si un correo termina en .com.

```python
correo = "usuario@gmail.com"
patron = r".+@.+\.com$"

print(bool(re.search(patron, correo)))  # True
```


## 9.9. Coincidencias con opciones

  

El | permite buscar varias opciones.

```python
texto = "Hola Mundo, Hello World"
patron = r"Hola|Hello"

print(re.findall(patron, texto))  # ['Hola', 'Hello']
```

## 9.10. Cuantificadores en Regex

• * → Cero o más veces.

• + → Una o más veces.

• ? → Cero o una vez.

```python
texto = "hellooooo"
patron = r"hello+"

print(re.search(patron, texto))  # Coincide con "hellooooo"
```


## 9.11. Contando ocurrencias en Regex

```python
texto = "python python python"
patron = r"python"

print(len(re.findall(patron, texto)))  # 3
```

## 9.12. Sets y corchetes en Regex

Para buscar caracteres específicos.

```python
texto = "gato, gato, perro"
patron = r"[gp]ato"

print(re.findall(patron, texto))  # ['gato', 'gato']
```

## 9.13. Coincidencia negada

Busca caracteres que **no** están en el set.

```python
texto = "123 ABC xyz"
patron = r"[^A-Z]"

print(re.findall(patron, texto))  # ['1', '2', '3', ' ', 'x', 'y', 'z']
```