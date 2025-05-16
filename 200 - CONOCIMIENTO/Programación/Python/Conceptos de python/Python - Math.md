---
aliases: 
tags:
  - Programación
categoria:
  - Funciones de python
subcategoria: 
nivel:
---

Ir a [[000 - Conceptos de python]] <br>
Ir a [[000 - Ejercicios prácticos con python]] <br>
Ir a [[000 - Bibliotecas de python]]

---

<!--INDICE-->
# Índice

- [[#1. Funciones “Math” built-in]]
- [[#2. El módulo “Math”]]
<!--/INDICE--> 

# 1. Funciones “Math” built-in

Python tiene un conjunto de funciones matemáticas incorporadas, incluyendo un extenso módulo matemático, que le permite realizar tareas matemáticas con números.

Las funciones `min()` y `max()` pueden utilizarse para encontrar el valor más bajo o más alto de un iterable

```python
x = min(5, 10, 25)
y = max(5, 10, 25)

print(x)
print(y)
```

	5
	25

`abs()` devuelve el valor absoluto (positivo) del número especificado

```python
x = abs(-7.25)  
  
print(x)
```

	7.25

`pow(_x_, _y_)` devuelve el valor de x a la potencia de y (xy).

```python
x = pow(4, 3)  
  
print(x)
```

	64

# 2. El módulo “Math”

Python también tiene un módulo incorporado llamado math, que amplía la lista de funciones matemáticas.

Para utilizarlo, debes importar el módulo math:

```python
import math
```

`math.sqrt()` devuelve la raíz cuadrada de un número.

```python
import math  
  
x = math.sqrt(64)  
  
print(x)
```

	8

`math.ceil()` redondea un número hacia arriba a su entero más cercano.

`math.floor()` redondea un número hacia abajo a su enero más cercano, y devuelve el resultado.

```python
import math  
  
x = math.ceil(1.4)  
y = math.floor(1.4)  
  
print(x) # returns 2  
print(y) # returns 1
```

	2
	1

`math.pi()` constant devuelve el valor de pi.

```python
import math  
  
x = math.pi  
  
print(x)
```