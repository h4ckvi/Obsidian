---
aliases: 
tags:
  - Programación
categoria:
  - Control de flujo en python
subcategoria: 
nivel:
---

Ir a [[000 - Conceptos de python]] <br>
Ir a [[000 - Ejercicios prácticos con python]] <br>
Ir a [[000 - Bibliotecas de python]]

---

`match` se utiliza para realizar diferentes acciones basadas en diferentes condiciones.

# Como usar el Match en python

En lugar de escribir muchos if…else, se puede usar `match`, que es una instrucción que selecciona uno de los muchos bloques de código a ejecutar.

```python
match expression:
case 1:
	code block
case 2:
	code block
case 3:
	code block
```

Así funciona:

1. `match` se evalúa una vez.
2. El valor se compara con los valores de cada uno de los casos
3. Si hay una coincidencia, se ejecuta el bloque de código asociado.

El siguiente ejemplo utiliza el número de día laborable para imprimir el nombre de día laborable:

```python
day = 4  
match day:  
  case 1:  
    print("Monday")  
  case 2:  
    print("Tuesday")  
  case 3:  
    print("Wednesday")  
  case 4:  
    print("Thursday")  
  case 5:  
    print("Friday")  
  case 6:  
    print("Saturday")  
  case 7:  
    print("Sunday")
```

Usa el carácter de subrayado _ como el último valor en caso de que se ejecute un bloque de código cuando no hay otras coincidencias:

```python
day = 4  
match day:  
  case 6:  
    print("Today is Saturday")  
  case 7:  
    print("Today is Sunday")  
  case _:  
    print("Looking forward to the Weekend")
```

Se puede usar el pipe `|`  como operador para los casos en los que haya más de un valor para cada caso:

```python
day = 4  
match day:  
  case 1 | 2 | 3 | 4 | 5:  
    print("Today is a weekday")  
  case 6 | 7:  
    print("I love weekends!")
```

Se pueden agregar condiciones para añadir una comprobación adicional a cada caso:

```python
month = 5  
day = 4  
match day:  
  case 1 | 2 | 3 | 4 | 5 if month == 4:  
    print("A weekday in April")  
  case 1 | 2 | 3 | 4 | 5 if month == 5:  
    print("A weekday in May")  
  case _:  
    print("No match")
```