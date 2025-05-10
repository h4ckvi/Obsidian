---
nivel: principiante
---

# Objetivo

Dado un **array de números** y un número objetivo (`goal`), necesitamos encontrar los **dos primeros números** en el array cuya suma sea igual a ese número objetivo. Si existe tal combinación, la función debe devolver los **índices** de estos dos números. Si no se encuentra ninguna combinación, debe devolver `None`.

# Ejemplo de código

Ejemplo: Encontrar la primera combinación que sume el número objetivo sin diccionarios

```python
# Función que encuentra los dos números que suman el valor objetivo
def find_first_sum(nums, goal):
  # Recorrer todos los pares posibles de números en el array
  for i in range(len(nums)):
      for j in range(i + 1, len(nums)):
          if nums[i] + nums[j] == goal:
              return [i, j]  # Devolver los índices de la combinación

  return None  # Si no se encuentra ninguna combinación, retornamos None

# Prueba con una lista de números y un objetivo
nums = [4, 5, 6, 2]
goal = 8
result = find_first_sum(nums, goal)  # Debería devolver [2, 3]
print(result)
```

# ¿Cómo funciona la función?

1. **Entrada**: La función recibe una lista de números `nums` y un número `goal` que es el valor objetivo que buscamos alcanzar al sumar dos números de la lista.
2. **Recorrido de todos los pares posibles**: Se utilizan dos bucles anidados para recorrer todos los posibles pares de números en la lista. El primer bucle recorre cada elemento, y el segundo bucle recorre los elementos que están después del primero.
3. **Condición de suma**: En cada iteración, comprobamos si la suma de los dos números actuales es igual al `goal`. Si es así, devolvemos los índices de estos dos números.
4. **Retorno final**: Si no se encuentra ninguna combinación, la función retorna `None`.

# Salida esperada:

- Al ejecutar la función con la lista `nums = [4, 5, 6, 2]` y `goal = 8`, la salida será `[2, 3]`, ya que los números en las posiciones 2 y 3 suman 8 (6 + 2).