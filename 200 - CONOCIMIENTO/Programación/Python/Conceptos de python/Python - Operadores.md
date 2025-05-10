---
aliases: 
link: 
tags: 
categoria:
  - Fundamentos de Python
subcategoria:
---

<!--INDICE-->
# Índice

- [[#1. Índice]]
- [[#2. Operadores aritméticos python]]
- [[#3. Operadores de Asignación python]]
- [[#4. Operadores de Comparación de Python]]
  - [[#4.1. Comparación de números]]
  - [[#4.2. Comparación de cadenas]]
  - [[#4.3. Más información importante]]
- [[#5. Operadores Lógicos Python]]
  - [[#5.1. Operadores lógicos: and, or, not]]
  - [[#5.2. Tablas de verdad (para referencia):]]
- [[#6. Operadores de Identidad de Python]]
- [[#7. Operadores de Membresía de Python]]
- [[#8. Operadores Bitwise Python]]
- [[#9. Precedencia de operadores]]
<!--/INDICE-->


# 2. Operadores aritméticos python

| perator | Name           | Example |
| ------- | -------------- | ------- |
| +       | Addition       | x + y   |
| -       | Subtraction    | x - y   |
| *       | Multiplication | x * y   |
| /       | Division       | x / y   |
| %       | Modulus        | x % y   |
| **      | Exponentiation | x ** y  |
| //      | Floor division | x // y  |


```python
a = 10
b = 3

suma = a + b
resta = a - b
multiplicacion = a * b
division = a / b` # Devuelve un float
division_entera = a // b
modulo = a % b
exponenciacion = a ** b

print(suma, resta, multiplicacion, division, division_entera, modulo, exponenciacion)
```

---

# 3. Operadores de Asignación python

Los operadores de asignación se utilizan para asignar valores a las variables:

| Operator | Example       | Same As             |
| -------- | ------------- | ------------------- |
| =        | x = 5         | x = 5               |
| +=       | x += 3        | x = x + 3           |
| -=       | x -= 3        | x = x - 3           |
| *=       | x *= 3        | x = x * 3           |
| /=       | x /= 3        | x = x / 3           |
| %=       | x %= 3        | x = x % 3           |
| //=      | x //= 3       | x = x // 3          |
| **=      | x **= 3       | x = x ** 3          |
| &=       | x &= 3        | x = x & 3           |
| \|=      | x \|= 3       | x = x \| 3          |
| ^=       | x ^= 3        | x = x ^ 3           |
| >>=      | x >>= 3       | x = x >> 3          |
| <<=      | x <<= 3       | x = x << 3          |
| :=       | print(x := 3) | x = 3  <br>print(x) |

---

# 4. Operadores de Comparación de Python

Los operadores de comparación se utilizan para comparar dos valores:

| Operator | Name                     | Example | Try it                                                                                 |
| -------- | ------------------------ | ------- | -------------------------------------------------------------------------------------- |
| ==       | Equal                    | x == y  | [Try it »](https://www.w3schools.com/python/trypython.asp?filename=demo_oper_compare1) |
| !=       | Not equal                | x != y  | [Try it »](https://www.w3schools.com/python/trypython.asp?filename=demo_oper_compare2) |
| >        | Greater than             | x > y   | [Try it »](https://www.w3schools.com/python/trypython.asp?filename=demo_oper_compare4) |
| <        | Less than                | x < y   | [Try it »](https://www.w3schools.com/python/trypython.asp?filename=demo_oper_compare5) |
| >=       | Greater than or equal to | x >= y  | [Try it »](https://www.w3schools.com/python/trypython.asp?filename=demo_oper_compare6) |
| <=       | Less than or equal to    | x <= y  | [Try it »](https://www.w3schools.com/python/trypython.asp?filename=demo_oper_compare7) |


## 4.1. Comparación de números

```python
# Operadores de comparación: Devuelven un booleano (True o False)
# -----------------------------------------------------------------
# == Igual: Comprueba si dos valores son iguales.
# != No igual: Comprueba si dos valores no son iguales.
# >  Mayor que: Comprueba si el valor del lado izquierdo es mayor que el del lado derecho.
# <  Menor que: Comprueba si el valor del lado izquierdo es menor que el del lado derecho.
# >= Mayor o igual que: Comprueba si el valor del lado izquierdo es mayor o igual que el del lado derecho.
# <= Menor o igual que: Comprueba si el valor del lado izquierdo es menor o igual que el del lado derecho.
# in: Comprueba si un valor está presente en una lista o colección.

# Comparación de números
x = 5
y = 10

igual = x == y          # False
distinto = x != y       # True
mayor_que = x > y       # False
menor_que = x < y       # True
mayor_igual = x >= y    # False
menor_igual = x <= y    # True

# Comprobación con el operador "in"
nums = [2, 9, 1, 8, 5, 64]
valor1_en_lista = 7 in nums  # False
valor2_en_lista = 2 in nums  # True

# Resultados
print("Comparación de números:")
print("Igual:", igual)
print("Distinto:", distinto)
print("Mayor que:", mayor_que)
print("Menor que:", menor_que)
print("Mayor o igual que:", mayor_igual)
print("Menor o igual que:", menor_igual)

print("\nUso del operador 'in':")
print("¿7 está en la lista?", valor1_en_lista)
print("¿2 está en la lista?", valor2_en_lista)

```


## 4.2. Comparación de cadenas

Python usa los operadores relacionales (<, >, <kbd>==</kbd>, !=, <=, >=) para comparar cadenas. Estas comparaciones siguen las siguientes reglas:

- Orden Unicode: Cada carácter tiene un valor único en el estándar Unicode. Python usa este valor para comparar.

- Por ejemplo, 'a' tiene un valor Unicode de 97, mientras que 'b' tiene 98.
- Puedes verificar estos valores usando ord():

```python
print(ord('a'))  # 97
print(ord('p'))  # 112
```

```python
print("'manzana' < 'pera':", "manzana" < "pera") # True
print("'Hola' == 'hola'", "Hola" == "hola") # False
```

> [!note]- Explicación del ejemplo anterior
> Python **compara los caracteres de izquierda a derecha hasta encontrar una diferencia.**
> 
> En `"manzana" < "pera"`: Compara `'m'` con `'p'`. Como el Unicode de `'m'` (109) es menor que el de `'p'` (112), devuelve `True` sin analizar los demás caracteres.
> 
> 
> ```python
> print("'manzana' < 'pera':", "manzana" < "pera") # True
> ```
> 
> Compara carácter por carácter:  `'m'` (109) vs `'p'` (112): Como 109 < 112, el resultado es `True`.
> 
> **No compara los caracteres restantes** porque ya se determinó el resultado con el primer carácter diferente.
> 
> ```python
> print("'Hola' == 'hola'", "Hola" == "hola") # False
> ```
> 
> Las cadenas son **sensibles a mayúsculas y minúsculas**. Las letras mayúsculas tienen valores Unicode más bajos que las minúsculas:
> 
>  - `'H'` tiene un valor Unicode de 72.
>  - `'h'` tiene un valor Unicode de 104.
>  
>  Como `'H'` no es igual a `'h'`, el resultado es `False`.


## 4.3. Más información importante


> [!info]- El comparador “igual a” es **CaseSensitive**
> ```python
> contraseña_almacenada = "Alvaro"
> contraseña_escrita = "alvaro"
>
> print(contraseña_almacenada == > contraseña_escrita) #Esto da False!!
> ```

> [!info]- <kbd>==</kbd> contra `is`, y Tener Varios Nombres Para un Mismo Valor
> **<kbd>==</kbd>** se utiliza para verificar si dos objetos tienen el mismo valor. Compara los valores de los objetos y devuelve `True` si los valores son iguales, y `False` si no lo son. Es una comparación de igualdad de valores.
>  
> 	 a = [1, 2, 3] b = [1, 2, 3] print(a == b)  # True, porque los valores de a y b son los mismos
>  
> **`is`** se utiliza para verificar si dos variables se refieren al mismo objeto en memoria. Compara las identidades de los objetos y devuelve `True` si ambas variables se refieren al mismo objeto en la memoria, y `False` si no. Es una comparación de identidad de objetos.
> 
> 	a = [1, 2, 3] b = a print(a is b)  # True, porque a y b se refieren al mismo objeto en la memoria
> 
> En resumen:
> 
> - **<kbd>==</kbd>** verifica si dos objetos tienen el mismo valor.
> - **`is`** verifica si dos variables se refieren al mismo objeto en la memoria.
> 

> [!info]- Sobre las comparaciones de cadenas
> 
> 
> # **Sensibilidad a mayúsculas y minúsculas**
> 
> - Las letras mayúsculas (`A-Z`) tienen valores Unicode menores que las minúsculas (`a-z`).
> - Por eso `'A' < 'a'` devuelve `True`.
> 
> # **Longitud de las cadenas**
> 
> - Si las cadenas tienen los mismos caracteres iniciales, pero una es más corta, la más corta será menor.
> 
>     ```python
>     print("abc" < "abcd")  # True (porque "abc" se considera "menor" al terminar antes)
>     ```
>     
> 
> # **Uso de funciones para comparar cadenas sin distinción de mayúsculas y minúsculas**
> 
> - Si quieres comparar cadenas ignorando la diferencia entre mayúsculas y minúsculas, puedes usar `.lower()` o `.casefold()`:
>     
>     ```python
>     print("Hola".lower() == "hola".lower())  # True 
>     print("Hola".casefold() == "hola".casefold())  # True```
>     
> 
> # **Comparaciones más avanzadas**
> 
> - Además de los operadores relacionales, puedes usar funciones como `startswith()`, `endswith()` o `in` para comparar partes de cadenas:
>     
>     
>     ```python
>     print("manzana".startswith("man"))  # True 
>     print("pera".endswith("ra"))       # True 
>     print("a" in "manzana")            # True
>     ```

---

# 5. Operadores Lógicos Python

Los operadores lógicos se utilizan para combinar declaraciones condicionales:

| Operator | Description                                             | Example               | Try it                                                                                 |
| -------- | ------------------------------------------------------- | --------------------- | -------------------------------------------------------------------------------------- |
| and      | Returns True if both statements are true                | x < 5 and  x < 10     | [Try it »](https://www.w3schools.com/python/trypython.asp?filename=demo_oper_logical1) |
| or       | Returns True if one of the statements is true           | x < 5 or x < 4        | [Try it »](https://www.w3schools.com/python/trypython.asp?filename=demo_oper_logical2) |
| not      | Reverse the result, returns False if the result is true | not(x < 5 and x < 10) | [Try it »](https://www.w3schools.com/python/trypython.asp?filename=demo_oper_logical3) |


```python
edad = 25
ingreso_mensual = 3000

# Operador AND
if edad > 18 and ingreso_mensual > 2000:
    print("Cumple con los requisitos de edad y ingresos.")

# Operador OR
if edad > 25 or ingreso_mensual > 5000:
    print("Cumple con uno de los requisitos de edad o ingresos.")

# Operador NOT
if not (edad < 18):
    print("Es mayor de edad.")
```

## 5.1. Operadores lógicos: and, or, not
```python
print("\nOperadores lógicos:")
print("True and True:", True and True)   # True
print("True and False:", True and False)  # False
print("True or False:", True or False)    # True
print("False or False:", False or False)  # False
print("not True:", not True)             # False
print("not False:", not False)            # True
```

## 5.2. Tablas de verdad (para referencia):
```python
print("\nTablas de verdad:")
print("\nand:")
print("A     B     A and B")
print("True  True ", True and True)
print("True  False", True and False)
print("False True ", False and True)
print("False False", False and False)

print("\n or:")
print("A     B     A or B")
print("True  True ", True or True)
print("True  False", True or False)
print("False True ", False or True)
print("False False", False or False)

print("\n not:") 
print("A     not A")
print("True ", not True)
print("False", not False)
```


## Declaración de aprobación 

Las declaraciones`if` no pueden estar vacías, pero si por algunar azón queremos tener un if sin contenido, se puede poner el `pass` para evitar un error.

```python
a = 33  
b = 200  
  
if b > a:  
  pass
```

---

# 6. Operadores de Identidad de Python

Los operadores de identidad se utilizan para comparar los objetos, no si son iguales, sino si en realidad son el mismo objeto, con la misma ubicación de memoria:

| Operator | Description                                            | Example    | Try it                                                                                  |
| -------- | ------------------------------------------------------ | ---------- | --------------------------------------------------------------------------------------- |
| is       | Returns True if both variables are the same object     | x is y     | [Try it »](https://www.w3schools.com/python/trypython.asp?filename=demo_oper_identity1) |
| is not   | Returns True if both variables are not the same object | x is not y | [Try it »](https://www.w3schools.com/python/trypython.asp?filename=demo_oper_identity2) |

---

# 7. Operadores de Membresía de Python

Los operadores de membresía se utilizan para probar si una secuencia se presenta en un objeto:

| Operator | Description                                                                      | Example    | Try it                                                                                    |
| -------- | -------------------------------------------------------------------------------- | ---------- | ----------------------------------------------------------------------------------------- |
| in       | Returns True if a sequence with the specified value is present in the object     | x in y     | [Try it »](https://www.w3schools.com/python/trypython.asp?filename=demo_oper_membership1) |
| not in   | Returns True if a sequence with the specified value is not present in the object | x not in y | [Try it »](https://www.w3schools.com/python/trypython.asp?filename=demo_oper_membership2) |

---

# 8. Operadores Bitwise Python

Los operadores de bitwise se utilizan para comparar números (binarios):

| Operator | Name                 | Description                                                                                             | Example | Try it                                                                                   |
| -------- | -------------------- | ------------------------------------------------------------------------------------------------------- | ------- | ---------------------------------------------------------------------------------------- |
| &        | AND                  | Sets each bit to 1 if both bits are 1                                                                   | x & y   | [Try it »](https://www.w3schools.com/python/trypython.asp?filename=demo_oper_and)        |
| \|       | OR                   | Sets each bit to 1 if one of two bits is 1                                                              | x \| y  | [Try it »](https://www.w3schools.com/python/trypython.asp?filename=demo_oper_or)         |
| ^        | XOR                  | Sets each bit to 1 if only one of two bits is 1                                                         | x ^ y   | [Try it »](https://www.w3schools.com/python/trypython.asp?filename=demo_oper_xor)        |
| ~        | NOT                  | Inverts all the bits                                                                                    | ~x      | [Try it »](https://www.w3schools.com/python/trypython.asp?filename=demo_oper_not)        |
| <<       | Zero fill left shift | Shift left by pushing zeros in from the right and let the leftmost bits fall off                        | x << 2  | [Try it »](https://www.w3schools.com/python/trypython.asp?filename=demo_oper_left_shift) |
| >>       | Signed right shift   | Shift right by pushing copies of the leftmost bit in from the left, and let the rightmost bits fall off | x >> 2  |                                                                                          |
|          |                      |                                                                                                         |         |                                                                                          |

# 9. Precedencia de operadores

El orden de precedencia se describe en la siguiente tabla, comenzando con la precedencia más alta en la parte superior:

| Operator                                                         | Description                                           | Try it                                                                                             |
| ---------------------------------------------------------------- | ----------------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| `()`                                                             | Parentheses                                           | [Try it »](https://www.w3schools.com/python/trypython.asp?filename=demo_precedence_parentheses)    |
| `**`                                                             | Exponentiation                                        | [Try it »](https://www.w3schools.com/python/trypython.asp?filename=demo_precedence_exponent)       |
| `+x`  `-x`  `~x`                                                 | Unary plus, unary minus, and bitwise NOT              | [Try it »](https://www.w3schools.com/python/trypython.asp?filename=demo_precedence_bitwise_not)    |
| `*`  `/`  `//`  `%`                                              | Multiplication, division, floor division, and modulus | [Try it »](https://www.w3schools.com/python/trypython.asp?filename=demo_precedence_multiplication) |
| `+`  `-`                                                         | Addition and subtraction                              | [Try it »](https://www.w3schools.com/python/trypython.asp?filename=demo_precedence_subtraction)    |
| `<<`  `>>`                                                       | Bitwise left and right shifts                         | [Try it »](https://www.w3schools.com/python/trypython.asp?filename=demo_precedence_shift)          |
| `&`                                                              | Bitwise AND                                           | [Try it »](https://www.w3schools.com/python/trypython.asp?filename=demo_precedence_bitwise_and)    |
| `^`                                                              | Bitwise XOR                                           | [Try it »](https://www.w3schools.com/python/trypython.asp?filename=demo_precedence_bitwise_xor)    |
| `\|`                                                             | Bitwise OR                                            | [Try it »](https://www.w3schools.com/python/trypython.asp?filename=demo_precedence_bitwise_or)     |
| `==`  `!=`  `>`  `>=`  `<`  `<=`  `is`  `is not`  `in`  `not in` | Comparisons, identity, and membership operators       | [Try it »](https://www.w3schools.com/python/trypython.asp?filename=demo_precedence_like)           |
| `not`                                                            | Logical NOT                                           | [Try it »](https://www.w3schools.com/python/trypython.asp?filename=demo_precedence_not)            |
| `and`                                                            | AND                                                   | [Try it »](https://www.w3schools.com/python/trypython.asp?filename=demo_precedence_and)            |
| `or`                                                             | OR                                                    | [Try it »](https://www.w3schools.com/python/trypython.asp?filename=demo_precedence_or)             |