---
aliases: 
link: 
tags: 
categoria:
  - Control de flujo en python
subcategoria:
---


> [!NOTE]- Ayuda para aprender a programar: **Python tutor**
> Visualización interactiva
> 
> Si quieres ver cómo se ejecuta este código paso a paso, puedes probarlo en **Python Tutor**, una herramienta interactiva para analizar la ejecución de código en Python.
> 
> 🔗 [Visualizar código en Python Tutor](https://pythontutor.com/render.html#mode=edit)


Antes de empezar debemos saber qué es un elemento iterable.


> [!note] Elemento iterable:
> Un elemento iterable es cualquier objeto en Python que puede ser recorrido o atravesado secuencialmente. La iteración es el proceso de acceder secuencialmente a los elementos de un iterable, uno a uno. **No todos los objetos son iterables**, pero muchos tipos de datos comunes en Python, como listas, tuplas, conjuntos, diccionarios y cadenas, son iterables.

# 1. Bucle for básico

```python
animales = ["perro", "gato", "elefante", "cocodrilo"]
for animal in animales:
	print(animal)
```

El bucle for itera sobre cada elemento en el iterable y ejecuta el bloque de código para cada elemento.

## 2.1 Bucles anidados (afecta a while, for e if) 

En el siguiente ejemplo, tenemos una lista de **letras** y otra de **números**.  
Usamos un **bucle `for` dentro de otro `for`** para recorrer todas las combinaciones posibles:

fdfsdf [[Python - Métodos de tuplas]]

Ejemplo: Bucles anidados en Python

```python
# Bucles anidados para combinar listas
letras = ["A", "B", "C"]
numeros = [1, 2, 3]

for letra in letras:
  for numero in numeros:
      print(f"{letra}{numero}")
```

Este código imprimirá todas las combinaciones de `letras` con `números`:

`A1 A2 A3 B1 B2 B3 C1 C2 C3`


## Conclusión

- Los **bucles anidados** permiten recorrer múltiples listas al mismo tiempo.
- Se ejecuta **una iteración del segundo bucle por cada iteración del primero**.
- Para visualizar cómo se ejecuta, puedes usar herramientas como **Python Tutor**.


# 2. Recorrer más de una lista a la vez

Puedes usar la función `zip()` para combinar múltiples listas y luego iterar sobre ellas:

```python
lista1 = [1, 2, 3]
lista2 = ['a', 'b', 'c']
for elemento1, elemento2 in zip(lista1, lista2):
    print(elemento1, elemento2)
```

# 3. Recorrer una lista por su índice: `enumerate()`

Lo importante no es el nombre de la variable, sino el lugar que ocupa.

Cuando usamos `enumerate`, guarda el índice en la primera variable y el valor de ese índice en la segunda.

```python
lista = ['a', 'b', 'c']
for indice, valor in enumerate(lista):
    print(indice, valor)
```

# 4. Iterar una tupla

Las tuplas se pueden iterar directamente de la misma manera que las listas:

```python
tupla = (1, 2, 3)
for elemento in tupla:
    print(elemento)
```


# 5. Iterar conjuntos

Los conjuntos se pueden iterar directamente como cualquier otro iterable:

```python
conjunto = {1, 2, 3}
for elemento in conjunto:
    print(elemento)
```

# 6. Iterar diccionarios

**Iterar directamente sobre el diccionario**: Puedes usar un bucle `for` para iterar sobre las **claves** del diccionario. Esto te permite acceder a los valores correspondientes. Aquí tienes un ejemplo:
 
 
 ```python
 my_dict = {"nombre": "Juan", "edad": 30, "ciudad": "Madrid"}
 for key in my_dict:
	  print(f"Clave: {key}, Valor: {my_dict[key]}")
 ```

- `key` toma el valor `"nombre"`.
- Accedemos al valor asociado a `"nombre"` en el diccionario: `my_dict["nombre"]`, que es `"Juan"`.
- El resultado impreso es: `Clave: nombre, Valor: Juan`.

 
**Usar el método `.items()`**: El método `.items()` devuelve una vista de pares clave-valor. Puedes iterar sobre estos pares directamente. Aquí está cómo:
 
 
 ```python
 for key, value in my_dict.items():
	  print(f"Clave: {key}, Valor: {value}")
 ```
 
 
**Iterar solo sobre las claves con `.keys()`**: Si solo necesitas las claves, puedes usar `.keys()`:

 
 ```python
 for key in my_dict.keys():
	  print(f"Clave: {key}")
 ```
 
 
**Iterar solo sobre los valores con `.values()`**: Si solo te interesan los valores, usa `.values()`:
 
 
 ```python
 for value in my_dict.values():
	  print(f"Valor: {value}")
 ```


# 7. Rangos de números

La función `range()` permite **generar secuencias de números** de manera eficiente.  
Es muy útil en **bucles `for`**, pero también se puede usar en otras situaciones.

## 7.1 Generar una secuencia de números

El siguiente código genera los números del **0 al 9**:

Ejemplo: range(n) genera números del 0 a n-1

```python
# Generando una secuencia de números del 0 al 9
for num in range(10):
  print(num)
```

---

## Range(inicio, fin)

También podemos definir un **rango con un inicio y un fin**, por ejemplo, del `5` al `9`:

Ejemplo: range(inicio, fin) genera números desde inicio hasta fin-1

```python
# Generando una secuencia de números del 5 al 9
for num in range(5, 10):
  print(num)
```

## Range(inicio, fin, paso)

Podemos **especificar un paso** para controlar cómo avanza la secuencia:

Ejemplo: range(inicio, fin, paso) con paso positivo

```python
# Generando una secuencia de 0 a 1000 en intervalos de 5
for num in range(0, 1000, 5):
  print(num)
```

También podemos usar valores **negativos** en `range()`:

Ejemplo: range() con valores negativos

```python
# Generando números negativos de -5 a -1
for num in range(-5, 0):
  print(num)
```

O también:

Ejemplo: range() con paso negativo

```python
# Cuenta regresiva del 10 al 1
for num in range(10, 0, -1):
  print(num)
```

- `range(n)` genera números **desde `0` hasta `n-1`**.
- `range(inicio, fin)` genera números **desde `inicio` hasta `fin-1`**.
- `range(inicio, fin, paso)` permite definir un **incremento o decremento** personalizado.
- `range()` es ampliamente utilizado en **bucles `for`** y otras estructuras de control.

## 7.2  Ejecutar una acción cinco veces

Si no necesitamos un índice en el bucle, podemos usar `_` como **variable descartada**:

Ejemplo: Usar range() para repetir una acción

```python
# Ejecutar una acción cinco veces
for _ in range(5):
  print("Hacer cinco veces algo")
```

### ¿Cómo funciona?

- `range(5)` genera una secuencia de **5 números** (`0, 1, 2, 3, 4`).
- La variable `_` indica que **no nos interesa** el valor actual, solo queremos que el bucle se repita.

# 8. “else” en el “for”

El bloque `else` en un bucle `for` se ejecuta al finalizar el bucle, a menos que el bucle haya sido interrumpido por una instrucción `break`:

```python
for elemento in iterable:
    # Bloque de código para cada elemento
else:
    # Bloque de código si el bucle termina sin interrupción
```

# 9. Break y continue

- **`break`**: Esta instrucción se utiliza para **salir completamente de un bucle** cuando se cumple una condición específica. Cuando se encuentra la instrucción `break`, el bucle se detiene inmediatamente y el control pasa al código que sigue después del bucle.
- **`continue`**: En cambio, la instrucción `continue` se utiliza para **omitir la iteración actual** y pasar a la siguiente iteración del bucle. El bucle no se detiene por completo; simplemente salta a la siguiente iteración.

```python
for i in range(10):
    if i == 5:
        break  # Sal del bucle si i es igual a 5
    print(f"Valor de i: {i}")
```

En este caso, el bucle se detendrá cuando `i` sea igual a 5.

**`else` en bucles**:

- Los bucles en Python pueden tener una cláusula `else`. Esta cláusula se ejecuta **después de que el bucle haya terminado completamente**, siempre que no se haya interrumpido con un `break`.
- Ejemplo con `else` en un bucle `for`:

```python
for i in range(5):
    print(f"Valor de i: {i}")
else:
    print("Bucle completado sin interrupciones")
```

Si no se encuentra un `break`, el mensaje “Bucle completado sin interrupciones” se imprimirá al final.

# Pass en bucle for

Los bucles `for` no pueden estar vacíos, pero si por agluna razón tienes el bucle for sin contenido, poner el pass te evitará que devuelva un error.

```python
for x in [0,1,2]:
	pass
```

# 10. Expresiones en una sola línea (comprensión de listas)

- Python permite escribir bucles y expresiones condicionales en una sola línea. Esto se llama **comprensión de listas**.
- Ejemplo de comprensión de lista para crear una lista de los cuadrados de los números del 0 al 9:


```python
squares = [x**2 for x in range(10)]
print(squares)
```

Esto crea una lista `[0, 1, 4, 9, 16, 25, 36, 49, 64, 81]`.


# ¿Qué es un iterador y un iterable?

🌀 Iteradores en Python

En Python, un iterador es un objeto que implementa los métodos especiales __iter__() y __next__() para permitir recorrer sus elementos uno a uno.

🔹 ¿Qué es un iterable?

Un objeto que puede ser recorrido con un for, como una lista, una tupla o un string. Internamente, al usar for, Python convierte ese iterable en un iterador.

🔹 ¿Qué es un iterator?

Un objeto que tiene:
	•	__iter__() → devuelve el propio objeto iterador.
	•	__next__() → devuelve el siguiente valor. Si no hay más, lanza StopIteration.

```python
class MyNumbers:
    def __init__(self):
        self.a = 1

    def __iter__(self):
        return self

    def __next__(self):
        if self.a <= 5:
            x = self.a
            self.a += 1
            return x
        else:
            raise StopIteration

obj = MyNumbers()
it = iter(obj)

for num in it:
    print(num)
```

 **🧠 Notas importantes:**

- Puedes inicializar los atributos en __init__() (más claro) o en __iter__() (menos común).
    
- El método __next__() debe lanzar StopIteration para decirle a Python que ya no hay más elementos.
    
- Esto es la base para entender cómo funcionan los bucles for por dentro y cómo crear tus propios objetos que se pueden recorrer.