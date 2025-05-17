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
  - [[#3.1. 📌 Métodos de `Match Object`: `start()`, `end()`, `group()`]]
    - [[#3.1.1. group()]]
    - [[#3.1.2. start()]]
    - [[#3.1.3. end()]]
    - [[#3.1.4. span()]]
- [[#4. re.finditer(): Iterar sobre coincidencias]]
- [[#5. Diferenciar entre mayúsculas y minúsculas]]
- [[#6. Reemplazar texto con re.sub()]]
- [[#7. Metacaracteres en Regex]]
- [[#8. ¿Cómo usar \ (barra invertida) en regex?]]
- [[#9. Cómo buscar dígitos con \d]]
- [[#10. Coincidencias con caracteres alfanuméricos (\w)]]
- [[#11. Espacios en blanco en Python (\s)]]
- [[#12. ** Validación de cadenas en Python**]]
- [[#13. Validación del final de una cadena ($)]]
- [[#14. Coincidencias con opciones (|)]]
- [[#15. Cuantificadores en Regex]]
- [[#16. Contando ocurrencias en Regex]]
- [[#17. Sets y corchetes en Regex ([ ])]]
- [[#18. Coincidencia negada ([^ ])]]
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

# Metacaracteres

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

# Flags

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

# Secuencias especiales

Una secuencia especial es un \ seguido de uno de los caracteres de la lista siguiente, y tiene un significado especial:

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

| \A  | Returns a match if the specified characters are at the beginning of the string                                                                                                                               | "\AThe"                  |     |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------ | --- |
| \b  | Returns a match where the specified characters are at the beginning or at the end of a word. (the "r" in the beginning is making sure that the string is being treated as a "raw string")                    | r\bain"<br/><br/>r"ain\b |     |
| \B  | Returns a match where the specified characters are present, but NOT at the beginning (or at the end) of a word. (the "r" in the beginning is making sure that the string is being treated as a "raw string") | r\bain"<br/><br/>r"ain\B                         |     |
| \d  | Returns a match where the string contains digits (numbers from 0-9)                                                                                                                                          | "\d"                     |     |
| \D  | Returns a match where the string DOES NOT contain digits                                                                                                                                                     | "\D"                     |     |
| \s  | Returns a match where the string contains a white space character                                                                                                                                            | "\s"                     |     |
| \S  | Returns a match where the string DOES NOT contain a white space character                                                                                                                                    | "\S"                     |     |
| \w  | Returns a match where the string contains any word characters (characters from a to Z, digits from 0-9, and the underscore _ character)                                                                      | "\w"                     |     |
| \W  | Returns a match where the string DOES NOT contain any word characters                                                                                                                                        | "\W"                     |     |
| \Z  | Returns a match if the specified characters are at the end of the string                                                                                                                                     | "Spain\Z"                |     |

# Sets

Un conjunto es un conjunto de caracteres dentro de un par de corchetes [] con un significado especial:

| Set        | Description                                                                                                           |
| ---------- | --------------------------------------------------------------------------------------------------------------------- |
| [arn]      | Returns a match where one of the specified characters (a, r, or n) is present                                         |
| [a-n]      | Returns a match for any lower case character, alphabetically between a and n                                          |
| [^arn]     | Returns a match for any character EXCEPT a, r, and n                                                                  | 
| [0123]     | Returns a match where any of the specified digits (0, 1, 2, or 3) are present                                         |
| [0-9]      | Returns a match for any digit between 0 and 9                                                                         |
| [0-5][0-9] | Returns a match for any two-digit numbers from 00 and 59                                                              |
| [a-zA-Z]   | Returns a match for any character alphabetically between a and z, lower case OR upper case                            |
| [+]        | In sets, +, *, ., \|, (), $,{} has no special meaning, so [+] means: return a match for any + character in the string |



# 3.1. 📌 Métodos de `Match Object`: `start()`, `end()`, `group()`

Cuando usamos `re.search()` o `re.match()`, obtenemos un objeto `Match`. Este objeto nos permite obtener información detallada sobre la coincidencia encontrada.

### 3.1.1. group()
Devuelve la coincidencia exacta encontrada en la búsqueda.

```python
import re

texto = "Mi número es 4567"
patron = r"\d+"

match = re.search(patron, texto)

if match:
    print(match.group())  # "4567"
```

### 3.1.2. start()

Devuelve la posición **donde comienza** la coincidencia en la cadena.
```python
match = re.search(r"\d+", "Mi número es 4567")

if match:
    print(match.start())  # 12
```
En "Mi número es 4567", la primera coincidencia (4567) empieza en el índice 12 (contando desde 0).

### 3.1.3. end()

Devuelve la posición **donde termina** la coincidencia (justo después del último carácter coincidente).

```python
match = re.search(r"\d+", "Mi número es 4567")

if match:
    print(match.end())  # 16
```

La cadena "4567" termina en el índice 16 (excluyendo este índice).

### 3.1.4. span()

Devuelve una tupla (start, end), que indica el rango donde se encuentra la coincidencia.

```python
match = re.search(r"\d+", "Mi número es 4567")

if match:
    print(match.span())  # (12, 16)
```

El número 4567 empieza en 12 y termina en 16.





# 4. re.finditer(): Iterar sobre coincidencias

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
  
# 5. Diferenciar entre mayúsculas y minúsculas

  

Por defecto, las búsquedas en re distinguen entre mayúsculas y minúsculas. Para hacerlas insensibles a esto, usamos re.IGNORECASE o re.I.

```python
texto = "Hola Mundo, hola Python"
patron = r"hola"

coincidencias = re.findall(patron, texto, re.IGNORECASE)
print(coincidencias)  # ['Hola', 'hola']
```

# 6. Reemplazar texto con re.sub()

  

Usamos re.sub() para reemplazar coincidencias en un texto.

```python
texto = "El color favorito es el color azul"
nuevo_texto = re.sub(r"color", "tono", texto)

print(nuevo_texto)  # "El tono favorito es el tono azul"
```

# 7. Metacaracteres en Regex

Los metacaracteres son caracteres especiales en regex. Algunos de los más usados son:

• . → Cualquier carácter excepto nueva línea.

• ^ → Inicio de una cadena.

• $ → Fin de una cadena.

• * → Cero o más repeticiones.

• + → Una o más repeticiones.

• ? → Cero o una repetición.

• {n} → Exactamente n repeticiones.

• {n,m} → Entre n y m repeticiones.

• \ → Escapa caracteres especiales.

```python
import re
texto = "Hola 123"
patron = r"\d+"  # Coincide con números

print(re.findall(patron, texto))  # ['123']
```

# 8. ¿Cómo usar \ (barra invertida) en regex?

  

La barra invertida \ tiene dos funciones:

1. **Escapar metacaracteres**: Si queremos buscar un . en texto, usamos \. porque . es un metacarácter.

2. **Usar secuencias especiales**:

• \d → Dígitos (0-9)

• \w → Caracteres alfanuméricos

• \s → Espacios en blanco


```python
import re
texto = "El precio es $100.50"
patron = r"\$[\d\.]+"  # Busca un símbolo $ seguido de números y punto

print(re.findall(patron, texto))  # ['$100.50']
```

# 9. Cómo buscar dígitos con \d

  

Para encontrar números en un texto:

```python
texto = "Hay 3 gatos y 5 perros"
patron = r"\d+"  # Encuentra dígitos

print(re.findall(patron, texto))  # ['3', '5']
```

# 10. Coincidencias con caracteres alfanuméricos (\w)

  

Busca letras, números y guiones bajos.

```python
texto = "Python3_rocks!"
patron = r"\w+"  # Encuentra palabras alfanuméricas

print(re.findall(patron, texto))  # ['Python3_rocks']
```

# 11. Espacios en blanco en Python (\s)

  

Para encontrar espacios, tabulaciones o saltos de línea.

```python
texto = "Hola\tMundo\nPython"
patron = r"\s"

print(re.findall(patron, texto))  # ['\t', '\n']
```

# 12. Validación de cadenas en Python

  

Podemos usar re.fullmatch() para validar una cadena completa.

```python
texto = "Python123"
patron = r"[A-Za-z]+\d+"  # Letras seguidas de números

print(bool(re.fullmatch(patron, texto)))  # True
```

# 13. Validación del final de una cadena ($)

  

Ejemplo: comprobar si un correo termina en .com.

```python
correo = "usuario@gmail.com"
patron = r".+@.+\.com$"

print(bool(re.search(patron, correo)))  # True
```


# 14. Coincidencias con opciones (|)

  

El | permite buscar varias opciones.

```python
texto = "Hola Mundo, Hello World"
patron = r"Hola|Hello"

print(re.findall(patron, texto))  # ['Hola', 'Hello']
```

# 15. Cuantificadores en Regex

• * → Cero o más veces.

• + → Una o más veces.

• ? → Cero o una vez.

```python
texto = "hellooooo"
patron = r"hello+"

print(re.search(patron, texto))  # Coincide con "hellooooo"
```


# 16. Contando ocurrencias en Regex

```python
texto = "python python python"
patron = r"python"

print(len(re.findall(patron, texto)))  # 3
```

# 17. Sets y corchetes en Regex ([ ])

  

Para buscar caracteres específicos.

```python
texto = "gato, gato, perro"
patron = r"[gp]ato"

print(re.findall(patron, texto))  # ['gato', 'gato']
```

# 18. Coincidencia negada ([^ ])

  

Busca caracteres que **no** están en el set.

```python
texto = "123 ABC xyz"
patron = r"[^A-Z]"

print(re.findall(patron, texto))  # ['1', '2', '3', ' ', 'x', 'y', 'z']
```