---
aliases: 
link: 
tags: 
categoria:
  - Funciones de python
subcategoria:
---

Las funciones son bloques de código reutilizables que realizan tareas específicas. En Python, hay varios tipos de funciones:

# Funciones incorporadas (built-in functions)
 
 Python proporciona muchas funciones incorporadas que están disponibles sin necesidad de importar módulos adicionales. Estas funciones son parte del lenguaje y se pueden usar directamente.
  
Algunas **funciones incorporadas importantes**:

  - **`abs(x)`**: Devuelve el valor absoluto de un número.
  - **`all(iterable)`**: Devuelve `True` si todos los elementos del iterable son verdaderos.
  - **`any(iterable)`**: Devuelve `True` si al menos un elemento del iterable es verdadero.
  - **`bin(x)`**: Convierte un número entero a una cadena binaria.
  - **`bool(x)`**: Convierte un valor a `True` o `False` según su verdad.
  - **`len(iterable)`**: Devuelve la longitud (cantidad de elementos) de un iterable (lista, cadena, etc.).
  - **`max(iterable)`** y **`min(iterable)`**: Devuelven el valor máximo y mínimo en un iterable, respectivamente.
  - **`sum(iterable)`**: Devuelve la suma de los elementos en un iterable numérico.
  - **`len()`**:  Devuelve la longitud (cantidad de elementos) de un iterable (lista, cadena, etc.).
  - **`type()`**:  Devuelve el tipo de datos de un objeto.
  - **`str(), int(), float()`**:  Convierten valores a cadenas, enteros o números de punto flotante, respectivamente
  - **`input()`**:  Lee una entrada del usuario desde la consola.
  - **`range()`** Genera una secuencia de números
  - **`list()`**, **`tuple()`**, **`set()`**: Crean listas, tuplas y conjuntos, respectivamente.
  - **`sorted()`**: Ordena una lista o iterable.


# Ejemplos de funciones incorporadas
 
 ```python
 # Ejemplo de abs()
 print(abs(-7))  # Resultado: 7
 
 # Ejemplo de all()
 print(all([True, True, False]))  # Resultado: False
 
 # Ejemplo de any()
 print(any([True, True, False]))  # Resultado: True
 
 # Ejemplo de len()
 print(len("Python"))  # Resultado: 6
 
 # Ejemplo de max()
 print(max([5, 8, 3, 10]))  # Resultado: 10
 
 # Ejemplo de sum()
 print(sum([1, 2, 3, 4]))  # Resultado: 10
 ```

```python
print("¡Hola, mundo!")
```

```python
nombre = "Python"
print(len(nombre))  # Resultado: 6 
```

```python
numero = 42
print(type(numero))  # Resultado: <class 'int'>
```

```python
num_str = "123"
num_int = int(num_str)  # Convierte a entero
num_float = float(num_str)  # Convierte a flotante
```

```python
nombre = input("Ingresa tu nombre: ")
print(f"Hola, {nombre}!")
```

```python
for i in range(5):
    print(i)  # Imprime 0, 1, 2, 3, 4
```

```python
mi_lista = list(range(5))
mi_tupla = tuple(range(5))
mi_conjunto = set(range(5))
```

```python
nombres = ["Ana", "Carlos", "David"]
print(sorted(nombres))  # Resultado: ['Ana', 'Carlos', 'David']
```

# Diferencia entre funciones definidas por el usuario y funciones incorporadas
 
 - Las funciones definidas por el usuario son específicas para tu programa y se crean según tus necesidades.
 - Las funciones incorporadas son parte del lenguaje Python y están disponibles en cualquier programa sin necesidad de definirlas.

Recuerda que las funciones son una parte fundamental de la programación, y dominarlas te permitirá escribir código más limpio y eficiente. ¡Sigue explorando y practicando! 🐍🚀


# Módulos built-in de python

Los **módulos built-in de Python** son **módulos que vienen incluidos con la instalación de Python**, sin necesidad de instalarlos manualmente.

Estos módulos contienen funciones y clases que permiten realizar diversas tareas como manipulación de archivos, operaciones matemáticas, generación de números aleatorios, manejo de fechas, entre otras.

---

Características de los módulos built-in**

- ✅ No requieren instalación adicional.
- ✅ Se importan con import nombre_modulo.
- ✅ Son optimizados y eficientes, ya que muchos están escritos en **C**.
- ✅ Permiten ampliar las funcionalidades de Python sin necesidad de librerías externas.

**📌 Ejemplos de módulos built-in más usados**

Aquí tienes algunos de los más importantes:

| **Módulo**  | **Función principal**                                                  |
| ----------- | ---------------------------------------------------------------------- |
| math        | Funciones matemáticas avanzadas (raíces, logaritmos, trigonometría)    |
| random      | Generación de números aleatorios                                       |
| datetime    | Manejo de fechas y horas                                               |
| time        | Funciones relacionadas con el tiempo y pausas en la ejecución          |
| os          | Interacción con el sistema operativo (archivos, procesos, directorios) |
| sys         | Manejo del sistema y argumentos de la línea de comandos                |
| json        | Trabajar con datos en formato JSON                                     |
| re          | Expresiones regulares para búsqueda y manipulación de texto            |
| collections | Estructuras de datos avanzadas como Counter, deque, defaultdict        |
| itertools   | Funciones para trabajar con iteradores y combinaciones                 |
| functools   | Herramientas para funciones como lru_cache, partial                    |
| io          | Manejo avanzado de archivos y flujos de entrada/salida                 |
| csv         | Lectura y escritura de archivos CSV                                    |
| shutil      | Operaciones de alto nivel con archivos y directorios                   |
| threading   | Manejo de hilos para ejecución en paralelo                             |

Ejemplo de uso: 

```python
import math

print(math.sqrt(16))  # Raíz cuadrada de 16 → 4.0
print(math.pi)        # Valor de π → 3.141592653589793
```

