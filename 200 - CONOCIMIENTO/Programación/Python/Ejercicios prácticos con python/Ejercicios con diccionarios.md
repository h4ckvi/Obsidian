---
nivel: principiante
---

Dado un **array de números** y un número objetivo (`goal`), necesitamos encontrar los **dos primeros números** en el array cuya suma sea igual a ese número objetivo. Si existe tal combinación, la función debe devolver los **índices** de estos dos números. Si no se encuentra ninguna combinación, debe devolver `None`.

Usaremos un **diccionario** para hacer la búsqueda de manera más eficiente.

# Ejemplo de código

Ejemplo: Encontrar la primera combinación que sume el número objetivo usando un diccionario

```python
# Función que encuentra los dos números que suman el valor objetivo usando un diccionario
def find_first_sum(nums, goal):
  seen = {}  # Diccionario para guardar el número y su índice

  for index, value in enumerate(nums):
      missing = goal - value  # Calculamos el número que falta para completar la suma
      if missing in seen:  # Si encontramos el número faltante en el diccionario
          return [seen[missing], index]  # Devolvemos los índices de la combinación
      seen[value] = index  # Guardamos el número actual a los vistos, porque no hemos encontrado la combinación

  return None  # Si no se encuentra ninguna combinación, retornamos None

# Prueba con una lista de números y un objetivo
nums = [4, 5, 6, 2]
goal = 8
result = find_first_sum(nums, goal)  # Debería devolver [2, 3]
print(result)
```

# ¿Cómo funciona la función?

1. **Entrada**: La función recibe una lista de números `nums` y un número `goal` que es el valor objetivo que buscamos alcanzar al sumar dos números de la lista.
2. **Uso del diccionario**: Usamos un diccionario `seen` para almacenar los números ya recorridos y sus índices. Cada vez que encontramos un número, calculamos el valor faltante (el que necesitamos para alcanzar el `goal`) y lo buscamos en el diccionario.
3. **Verificación de la combinación**: Si encontramos el número faltante en el diccionario, significa que la suma de ese número y el número actual es igual a `goal`, por lo que devolvemos los índices de ambos números.
4. **Retorno final**: Si no se encuentra ninguna combinación, la función retorna `None`.

# Salida esperada:

- Al ejecutar la función con la lista `nums = [4, 5, 6, 2]` y `goal = 8`, la salida será `[2, 3]`, ya que los números en las posiciones 2 y 3 suman 8 (6 + 2).

---

Conclusión

- Usar un **diccionario** mejora la eficiencia de la búsqueda, ya que nos permite buscar rápidamente el número faltante sin tener que recorrer todos los pares posibles.
- Este enfoque tiene una **complejidad temporal O(n)**, lo que lo hace mucho más rápido que la solución de fuerza bruta que utiliza bucles anidados.
- Los **diccionarios** son estructuras muy útiles para este tipo de problemas, donde necesitas buscar valores de manera rápida y eficiente.