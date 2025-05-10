---
nivel: principiante
---

En **Jurassic Park**, los dinosaurios carnívoros, como el temible **T-Rex**, depositan un número par de huevos. En este ejercicio, se nos proporciona una lista de números enteros que representan la cantidad de huevos puestos por diferentes dinosaurios en el parque.

# Objetivo

Escribe una función en Python que reciba una lista de números enteros y devuelva la suma total de los huevos que pertenecen a los dinosaurios carnívoros, es decir, la suma de todos los números pares en la lista.

## Ejemplo de código

Ejemplo: Función que suma los huevos de dinosaurios carnívoros

```python
# Función que suma los huevos de dinosaurios carnívoros (números pares)
def count_carnivore_dinosaur_eggs(egg_list) -> int:
  """
  Esta función recibe una lista de números enteros que representan la cantidad de huevos que han puesto diferentes dinosaurios en el parque jurásico y los de número par son de carnívoros. Devuelve un número con la suma de todos los huevos de carnívoros.
  """
  total_carnivore_eggs = 0

  for eggs in egg_list:
      if eggs % 2 == 0:  # Comprobamos si el número es par
          total_carnivore_eggs += eggs  # Sumamos los huevos de los dinosaurios carnívoros

  # Esta forma más corta:
  # total_carnivore_eggs = sum(filter(lambda x: x % 2 == 0, egg_list))

  return total_carnivore_eggs

# Prueba con una lista de huevos
egg_list = [3, 4, 7, 5, 8]
print(count_carnivore_dinosaur_eggs(egg_list))  # Salida esperada: 12
```

## ¿Cómo funciona la función?

1. **Entrada**: La función recibe una lista de números enteros que representan la cantidad de huevos puestos por diferentes dinosaurios en el parque.
2. **Verificación de números pares**: Se utiliza el operador de módulo `%` para verificar si un número es par. Si `eggs % 2 == 0`, significa que el número es par y corresponde a un dinosaurio carnívoro.
3. **Suma**: Si el número es par, se suma a la variable `total_carnivore_eggs`.
4. **Alternativa más corta**: Se podría usar una versión más compacta de la función utilizando `filter()` y `sum()`, como se muestra en el comentario del código.

## Salida esperada:

- Al ejecutar la función con la lista `[3, 4, 7, 5, 8]`, la salida será `12`, ya que los números pares (4 y 8) suman 12.


---
 
 Explicación:
 
 1️⃣ **Se define la función** count_carnivore_dinosaur_eggs(egg_list), pero no se ejecuta aún.

2️⃣ Se crea la lista egg_list = [3, 4, 7, 5, 8].

3️⃣ Se llama a la función con print(count_carnivore_dinosaur_eggs(egg_list)).

4️⃣ En este momento, Python ya conoce egg_list, por lo que se pasa correctamente como argumento a la función.

5️⃣ Dentro de la función, egg_list se usa en el bucle y el código se ejecuta sin problemas.