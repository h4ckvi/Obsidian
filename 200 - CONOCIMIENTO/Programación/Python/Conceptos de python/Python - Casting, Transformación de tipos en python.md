---
aliases:
  - Casting de tipos en python
tags:
  - Programación
categoria:
  - Fundamentos de Python
subcategoria: 
nivel:
---

Ver [[000 - Conceptos de python]]

# Conceptos generales sobre  Casting - Transformación de tipos en python

El **casting de tipos** en Python permite transformar un valor de un tipo a otro. Esto es especialmente útil cuando necesitas trabajar con datos que tienen diferentes tipos.

# Contenido

```python
print(2 + int("100"))  # Convierte la cadena "100" a entero y suma 2
print("100" + str(2))  # Convierte el número 2 a cadena y los concatena: "1002"
```

# Conversión a flotante

Podemos convertir cadenas que representan números decimales a `float`, y también redondear valores flotantes a enteros.

Conversiones a float e int

```python
print(type(float("3.1416")))  # Convierte la cadena "3.1416" a float
print(int(3.1416))  # Convierte el float 3.1416 a entero truncando la parte decimal
```

# Conversión a booleanos

En Python, algunos valores son evaluados como `True` y otros como `False`. La función `bool()` permite verificar esto.

Conversiones a booleano

```python
print(bool(3))  # True, porque cualquier número distinto de 0 es verdadero
print(bool(0))  # False, porque 0 es considerado falso
print(bool(-1))  # True, porque es un número distinto de 0

print(bool(""))  # False, una cadena vacía es falsa
print(bool(" "))  # True, una cadena con espacio no está vacía
print(bool("False"))  # True, porque la cadena no está vacía
```

# Errores al convertir

No todos los valores pueden convertirse entre tipos. Por ejemplo, intentar convertir texto que no representa un número a `int` generará un error.

Errores y redondeos

```python
# print(int("Hola mundo"))  # Generará un ValueError
print(round(2.51))  # Redondea el valor flotante al entero más cercano
```

# Resumen

El casting de tipos te permite trabajar de manera flexible con datos en Python. Sin embargo:

- Asegúrate de que el valor puede convertirse correctamente antes de usar funciones como `int()` o `float()`.
- Usa el casting para garantizar que los datos sean del tipo adecuado antes de operar con ellos.

Experimenta en el shell de Python para entender cómo funciona cada tipo de conversión. 🚀






