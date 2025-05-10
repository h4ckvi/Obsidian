---
aliases: 
tags:
  - Programación
categoria:
  - Funciones de python
subcategoria: 
nivel:
---

# Función `filter()`:

- La función **`filter()`** se utiliza para **filtrar elementos de un iterable** (como una lista, tupla o conjunto) según una condición dada.
- Toma dos argumentos: una función (o función lambda) y un iterable.
- Devuelve un nuevo iterable que contiene solo los elementos que cumplen la condición especificada.

## Ejemplo de uso de `filter()`:

Supongamos que queremos filtrar los números pares de una lista:

**opción 1:**

```python
numeros = [1, 2, 3, 4, 5, 6, 7, 8]

# Filtrar los números pares
numeros_pares = list(filter(lambda x: x % 2 == 0, numeros))
print(numeros_pares)  # Resultado: [2, 4, 6, 8]
```

**opción 2:**

```python
numeros = [1, 2, 3, 4, 5, 6, 7, 8]

# Filtrar los números pares
numeros_pares = filter(lambda x: x % 2 == 0, numeros)
print(list(numeros_pares))
```

En este ejemplo:

- La función lambda verifica si un número es par (`x % 2 == 0`).
- `filter()` crea un nuevo iterable con los números pares de la lista original.

**Nota**: Puedes usar list comprehensions como alternativa a `filter()`, pero `filter()` es útil cuando necesitas aplicar una función más compleja para filtrar elementos.


# Función `map()`




# Función `reduce()`

