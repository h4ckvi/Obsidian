---
aliases: 
link: 
tags: 
categoria:
  - Funciones de python
subcategoria:
---

<!--INDICE-->
# Índice

- [[#1. Índice]]
- [[#2. Funciones definidas por el usuario]]
- [[#3. Valores múltiples en una función]]
- [[#4. Argumentos de longitud  `args`  y de clave-valor `**kwargs`]]
  - [[#4.1. Argumentos de clave-valor variable (**kwargs)]]
  - [[#4.2. Argumentos de longitud `*args`]]
- [[#5. Argumentos por posición y argumentos por clave]]
  - [[#5.1. Argumentos por posición]]
  - [[#5.2. Argumentos por clave]]
  - [[#5.3. ¿Se pueden combinar? Sí]]
- [[#6. Función con valores por defecto y opcionales]]
  - [[#6.1. 5.1 Ejemplo de Función con Valores por Defecto y Opcionales]]
- [[#7. Pasar una lista como argumento]]
- [[#8. Llamar a funciones definidas en orto módulo o clase]]
- [[#9. Devolver valores con `return`]]
- [[#10. Uso de `pass` para funciones vacías]]
- [[#11. Recursividad]]
- [[#12. Documentar una función con `docstring`]]
  - [[#12.1. 7.1 Ejemplo: Documentar una función con docstring]]
  - [[#12.2. 7.2 ¿Por qué utilizar docstrings?]]
<!--/INDICE-->


Las funciones son bloques de código reutilizables que realizan tareas específicas. En Python, hay varios tipos de funciones.

Los términos parámetro y argumento pueden ser usados para lo mismo: información que se pasa en la función.

> [!NOTE] Nota:
> Desde la perspectiva de una función:
> 
> Un parámetro es la variable que aparece entre paréntesis en la definición de la función.
> 
> Un argumento es el valor que se envía a la función cuando se llama.
> 
>> [!NOTE] Nota 2:
>> Por defecto, una función debe ser llamada con el número correcto de argumentos. Lo que significa que si tu función espera 2 argumentos, tienes que llamar a la función con 2 argumentos, ni más, ni menos.

- Las funciones permiten reutilizar código y mejorar la organización del programa.
- Se pueden definir funciones sin parámetros, con parámetros, y que retornen valores.
- Utilizar funciones facilita la mantenibilidad y claridad del código.

# 2. Funciones definidas por el usuario
 
- Para crear una función, utilizamos la palabra clave **`def`** seguida del nombre de la función y paréntesis `()`.
- Dentro de los paréntesis, puedes especificar los **parámetros** que la función aceptará (si es necesario).
- Luego, se define el **cuerpo de la función** con dos puntos `:` y se indentan las instrucciones que forman parte de la función.
 
 ```python
 def saludar(nombre):
	  print(f"Hola, {nombre}!")
 
 saludar("Juan")
 ```

 - En este ejemplo, `saludar` es una función que toma un argumento (`nombre`) y muestra un saludo personalizado.
 
```python
def suma(a, b):
    resultado = a + b
    return resultado

# Llamada a la función
resultado_suma = suma(5, 3)
print(f"Resultado de la suma: {resultado_suma}")
```

- `suma` es el nombre de la función.
- `a` y `b` son los parámetros.
- El cuerpo de la función calcula


**Listas**:

 - Una lista es una colección ordenada de elementos. Puedes almacenar varios valores en una lista y acceder a ellos mediante índices.
 - Ejemplo:

 
 ```python
 def obtener_numeros():
	  return [1, 2, 3, 4, 5]
 
 numeros = obtener_numeros()
 print(numeros)  # Resultado: [1, 2, 3, 4, 5]
 ```
 

 
**Tuplas**:
 
 - Las tuplas son similares a las listas, pero son **inmutables** (no se pueden modificar después de la creación).
 - Ejemplo:

 
 ```python
 def obtener_coordenadas():
	  return (10, 20)
 
 x, y = obtener_coordenadas()
 print(f"Coordenadas: x={x}, y={y}")  # Resultado: Coordenadas: x=10, y=20
 ```

**Diccionarios**:
 
 - Los diccionarios almacenan pares clave-valor. Cada valor se asocia con una clave única.
 - Ejemplo:
 
 ```python
 def obtener_informacion_persona():
	  return {"nombre": "Ana", "edad": 25, "ciudad": "Madrid"}
 
 persona = obtener_informacion_persona()
 print(persona["nombre"])  # Resultado: Ana
 ```
 
 
# 3. Valores múltiples en una función
 
 - Puedes devolver múltiples valores desde una función utilizando una tupla o una lista.
 - Ejemplo:
 
 ```python
 def obtener_datos():
	  nombre = "Carlos"
	  edad = 30
	  return nombre, edad
 
 nombre, edad = obtener_datos()
 print(f"Nombre: {nombre}, Edad: {edad}")  # Resultado: Nombre: Carlos, Edad: 30
 ```


# 4. Argumentos de longitud  `args`  y de clave-valor `**kwargs`

## 4.1. Argumentos de clave-valor variable (**kwargs)

La siguiente función utiliza `**kwargs` para recibir un número variable de argumentos nombrados y mostrarlos. De este modo, la función recibirá un diccionario de argumentos y podrá acceder a los elementos correspondientes:

Ejemplo:

```python
# Argumentos de clave-valor variable (**kwargs)
def mostrar_informacion_de(**kwargs):
  for clave, valor in kwargs.items():
      print(f"{clave}: {valor}")

mostrar_informacion_de(nombre="midudev", edad=25, sexo="gato")
print("\n")
mostrar_informacion_de(name="madeval", edad=21, country="Uruguay")
print("\n")
mostrar_informacion_de(nick="pheralb", es_sub=True, is_rich=True)
print("\n")
mostrar_informacion_de(super_name="felixicaza", es_modo=True, gatos=40)
```

- Funciones básicas con argumentos posicionales y por clave.
- Uso de parámetros por defecto.

## 4.2. Argumentos de longitud `*args`

- Cuando defines una función con `*args`, puedes pasar cualquier cantidad de argumentos posicionales al llamarla.
- Dentro de la función, los argumentos pasados se agrupan automáticamente en una **tupla** llamada `args`.
- Puedes iterar sobre esta tupla o realizar otras operaciones según tus necesidades.

```python
def suma(*args):
    total = 0
    for num in args:
        total += num
    return total

resultado = suma(1, 2, 3, 4, 5)
print(f"La suma es: {resultado}")  # Resultado: La suma es: 15
```

En este ejemplo:

- La función `suma` acepta cualquier cantidad de argumentos posicionales.
- Los valores pasados (1, 2, 3, 4, 5) se agrupan en la tupla `args`.
- La función suma los valores y devuelve el resultado.

> [!NOTE] Puedes nombrar el parámetro de cualquier manera, pero es una buena práctica usar `*args` para que otros programadores entiendan su propósito.

---

# 5. Argumentos por posición y argumentos por clave

En Python, los argumentos de una función se pueden pasar **por posición** o **por clave** (también conocidos como argumentos nombrados).

- **Argumentos por posición:** Se pasan en el mismo orden en que fueron definidos en la función.
- **Argumentos por clave:** Se pasan especificando el nombre del parámetro, lo que permite enviarlos en cualquier orden.

## 5.1. Argumentos por posición

En el siguiente ejemplo, la función `describir_persona` recibe tres parámetros: `nombre`, `edad` y `sexo`.  
Al llamarla con argumentos por posición, el orden es fundamental:

Ejemplo: Llamadas con argumentos por posición

```python
# Argumentos por posición
def describir_persona(nombre: str, edad: int, sexo: str):
  print(f"Soy {nombre}, tengo {edad} años y me identifico como {sexo}")

# Llamadas con argumentos posicionales
describir_persona(1, 25, "gato") # Se pasa 1 como nombre, 25 como edad y "gato" como sexo
describir_persona("midudev", 25, "gato") # Correcto: nombre="midudev", edad=25, sexo="gato"
describir_persona("hombre", "madeval", 39) # Orden incorrecta: se pasan los argumentos en un orden no esperado
```

## 5.2. Argumentos por clave

Con los argumentos por clave, se especifica el nombre del parámetro en cada llamada, lo que permite enviarlos en cualquier orden:

Ejemplo: Llamadas con argumentos por clave

```python
# Argumentos por clave
# Llamadas con argumentos nombrados
describir_persona(sexo="gato", nombre="midudev", edad=25)
describir_persona(sexo="hombre", nombre="madeval", edad=21)
```

## 5.3. ¿Se pueden combinar? Sí

```python
def func(a, b, /, c, *, d, e):
    print(a, b, c, d, e)

func(1, 2, 3, d=4, e=5)  # ✅ Correcto
```

- a, b → solo posicionales
    
- c → puede ser posicional o keyword
    
- d, e → solo keyword

# 6. Función con valores por defecto y opcionales

- Puedes definir valores por defecto para los parámetros de una función. Estos valores se utilizan si no se proporcionan argumentos específicos al llamar la función.
- Además, puedes crear parámetros opcionales que el usuario puede o no proporcionar al llamar la función.

## 6.1. Ejemplo de Función con Valores por Defecto y Opcionales

```python
def saludar(nombre="Invitado", saludo="Hola"):
    mensaje = f"{saludo}, {nombre}!"
    return mensaje

# Llamadas a la función
print(saludar())  # Resultado: Hola, Invitado!
print(saludar("Ana"))  # Resultado: Hola, Ana!
print(saludar("Carlos", "¡Buen día!"))  # Resultado: ¡Buen día!, Carlos!
```

En este ejemplo:

- La función `saludar` tiene dos parámetros con valores por defecto: `nombre` y `saludo`.
- Si no se proporcionan argumentos, se utilizan los valores por defecto.
- Puedes especificar valores diferentes al llamar la función, como en el tercer ejemplo.

>[!info] Si en una función no retornamos el resultado u objeto con la palabra clave `retunrn` el resultado será un `none`
>`None` es un valor especial 'nulo' que no puede hacer nada interesante. Es un marcador de posición común que representa la falta de un valor útil real. Las funciones que no quieren devolver nada devuelven `None` por defecto. Si ves un mensaje de error sobre `None` o `NoneType`, a menudo significa que has asignado algo incorrecto a una variable:

# 7. Pasar una lista como argumento

Se pueden enviar cualquier tipo de datos como argumentos de una función (strings, numbers, lists, dictionaries, etc.), y se tratarán como el mismo tipo de dato dentro de la función.

Por ejemplo, si envías una lista como argumento, seguirá siendo una lista cuando llegue a la función:

```python
def my_function(food):  
  for x in food:  
    print(x)  
  
fruits = ["apple", "banana", "cherry"]  
  
my_function(fruits)
```


# 8. Llamar a funciones definidas en orto módulo o clase

```PYTHON
# Importing the math module
import math
math.pow(2,4) # Calling the pow() function from the math module
16.0
```

```python
# Calling methods or functions in classes and modules.
start_text = "my silly sentence for examples."
str.upper(start_text) # Calling the upper() method for the built-in str class.
```

# 9. Devolver valores con `return`

Para que una función devuelva un valor, utiliza `return`

```python
def my_function(x):
  return 5 * x

print(my_function(3))
print(my_function(5))
print(my_function(9))
```


> [!hey]- ¿de que se diferencia return de print?
> 
> # **✅  return**
> 
> - **Devuelve un valor** desde una función al lugar donde se llamó.
>     
> - Ese valor **puede ser usado más adelante** (asignado a una variable, manipulado, etc.).
>     
> - Finaliza la ejecución de la función en ese punto.
>     
> 
> ---
> 
> # **✅ print()**
> 
> - **Muestra algo en pantalla**, pero **no devuelve ningún valor**.
>     
> - Solo sirve para visualizar, **no puedes reutilizar lo que imprime**.
>     
> 
> ---
> 
> ```python
> def con_return(x):
>     return 5 * x
> 
> def con_print(x):
>     print(5 * x)
> 
> resultado = con_return(3)
> print("Valor devuelto:", resultado)
> 
> resultado2 = con_print(3)
> print("Valor devuelto:", resultado2)  # Muestra None, porque no devuelve nada
> ```
> 
> ```python
> Valor devuelto: 15
> Valor devuelto: None
> ```
> 
> - Usa return si necesitas **usar el resultado fuera de la función**.
>     
> - Usa print() solo si quieres **mostrar información en pantalla** sin reutilizarla.
> 
> 

# 10. Uso de `pass` para funciones vacías

Las definiciones de función no pueden estar vacías, pero si por alguna razón tienes una definición de función sin contenido, pon la sentencia pass para evitar obtener un error.

```python
def myfunction():  
  pass
```


# 11. Recursividad

La **recursividad** es una técnica en la que una **función se llama a sí misma** para resolver un problema dividiéndolo en **subproblemas más pequeños**.

```python

```

# 12. Documentar una función con `docstring`

Documentar funciones en Python

La documentación de funciones es fundamental para **mejorar la legibilidad** y **facilitar el mantenimiento** del código. En Python, se utilizan los **docstrings** para describir qué hace una función, sus parámetros y su valor de retorno.

## 12.1. Ejemplo: Documentar una función con docstring

El siguiente ejemplo muestra cómo documentar una función que resta dos números:

Ejemplo: Función 'restar' documentada con un docstring

```python
# Documentar funciones con docstring
def restar(a, b):
  """Resta dos números y devuelve el resultado"""
  return a - b
```

## 12.2. ¿Por qué utilizar docstrings?

- **Claridad:** Facilita la comprensión del propósito de la función.
- **Mantenibilidad:** Ayuda a otros (y a ti mismo) a recordar cómo y para qué fue diseñada la función.
- **Integración con herramientas:** Muchos entornos de desarrollo y herramientas de documentación (como Sphinx) utilizan docstrings para generar documentación automática.

---

Recuerda que una **buena documentación** es esencial para el desarrollo colaborativo y la escalabilidad de tus proyectos.