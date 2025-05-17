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

- [[#1. ¿Qué son las expresiones regulares?]]
  - [[#1.1. ¿Por qué se usa r delante de una regex?]]
- [[#2. Funciones de RegEx en Python]]
  - [[#2.1. 📌 Métodos de `Match Object`: `start()`, `end()`, `group()`]]
    - [[#2.1.1. group()]]
    - [[#2.1.2. start()]]
    - [[#2.1.3. end()]]
    - [[#2.1.4. span()]]
- [[#3.  re.finditer(): Iterar sobre coincidencias]]
- [[#4.  Diferenciar entre mayúsculas y minúsculas]]
- [[#5.  Reemplazar texto con re.sub()]]
- [[#6.  Metacaracteres en Regex]]
- [[#7.  ¿Cómo usar \ (barra invertida) en regex?]]
- [[#8.  Cómo buscar dígitos con \d]]
- [[#9.  Coincidencias con caracteres alfanuméricos (\w)]]
- [[#10.  Espacios en blanco en Python (\s)]]
- [[#11.  Validación de cadenas en Python]]
- [[#12.  Validación del final de una cadena ($)]]
- [[#13.  Coincidencias con opciones (|)]]
- [[#14.  Cuantificadores en Regex]]
- [[#15.  Contando ocurrencias en Regex]]
- [[#16.  Sets y corchetes en Regex ([ ])]]
- [[#17.  Coincidencia negada ([^ ])]]
<!--/INDICE-->


# 1. ¿Qué son las expresiones regulares?

Una RegEx, o Expresión Regular, es una secuencia de caracteres que forma un patrón de búsqueda.

RegEx puede utilizarse para comprobar si una cadena contiene el patrón de búsqueda especificado.

En Python, las regex se manejan con el módulo `re`.

```python
import re  # Importamos el módulo de expresiones regulares
```


## 1.1. ¿Por qué se usa r delante de una regex?

La r** convierte la cadena en “raw string” (cadena sin procesar), evitando que Python interprete \ como caracteres de escape.

```python
# Sin r
print("\n")  # Salto de línea

# Con r
print(r"\n")  # Imprime \n literalmente
```

==Siempre usa r"" al definir regex en Python.==

# 2. Funciones de RegEx en Python


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

## 2.1. 📌 Métodos de `Match Object`: `start()`, `end()`, `group()`

Cuando usamos `re.search()` o `re.match()`, obtenemos un objeto `Match`. Este objeto nos permite obtener información detallada sobre la coincidencia encontrada.

### 2.1.1. group()
Devuelve la coincidencia exacta encontrada en la búsqueda.

```python
import re

texto = "Mi número es 4567"
patron = r"\d+"

match = re.search(patron, texto)

if match:
    print(match.group())  # "4567"
```

### 2.1.2. start()

Devuelve la posición **donde comienza** la coincidencia en la cadena.
```python
match = re.search(r"\d+", "Mi número es 4567")

if match:
    print(match.start())  # 12
```
En "Mi número es 4567", la primera coincidencia (4567) empieza en el índice 12 (contando desde 0).

### 2.1.3. end()

Devuelve la posición **donde termina** la coincidencia (justo después del último carácter coincidente).

```python
match = re.search(r"\d+", "Mi número es 4567")

if match:
    print(match.end())  # 16
```

La cadena "4567" termina en el índice 16 (excluyendo este índice).

### 2.1.4. span()

Devuelve una tupla (start, end), que indica el rango donde se encuentra la coincidencia.

```python
match = re.search(r"\d+", "Mi número es 4567")

if match:
    print(match.span())  # (12, 16)
```

El número 4567 empieza en 12 y termina en 16.





# 3. re.finditer(): Iterar sobre coincidencias

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
  
# 4. Diferenciar entre mayúsculas y minúsculas

  

Por defecto, las búsquedas en re distinguen entre mayúsculas y minúsculas. Para hacerlas insensibles a esto, usamos re.IGNORECASE o re.I.

```python
texto = "Hola Mundo, hola Python"
patron = r"hola"

coincidencias = re.findall(patron, texto, re.IGNORECASE)
print(coincidencias)  # ['Hola', 'hola']
```

# 5. ** Reemplazar texto con re.sub()**

  

Usamos re.sub() para reemplazar coincidencias en un texto.

```python
texto = "El color favorito es el color azul"
nuevo_texto = re.sub(r"color", "tono", texto)

print(nuevo_texto)  # "El tono favorito es el tono azul"
```

# 6. ** Metacaracteres en Regex**

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

# 7. ** ¿Cómo usar \ (barra invertida) en regex?**

  

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

# 8. ** Cómo buscar dígitos con \d**

  

Para encontrar números en un texto:

```python
texto = "Hay 3 gatos y 5 perros"
patron = r"\d+"  # Encuentra dígitos

print(re.findall(patron, texto))  # ['3', '5']
```

# 9. ** Coincidencias con caracteres alfanuméricos (\w)**

  

Busca letras, números y guiones bajos.

```python
texto = "Python3_rocks!"
patron = r"\w+"  # Encuentra palabras alfanuméricas

print(re.findall(patron, texto))  # ['Python3_rocks']
```

# 10. ** Espacios en blanco en Python (\s)**

  

Para encontrar espacios, tabulaciones o saltos de línea.

```python
texto = "Hola\tMundo\nPython"
patron = r"\s"

print(re.findall(patron, texto))  # ['\t', '\n']
```

# 11. ** Validación de cadenas en Python**

  

Podemos usar re.fullmatch() para validar una cadena completa.

```python
texto = "Python123"
patron = r"[A-Za-z]+\d+"  # Letras seguidas de números

print(bool(re.fullmatch(patron, texto)))  # True
```

# 12. ** Validación del final de una cadena ($)**

  

Ejemplo: comprobar si un correo termina en .com.

```python
correo = "usuario@gmail.com"
patron = r".+@.+\.com$"

print(bool(re.search(patron, correo)))  # True
```


# 13. ** Coincidencias con opciones (|)**

  

El | permite buscar varias opciones.

```python
texto = "Hola Mundo, Hello World"
patron = r"Hola|Hello"

print(re.findall(patron, texto))  # ['Hola', 'Hello']
```

# 14. ** Cuantificadores en Regex**

• * → Cero o más veces.

• + → Una o más veces.

• ? → Cero o una vez.

```python
texto = "hellooooo"
patron = r"hello+"

print(re.search(patron, texto))  # Coincide con "hellooooo"
```


# 15. ** Contando ocurrencias en Regex**

```python
texto = "python python python"
patron = r"python"

print(len(re.findall(patron, texto)))  # 3
```

# 16. ** Sets y corchetes en Regex ([ ])**

  

Para buscar caracteres específicos.

```python
texto = "gato, gato, perro"
patron = r"[gp]ato"

print(re.findall(patron, texto))  # ['gato', 'gato']
```

# 17. ** Coincidencia negada ([^ ])**

  

Busca caracteres que **no** están en el set.

```python
texto = "123 ABC xyz"
patron = r"[^A-Z]"

print(re.findall(patron, texto))  # ['1', '2', '3', ' ', 'x', 'y', 'z']
```