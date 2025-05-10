---
nivel:
  - principiante
---

# Ejercicio: Los 4 fantásticos.

En el universo de los **4 Fantásticos**, la unión y el equilibrio entre los poderes es clave para enfrentar desafíos. En este ejercicio, nos centraremos en dos miembros de la alianza:

- **Reed Richards (Mr. Fantastic)**, representado por la letra `R`.
- **Johnny Storm (La Antorcha Humana)**, representado por la letra `J`.

El objetivo es crear una función en Python que reciba una cadena de texto y cuente cuántas veces aparece la letra `R` (para Reed Richards) y cuántas veces aparece la letra `J` (para Johnny Storm). La función debe tener los siguientes comportamientos:

1. Si la cantidad de `R` y la cantidad de `J` son iguales, la alianza está en equilibrio y la función debe retornar `True`.
2. Si las cantidades no son iguales, la función debe retornar `False`.
3. Si no aparece ninguna de las dos letras en la cadena, se considera que el equilibrio se mantiene, por lo que la función debe retornar `True`.

---

# Soluciones.

Ejemplo: Función que verifica el equilibrio entre Reed Richards y Johnny Storm

```python
# Función que verifica el equilibrio entre Reed Richards y Johnny Storm
def check_is_balanced(text):
  text = text.upper()  # Convertir el texto a mayúsculas para comparar fácilmente

  # Contar las veces que aparecen las letras 'R' y 'J'
  count_r = text.count("R")  # Reed Richards
  count_j = text.count("J")  # Johnny Storm

  # Imprimir los resultados
  print(f"count_r: {count_r} count_j: {count_j}")

  # Retornar True si las cantidades son iguales, False si no
  return count_r == count_j

# Pruebas
print(check_is_balanced("RRJJ"))
print(check_is_balanced("RRRRJJ"))
print(check_is_balanced("RRJJJJJJ"))
print(check_is_balanced("awwwaqAQAQA"))
```

## ¿Cómo funciona la función?

1. **Entrada**: La función recibe un texto y convierte todas las letras a mayúsculas con `text.upper()` para asegurar que la comparación no sea sensible al caso (mayúsculas o minúsculas).
2. **Contador**: Usamos el método `.count()` para contar cuántas veces aparece la letra `R` y la letra `J` en la cadena.
3. **Evaluación**: Si el número de veces que aparece `R` es igual al número de veces que aparece `J`, la función retorna `True`, indicando que la alianza está en equilibrio. De lo contrario, retorna `False`.
4. **Pruebas**: En el código de prueba, puedes ver cómo la función se comporta con diferentes cadenas de texto.

## Salida esperada:

- `check_is_balanced("RRJJ")` retorna `True` porque hay el mismo número de `R` y `J`.
- `check_is_balanced("RRRRJJ")` retorna `True` porque las cantidades de `R` y `J` son iguales.
- `check_is_balanced("RRJJJJJJ")` retorna `False` porque hay más `J` que `R`.
- `check_is_balanced("awwwaqAQAQA")` retorna `True` porque no hay ni `R` ni `J`, lo que implica que el equilibrio se mantiene.



