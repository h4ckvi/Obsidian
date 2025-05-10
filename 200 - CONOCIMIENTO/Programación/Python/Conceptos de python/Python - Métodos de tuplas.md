---
aliases: 
tags:
  - Programación
categoria:
  - Manipulación de datos
subcategoria: 
nivel:
---

<!--INDICE-->
# Índice

- [[#1. count()]]
- [[#2. index()]]
<!--/INDICE-->

---

Python tiene dos métodos integrados que puedes usar en tuplas.

| Method  | Description                                                                             |
|---------|-----------------------------------------------------------------------------------------|
| count() | Returns the number of times a specified value occurs in a tuple                         |
| index() | Searches the tuple for a specified value and returns the position of where it was found |

---

# 1. count()

El `count()` el método devuelve el número de veces aparece un valor especificado en la tupla.

```python
thistuple = (1, 3, 7, 8, 7, 5, 4, 6, 8, 5)  
  
x = thistuple.count(5)  
  
print(x)
```



# 2. index()

Busca la primera aparición del valor 8 y devuelve su posición:

- Encuentra el primero ocurrencia del valor especificado.

- Plantea una excepción si no se encuentra el valor.

```python
thistuple = (1, 3, 7, 8, 7, 5, 4, 6, 8, 5)  
  
x = thistuple.index(8)  
  
print(x)

[Pruébalo Tú mismo »](https://www.w3schools.com/python/trypython.asp?filename=demo_ref_tuple_index)
```