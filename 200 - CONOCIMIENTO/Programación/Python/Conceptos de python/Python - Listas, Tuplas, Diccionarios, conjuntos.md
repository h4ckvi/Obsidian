---
aliases: 
link: 
tags: 
categoria:
  - Estructuras de datos en python
subcategoria:
---

- Ver [[000 - Conceptos de python]]
- Ver [[Python - Métodos de diccionarios]]

<!--INDICE-->
# Índice

- [[#1. Índice]]
- [[#2. Listas]]
  - [[#2.1. Formas de crear listas]]
  - [[#2.2. Slicing o rebanado (rangos en listas)]]
  - [[#2.3. Buscar por índices pares]]
  - [[#2.4. Lista en orden inverso]]
  - [[#2.5. Modificar una lista]]
  - [[#2.6. Añadir elementos a una lista]]
  - [[#2.7. Comprensión de listas]]
  - [[#2.8. Copiar listas]]
- [[#3. Tuplas]]
  - [[#3.1. Formas de crear tuplas]]
  - [[#3.2. ¿Cómo modificar una tupla?]]
  - [[#3.3. Agregar datos a una tupla]]
  - [[#3.4. Multiplicar datos de una tupla]]
  - [[#3.5. Eliminar datos de una tupla]]
  - [[#3.6. Desemplaquetar una tupla]]
  - [[#3.7. Recorrer una tupla (loop tuples)]]
- [[#4. Conjuntos]]
  - [[#4.1. Formas de crear conjuntos y conjuntos congelados]]
  - [[#4.2. Agregar datos a un conjunto]]
  - [[#4.3. Recorrer los elementos de un conjunto]]
  - [[#4.4. Eliminar datos de un conjunto]]
  - [[#4.5. Superconjuntos y subconjuntos]]
  - [[#4.6. Datos comunes en dos o más conjuntos]]
  - [[#4.7. Diferencias entre dos o mas conjuntos]]
  - [[#4.8. Maneras de unir dos o más conjuntos]]
    - [[#4.8.1. Union y update]]
    - [[#4.8.2. Unir múltiples conjuntos]]
    - [[#4.8.3. Unir un conjunto con otros tipos de datos]]
- [[#5. Diccionarios]]
  - [[#5.1. Crear diccionarios]]
    - [[#5.1.1. Crear diccionario a partir de secuencia de claves .`fromkeys()`]]
  - [[#5.2. Modificar diccionarios]]
    - [[#5.2.1. Modificar valores]]
    - [[#5.2.2. Eliminar una propiedad]]
    - [[#5.2.3. Extraer una propiedad y eliminarla]]
  - [[#5.3. Combinar diccionarios]]
  - [[#5.4. Comprobar la existencia de una clave]]
  - [[#5.5. Obtener claves, valores e items]]
  - [[#5.6. Iterar sobre un diccionario]]
- [[#6. Consideraciones]]
<!--/INDICE-->

Tabla de características: ^16e405

| **Tipo**                 | **Mutables** | **Ordenadas**            | **Permiten duplicados** | **Indexables**    | **Sintaxis**     | **Uso típico**                              |
| ------------------------ | ------------ | ------------------------ | ----------------------- | ----------------- | ---------------- | ------------------------------------------- |
| **[[#2. Listas]]**       | ✅ Sí        | ✅ Sí                    | ✅ Sí                   | ✅ Sí             | [1, 2, 3]        | Almacenar colecciones ordenadas y editables |
| **[[#3. Tuplas]]**       | ❌ No        | ✅ Sí                    | ✅ Sí                   | ✅ Sí             | (1, 2, 3)        | Datos constantes e inmutables               |
| **[[#4. Conjuntos]]**    | ✅ Sí        | ❌ No                    | ❌ No (sin duplicados)  | ❌ No             | {1, 2, 3}        | Conjuntos únicos, operaciones de conjuntos  |
| **[[#5. Diccionarios]]** | ✅ Sí        | ✅ Sí (desde Python 3.7) | ❌ Claves únicas        | ✅ Sí (por clave) | {"a": 1, "b": 2} | Pares clave-valor, lookup                   |


**📌 Notas adicionales:**

- Los **sets** son ideales para eliminar duplicados o hacer operaciones como intersección, unión, etc.
    
- Las **tuplas** ocupan menos memoria y son más rápidas que las listas.
    
- Los **diccionarios** permiten acceder rápidamente a valores mediante claves únicas.
    
- Las **listas** son las más flexibles y utilizadas para la mayoría de tareas generales.

Hay <u>cuatro tipos de datos de recopilación </u>en el lenguaje de programación Python:

- **[Lista](https://www.w3schools.com/python/python_lists.asp)** es una colección [^5]ordenada y cambiante. Permite miembros duplicados.
- **[Tupla](https://www.w3schools.com/python/python_tuples.asp)** es una colección ordenada e inmutable. Permite miembros duplicados.
- **[Establecer](https://www.w3schools.com/python/python_sets.asp)** es una colección que no está ordenada inmutable*, y sin indexar. Sin miembros duplicados.
- **[Diccionario](https://www.w3schools.com/python/python_dictionaries.asp)** es una colección que se ordena** y cambiante. Sin miembros duplicados.

<br>
<br>
<br>

# 2. Listas

> [!info] Ver [[#^16e405|Tabla de características de los 4 tipos de datos]]

Una lista es una _secuencia_ (una colección/contenedor con orden determinado) de cualquier cantidad de valores, stos valores a menudo son referidos como _elementos_ y pueden ser cualquier cosa: números, cadenas, valores booleanos, ¡incluso otras listas! También pueden ser una mezcla de dichos tipos. 

Los elementos de la lista están indexados, el primer elemento tiene índice `[0]`, el segundo elemento tiene índice `[1]` etc.


> [!info]+ Características: 
> Los elementos de la lista se ordenan, se pueden cambiar y **permiten valores duplicados.**
> - Se pueden **modificar**: Lo que significa que podemos cambiar, agregar y eliminar elementos en una lista después de que se haya creado.
> - Se pueden **llamar a nivel de índices** (elementos)
> - Se escriben con **corchetes**
> - Podemos crear listas con **diferentes tipos de datos**

> [!warning] Cuando decimos que las listas están ordenadas, significa que los elementos tienen un orden definido, y ese orden no cambiará.
> Hay algunos [[Python - Métodos de listas]] que cambian el orden, pero en general: el orden de los artículos no cambiará.

## 2.1. Formas de crear listas

```python
# Creación de listas
lista1 = [1, 2, 3, 4, 5]  # Lista de enteros
lista2 = ["manzanas", "peras", "plátanos"]  # Lista de cadenas
lista3 = [1, "hola", 3.14, True]  # Lista de tipos mixtos

# Creación de una lista sobre un tipo de dato que NO es una lista
thislist = list(("Apple", "Banana", "cherry")) # Nótese el doble paréntesis

# Otras formas de listas
lista_vacia = []  # Lista vacía
lista_de_listas = [[1, 2], ["calcetin", 4]]  # Lista de listas
matrix = [[1, 2], [2, 3], [4, 5]]  # Lista que representa una matriz
```

```python
thislist = ["apple", "banana", "cherry"]  
print(len(thislist))
```

## 2.2. Slicing o rebanado (rangos en listas)

En Python, el **slicing** o **rebanado** es una técnica que permite acceder a una porción (sublista) de una lista utilizando un índice de inicio, fin y un paso. Es muy útil para manipular listas de manera eficiente.

El slicing se realiza utilizando la sintaxis `[inicio:fin:paso]`. Aquí hay algunos ejemplos prácticos:

```python
# Lista original
lista1 = [1, 2, 3, 4, 5]

# Slicing de la lista
print(lista1[1:4])  # Sublista desde el índice 1 hasta el índice 4 (sin incluir el índice 4): [2, 3, 4]
print(lista1[:3])   # Sublista desde el inicio hasta el índice 3 (sin incluirlo): [1, 2, 3]
print(lista1[3:])   # Sublista desde el índice 3 hasta el final: [4, 5]
print(lista1[:])    # Copia completa de la lista: [1, 2, 3, 4, 5]

# Soluciones
# 1 -> [2, 3, 4]
# 2 -> [1, 2, 3]
# 3 -> [4, 5]
# 4 -> [1, 2, 3, 4, 5]
```

En Python, el **slicing** ofrece un poder increíble para manipular listas de formas creativas. Aquí te mostramos dos trucos avanzados utilizando el slicing que te sorprenderán.

## 2.3. Buscar por índices pares

Puedes acceder a los elementos en índices pares usando un paso de 2. Este es un truco para extraer solo los elementos de los índices 0, 2, 4, 6, etc.

```python
# Lista original
lista1 = [1, 2, 3, 4, 5, 6, 7, 8]

# Índices pares
print(lista1[::2])  # [1, 3, 5, 7]
```

## 2.4. Lista en orden inverso

Utilizando un paso negativo (`[::-1]`), puedes obtener la lista en orden inverso, lo cual es útil para revertir el contenido de la lista.


```python
# Lista original
lista1 = [1, 2, 3, 4, 5, 6, 7, 8]

# Índices inversos
print(lista1[::-1])  # [8, 7, 6, 5, 4, 3, 2, 1]
```

## 2.5. Modificar una lista

Puedes acceder a un elemento de la lista por su índice y asignarle un nuevo valor para modificarlo.


```python
# Modificar un elemento
lista1 = [1, 2, 3, 4, 5]
lista1[0] = 20  # Cambia el primer elemento
print(lista1)  # [20, 2, 3, 4, 5]
```

## 2.6. Añadir elementos a una lista

**Forma larga y menos eficiente**

Puedes añadir elementos a una lista utilizando el operador `+`, pero es menos eficiente ya que crea una nueva lista en memoria.

```python
# Forma larga y menos eficiente
lista1 = [1, 2, 3]
lista1 = lista1 + [4, 5, 6]  # Añade los elementos
print(lista1)  # [1, 2, 3, 4, 5, 6]
```

**Forma corta y más eficiente**

Una forma más eficiente de añadir elementos es utilizando el operador `+=`, que modifica la lista original directamente.

```python
# Forma corta y más eficiente
lista1 = [1, 2, 3]
lista1 += [7, 8, 9]  # Añade los elementos de manera más eficiente
print(lista1)  # [1, 2, 3, 7, 8, 9]
```

```python
lista = ["Alvaro Tejada", True, 1.85, "Pepe"]
print(lista)

lista = ["Alvaro Tejada", True, 1.85, "Pepe"]
print(lista[1])
```

## 2.7. Comprensión de listas

La **comprensión de listas** (`list comprehension`) es una forma concisa y eficiente de **crear listas** en Python.  Nos permite <u>generar una nueva lista aplicando una expresión a cada elemento de un iterable.</u>

```python
newlist = [expression for item in iterable if condition == True]
```

**Transformar elementos con comprensión de listas**

En el siguiente ejemplo, convertimos los nombres de animales en **mayúsculas** de forma compacta:

```python
# Usando list comprehension para convertir a mayúsculas
animales = ["perro", "gato", "raton", "loro", "pez", "canario"]
animales_mayus = [animal.upper() for animal in animales]

print(animales_mayus)
```

¿Cómo funciona?

- `[animal.upper() for animal in animales]` crea una **nueva lista** donde cada `animal` de la lista original se convierte a **mayúsculas** con `.upper()`.
- Es una alternativa más compacta a usar un bucle `for` tradicional.


- La **comprensión de listas** permite generar listas de manera más **eficiente** y **legible**.
- Es útil para **transformar, filtrar y modificar** listas en una sola línea de código.

## 2.8. Copiar listas

No puede copiar una lista simplemente escribiendo `list2 = list1`, porque: `list2` sólo será un _referencia_ a `list1`y cambios realizados en `list1` también se hará automáticamente en `list2`.

Puede utilizar el método de lista incorporado `copy()` para copiar una lista.

```python
thislist = ["apple", "banana", "cherry"]  
mylist = thislist.copy()  
print(mylist)
```

Otra forma de hacer una copia es usar el método incorporado `list()`.

```python
thislist = ["apple", "banana", "cherry"]  
mylist = list(thislist)  
print(mylist)
```

También puede hacer una copia de una lista utilizando el `:` (rebanada) operador.

```python
thislist = ["apple", "banana", "cherry"]  
mylist = thislist[:]  
print(mylist)
```

<br>
<br>
<br>

# 3. Tuplas

> [!info] Ver [[#^16e405|Tabla de características de los 4 tipos de datos]]

Se utilizan para almacenar múltiples elementos en una sola variable.

Iguales a las [[#Listas]] pero se ponen **entre paréntesis `()`**. La diferencia principal con las listas es que las tuplas **no se pueden modificar**.

> [!info]+ Características: 
> - Los elementos están ordenados, igual que las [[#Listas]]
>  - permiten valores **duplicados.**
> - **NO** pueden **modificar**: Lo que significa que podemos cambiar, agregar y eliminar elementos en una lista después de que se haya creado.
> - Se pueden **llamar a nivel de índices** (elementos)
> - Se escriben con **paréntesis**
> - Podemos crear tuplas con **diferentes tipos de datos**


```python
lista = ("Alvaro Tejada", True, 1.85, "Pepe")
print(lista)

tupla = ("Silvia Tejada", False, 1.85, "Pepe")
print(lista)

#Esto se puede
lista[3] = "Eres feo"

#Esto no se puede
tupla[3] = "Eres feo"
```

## 3.1. Formas de crear tuplas

Podemos crear una tupla de las siguientes formas:

```python
# Creando tuplas con tuple()

tupla = tuple(["dato1,dato2"])

# Creando una tupla sin paréntesis de múltiples datos

tupla = "dato1", "dato"

# Creando una tupla sin paréntesis de un solo dato 

tupla = "dato", 

print(tupla)
```

<u>También se pueden utilizar las técnicas de</u> [[#Slicing o rebanado (rangos en listas)]], [[#Buscar por índices pares]], [[#Lista en orden inverso]], etc… que vimos en las listas.

## 3.2. ¿Cómo modificar una tupla?

Se puede transformar la tupla en lista, cambiar el valor y posteriormente volver a convertirlo en tupla.

```python
x = ("apple", "banana", "cherry")  
y = list(x)  
y[1] = "kiwi"  
x = tuple(y)  
  
print(x)
```

## 3.3. Agregar datos a una tupla

Como las tuplas son inmutables, no tienen un incorporado `append()` método, pero hay otras formas de agregar elementos a una tupla.

1. **Convertir en una lista**: Al igual que la solución para modificar una tupla, puede convertirla en una lista, agregar su item(s) y convertirla nuevamente en una tupla.

```python
thistuple = ("apple", "banana", "cherry")  
y = list(thistuple)  
y.append("orange")  
thistuple = tuple(y)
```

2. **Añade tupla a una tupla**. Se le permite agregar tuplas a tuplas, así que si quieres agregar un elemento, (o muchos), crea una nueva tupla con el item(s), y añadirlo a la tupla existente:

```python
thistuple = ("apple", "banana", "cherry")  
y = ("orange",)  
thistuple += y  
  
print(thistuple)
```

## 3.4. Multiplicar datos de una tupla

Si queremos multiplicar el contenido de una tupla un número de veces, podemos usar el operador `*`.

```python
# Multiplicar las frutas por 2

fruits = ("banana", "apple", "cherry")
mytuple = fruits * 2

print(mytuple)
```

## 3.5. Eliminar datos de una tupla

Las tuplas son **inmutable**, por lo que no puede eliminar elementos a partir de él, pero puede usar la misma solución alternativa que usamos para cambiar y agregar elementos de tupla:

```python
thistuple = ("apple", "banana", "cherry")  
y = list(thistuple)  
y.remove("apple")  
thistuple = tuple(y)
```

O puede eliminar la tupla por completo:

El `del` la palabra clave puede eliminar la tupla completamente:

```python
thistuple = ("apple", "banana", "cherry")  
del thistuple  
print(thistuple) #this will raise an error because the tuple no longer exists
```

## 3.6. Desemplaquetar una tupla

Cuando creamos una tupla, normalmente le asignamos valores. Esto se llama "empaquetar" una tupla.

Pero, en Python, también se nos permite <font color="#c3d69b">extraer los valores de nuevo en variables</font>. Esto se llama "<u>desempaquetar</u>":

```python
fruits = ("apple", "banana", "cherry")  
  
(green, yellow, red) = fruits  
  
print(green)  
print(yellow)  
print(red)
```


> [!hey] Oye, ¡importante!
> 
> El número de variables debe coincidir con el número de valores en la tupla de lo contrario, debe usar un asterisco para recopilar los valores restantes como una lista.
> 
> ```python
> fruits = ("apple", "banana", "cherry", "strawberry", "raspberry")  
> 
> (green, yellow, *red) = fruits  
> 
> print(green)  
> print(yellow)  
> print(red)
> ```


> [!hey]+ ¿Y si el asterisco se agrega a una variable del medio?
> 
> Python asignará valores a la variable hasta que el número de valores que quedan coincida con el número de variables que quedan.
> 
> ```python
> fruits = ("apple", "mango", "papaya", "pineapple", "cherry")  
>   
> (green, *tropic, red) = fruits  
>   
> print(green)  
> print(tropic)  
> print(red)
> ```


## 3.7. Recorrer una tupla (loop tuples)

Se pueden recorrer los elementos de una tupla con el [[Python - For loop]] y un [[Python - While loop]]. 
También se pueden recorrer los elementos de una tupla haciendo referencia a su número de índice usando `range()`y `len()`. [^1]


<br>
<br> 
<br>

# 4. Conjuntos

> [!info] Ver [[#^16e405|Tabla de características de los 4 tipos de datos]]

En Python, un conjunto (set) es una colección desordenada de elementos únicos. Se define utilizando llaves `{}`.  Se utilizan para almacenar múltiples elementos en una sola variable.

> [!info]+ Características:
> - Son inmutables, pero se pueden reconstruir al igual que las [[#2. Tuplas]].
> 	- Eso si, se pueden eliminar y añadir ítems.
> - No admite elementos duplicados.
> - Admite diferentes tipos de datos, igual que las [[#1. Listas]] y [[#2. Tuplas]].
> - Se escriben con llaves `{}`.
> - Elementos no ordenados, pueden aparecer en orden diferente cada vez que se utilizan.
> - No pueden llamar a nivel de índices (elementos).
> - Los valores `True` y `1` se consideran el mismo valor en conjuntos (sets) y se tratan como duplicados. Lo mismo pasa con `False` y `0`

```python
# Crear un conjunto
mi_conjunto = {1, 2, 3, 4, 5}

# Agregar un elemento al conjunto
mi_conjunto.add(6)

# Intentar agregar un elemento existente (no se produce duplicado)
mi_conjunto.add(3)

# Eliminar un elemento del conjunto
mi_conjunto.remove(2)

# Verificar si un elemento está en el conjunto
resultado = 4 in mi_conjunto

print(mi_conjunto)
print(resultado)
```

En este ejemplo, `mi_conjunto` contiene los números del 1 al 6. Al agregar el 3 nuevamente, no se duplica, ya que los conjuntos solo contienen elementos únicos. Luego, se elimina el 2, y al final se verifica si el 4 está presente en el conjunto.

## 4.1. Formas de crear conjuntos y conjuntos congelados

`frozenset` es similar a `set`, pero es inmutable, lo que significa que una vez que se crea, no se puede modificar agregando, eliminando o cambiando elementos. Esta inmutabilidad hace que los frozensets sean útiles en situaciones donde necesitas un conjunto que no cambie, por ejemplo, como claves en un diccionario o elementos en otro conjunto.

Por otro lado, `set(["dato1"])` se utiliza para crear un conjunto que contiene un solo elemento, que es la lista `[dato1]`. 

> Esto se debe a que `set()` espera un iterable como argumento, y cuando pasas una cadena (`"dato1"`), se interpreta como una secuencia de caracteres, donde cada carácter se convierte en un elemento separado en el conjunto. Por lo tanto, para crear un conjunto con un solo elemento que sea la cadena completa `"dato1"`, debes envolverla en una lista, como en `set(["dato1"])`.

Aquí hay un ejemplo para clarificarlo:

```python
# Crear un frozenset
conjunto_inmutable = frozenset([1, 2, 3])

# Intentar agregar un elemento (esto generará un error)
# conjunto_inmutable.add(4)  # Generaría un error 'frozenset' object has no attribute 'add'
```

```python
# Crear un conjunto con una lista como único elemento
conjunto_con_lista = set(["dato1"])

# Crear un conjunto con cada carácter de la cadena como un elemento
conjunto_con_caracteres = set("dato1")

print(conjunto_con_lista)     # Salida: {'dato1'}
print(conjunto_con_caracteres)  # Salida: {'d', 'o', '1', 't', 'a'}
```

Como se puede ver, `conjunto_con_lista` contiene la cadena completa como un solo elemento, mientras que `conjunto_con_caracteres` contiene cada carácter de la cadena como elementos separados en el conjunto.

Puedes utilizar los siguientes métodos en conjuntos para comparar si un conjunto es subconjunto o superconjunto de otro, así como para verificar si tienen datos en común o distintos:

## 4.2. Agregar datos a un conjunto

Cuando se crea un conjunto no se pueden cambiar sus elementos, pero sí se pueden agregar nuevos.

```python
# Añadir elementos a un conjunto
thisset = {"apple", "banana", "cherry"}

tisset.add("orange")

print(thisset)
```

```python
# Añadir un conjunto a otro 
thisset = {"apple", "banana", "cherry"}  
tropical = {"pineapple", "mango", "papaya"}  
  
thisset.update(tropical)  
  
print(thisset)
```


> [!important] ¡`update()` sirve para unir cualquier tipo de dato iterable con otro!
> ```python
> thisset = {"apple", "banana", "cherry"}  
> mylist = ["kiwi", "orange"]  
>   
> thisset.update(mylist)  
>   
> print(thisset)
> ```

## 4.3. Recorrer los elementos de un conjunto

Se pueden recorrer los elementos de un set con [[Python - For loop]] y [[Python - While loop]].

```python
thisset = {"apple", "banana", "cherry"}  
  
for x in thisset:  
  print(x)
```

## 4.4. Eliminar datos de un conjunto

Se pueden utilizar los métodos `remove()` o `discard()`. También `pop()`, aunque este último elimina de forma random un item porque los conjuntos no están ordenados.

```python
thisset = {"apple", "banana", "cherry"}  
  
thisset.remove("banana")
# Si el item a eliminar no lo encuentra, remove genera un error
  
print(thisset)
```

```python
thisset = {"apple", "banana", "cherry"}  
  
thisset.discard("banana")  
# Si el item a eliminar no lo encuentra, discard NO genera un error
print(thisset)
```

Eliminar todos los item de un conjunto sin eliminar el conjunto: `clear()`

```python
thisset = {"apple", "banana", "cherry"}  
  
thisset.clear()  
  
print(thisset)
```

Eliminar el conjunto directamente: `del`

```python
thisset = {"apple", "banana", "cherry"}  
  
del thisset  
  
print(thisset)
```


## 4.5. Superconjuntos y subconjuntos

1. Para verificar si un conjunto es subconjunto de otro, puedes usar el método `issubset()` o el operador de subconjunto (`<=`):

```python
conjunto1 = {1, 2, 3}
conjunto2 = {1, 2}

# Verificar si conjunto2 es un subconjunto de conjunto1
es_subconjunto = conjunto2.issubset(conjunto1)
print(es_subconjunto)  # Salida: True

# O utilizando el operador de subconjunto
es_subconjunto = conjunto2 <= conjunto1
print(es_subconjunto)  # Salida: True

```


2. Para verificar si un conjunto es superconjunto de otro, puedes usar el método `issuperset()` o el operador de superconjunto (`>=`):

```python
conjunto1 = {1, 2, 3}
conjunto2 = {1, 2}

# Verificar si conjunto1 es un superconjunto de conjunto2
es_superconjunto = conjunto1.issuperset(conjunto2)
print(es_superconjunto)  # Salida: True

# O utilizando el operador de superconjunto
es_superconjunto = conjunto1 >= conjunto2
print(es_superconjunto)  # Salida: True

```

## 4.6. Datos comunes en dos o más conjuntos

Para verificar si dos conjuntos tienen datos en común, puedes utilizar el método `intersection()` o el operador de intersección (`&`)[^2]. 

Esto te devolverá un nuevo conjunto que contiene los elementos que están presentes en ambos conjuntos, es decir, SOLO mantiene los duplicados. El método **devuelve un nuevo set con los items presentes en ambos sets.** 

```python
conjunto1 = {1, 2, 3}
conjunto2 = {2, 3, 4}

# Verificar si hay datos en común entre conjunto1 y conjunto2
datos_comunes = conjunto1.intersection(conjunto2)
print(datos_comunes)  # Salida: {2, 3}

# Alternativa: Utilizando el operador & 
datos_comunes = conjunto1 & conjunto2
print(datos_comunes)  # Salida: {2, 3}
```


Para verificar si dos conjuntos no tienen datos en común, puedes utilizar el método `isdisjoint()`. Esto devuelve `True` si no hay elementos en común entre los dos conjuntos:

```python
conjunto1 = {1, 2, 3}
conjunto2 = {4, 5, 6}

# Verificar si no hay datos en común entre conjunto1 y conjunto2
no_datos_comunes = conjunto1.isdisjoint(conjunto2)
print(no_datos_comunes)  # Salida: True
```

`intersection_update()` también mantendrá SOLO los duplicados, pero cambiará el conjunto original en lugar de devolver un nuevo conjunto.

```python
# Mantenga los elementos que existen en ambos `set1`, y `set2`:

set1 = {"apple", "banana", "cherry"}  
set2 = {"google", "microsoft", "apple"}  
  
set1.intersection_update(set2)  
print(set1)
```

Los valores `True` y `1` se consideran el mismo valor. Lo mismo ocurre con `False` y `0`.

```python
# Unir conjuntos que contengan los valores `True`, `False`, `1`, y `0`y vea lo que se considera como duplicados:

set1 = {"apple", 1,  "banana", 0, "cherry"}  
set2 = {False, "google", 1, "apple", 2, True}  
  
set3 = set1.intersection(set2)  
print(set3)
```

## 4.7. Diferencias entre dos o mas conjuntos

`difference()` y `-`[^3] devolverá un nuevo conjunto que contendrá solo los elementos del primer conjunto que no están presentes en el otro conjunto.

```python
# Mantenga todos los elementos de set1 que no estén en set2:

set1 = {"apple", "banana", "cherry"}  
set2 = {"google", "microsoft", "apple"}  
  
set3 = set1.difference(set2)    
print(set3)

# Alternativa: Puedes usar el operador `-` en lugar de `difference()` para el mismo resultado.
set3 = set1 - set2  
print(set3)
```

`difference_update()` método también se mantendrá los elementos del primer conjunto que no están en el otro conjunto, pero cambiará el conjunto original en lugar de devolver un nuevo conjunto.

```python
# Usa el `difference_update()` método para mantener los elementos que no están presentes en ambos conjuntos:

set1 = {"apple", "banana", "cherry"}  
set2 = {"google", "microsoft", "apple"}  
  
set1.difference_update(set2)  
print(set1)
```

`symmetric_difference()` o `^`[^4] método mantendrá solo los elementos que NO están presentes en ambos conjuntos.

```python
# Mantenga los elementos que no están presentes en ambos conjuntos:

set1 = {"apple", "banana", "cherry"}  
set2 = {"google", "microsoft", "apple"}  
  
set3 = set1.symmetric_difference(set2)  
print(set3)

# Alternativa: '^' para obtener el mismo resultado
set3 = set1 ^ set2  
print(set3)
```

`symmetric_difference_update()` también lo mantendrá todo pero los duplicados, pero cambiará el conjunto original en lugar de devolver un nuevo conjunto.

```python
# Usa el `symmetric_difference_update()` método para mantener los elementos que no están presentes en ambos conjuntos:

set1 = {"apple", "banana", "cherry"}  
set2 = {"google", "microsoft", "apple"}  
  
set1.symmetric_difference_update(set2)  
print(set1)
```

## 4.8. Maneras de unir dos o más conjuntos

Hay varias formas de unir dos o más conjuntos en Python.

- `union()` y `update()` los métodos se unen a todos los elementos de ambos conjuntos.  

- `intersection()` el método mantiene SOLO los duplicados.

-  `difference()` el método mantiene los artículos desde el primer conjunto que no están en el otro set(s).

- `symmetric_difference()` el método lo mantiene todo elementos EXCEPTO los duplicados.

### 4.8.1. Union y update

El `union()` method devuelve un nuevo conjunto con todos los elementos de ambos conjuntos.

> [!NOTE]
> The `update()` method inserts all items from one set into another.
> 
> The `update()` changes the original set, and does not return a new set.
> 
>>[!NOTE] `union()` and `update()` will exclude any duplicate items.

```python
set1 = {"a", "b", "c"}  
set2 = {1, 2, 3}  
  
set3 = set1.union(set2)  
print(set3)
```

<u>Alternativa:</u>

Puedes usar el `|` operador en lugar de la `union()` método, y obtendrá el mismo resultado.

```python
set1 = {"a", "b", "c"}  
set2 = {1, 2, 3}  
  
set3 = set1 | set2  
print(set3)
```

### 4.8.2. Unir múltiples conjuntos

Todos los métodos y operadores de unión se pueden usar para unir múltiples conjuntos.

Cuando uses un método, simplemente agregua más conjuntos entre paréntesis, separados por comas:

```python
set1 = {"a", "b", "c"}  
set2 = {1, 2, 3}  
set3 = {"John", "Elena"}  
set4 = {"apple", "bananas", "cherry"}  
  
myset = set1.union(set2, set3, set4)  
print(myset)
```

<u>Alternativa:</u>

```python
set1 = {"a", "b", "c"}  
set2 = {1, 2, 3}  
set3 = {"John", "Elena"}  
set4 = {"apple", "bananas", "cherry"}  
  
myset = set1 | set2 | set3 |set4  
print(myset)
```


### 4.8.3. Unir un conjunto con otros tipos de datos

Con el método `union()` se pueden unir diferentes tipos de datos como listas o tuplas al set.

```python
x = {"a", "b", "c"}  
y = (1, 2, 3)  
  
z = x.union(y)  
print(z)
```

<br>
<br>
<br>

# 5. Diccionarios

> [!info] Ver [[#^16e405|Tabla de características de los 4 tipos de datos]]

> [!info]+ Características:
> - Su estructura es ==key : value==
> - Se pueden modificar
> - No tienen un orden específico
> - Se pueden llamar a nivel de índices (en este caso la key)
> - Se escriben con llaves
> - No permiten duplicados

Estructura de datos que almacena pares clave-valor *(key : value)*. Cada elemento del diccionario tiene una clave única que se utiliza para acceder al valor asociado.

Puedes acceder a los valores utilizando las claves, modificarlos, agregar nuevos pares clave-valor y eliminar elementos según sea necesario.

```python
# Crear un diccionario
mi_diccionario = {
    'nombre': 'Álvaro', 
    'edad': 27, 
    'ciudad': 'Madrid'
}

# Acceder a un valor mediante la clave
nombre = mi_diccionario['nombre']

# Modificar un valor existente
mi_diccionario['edad'] = 28

# Agregar un nuevo par clave-valor
mi_diccionario['profesion'] = 'Analista de pruebas manuales QA'

# Eliminar un elemento del diccionario
del mi_diccionario['ciudad']

# Verificar si una clave está en el diccionario
resultado = 'edad' in mi_diccionario

print(mi_diccionario)
print(nombre)
print(resultado)

# Otro ejemplo típico de un diccionario

persona = {
"nombre": "midudev",
"edad": 25,
"es_estudiante": True,
"calificaciones": [7, 8, 9],
"socials": {
  "twitter": "@midudev",
  "instagram": "@midudev",
  "facebook": "midudev"
}
}

# Accediendo a los valores
print(persona["nombre"])  # midudev
print(persona["calificaciones"][2])  # 9
print(persona["socials"]["twitter"])  # @midudev
```

## 5.1. Crear diccionarios

**Con un conjunto de pares clave-valor:** Puedes pasar un conjunto de pares clave-valor como argumento a `dict()` para crear un diccionario. Cada par clave-valor se especifica como una tupla, donde el primer elemento es la clave y el segundo es el valor.

```python
diccionario = dict([('clave1', 1), ('clave2', 2), ('clave3', 3)])
print(diccionario)  # Salida: {'clave1': 1, 'clave2': 2, 'clave3': 3}
```

> [!NOTE]-
> el código `dict([('clave1', 1), ('clave2', 2), ('clave3', 3)])` crea un diccionario utilizando la función `dict()` y una lista de tuplas donde cada tupla representa una pareja clave-valor en el diccionario resultante.

---

**Con argumentos de palabras clave:** También puedes crear un diccionario utilizando argumentos de palabras clave donde cada argumento representa un par clave-valor.

```python
diccionario = dict(clave1=1, clave2=2, clave3=3)
print(diccionario)  # Salida: {'clave1': 1, 'clave2': 2, 'clave3': 3}
```

---

**Con una secuencia de claves y un valor inicial:** Puedes utilizar `dict.fromkeys()` para crear un diccionario a partir de una secuencia de claves, donde cada clave tendrá el mismo valor inicial.

```python
claves = ['clave1', 'clave2', 'clave3']
valor_inicial = 0
diccionario = dict.fromkeys(claves, valor_inicial)
print(diccionario)  # Salida: {'clave1': 0, 'clave2': 0, 'clave3': 0}
```

---

**Con un diccionario existente:** Puedes crear una copia de un diccionario existente utilizando la función `dict()`.

```python
diccionario_existente = {'clave1': 1, 'clave2': 2, 'clave3': 3}
nuevo_diccionario = dict(diccionario_existente)
print(nuevo_diccionario)  # Salida: {'clave1': 1, 'clave2': 2, 'clave3': 3}
```


### 5.1.1. Crear diccionario a partir de secuencia de claves .`fromkeys()`

Este método se utiliza para crear un nuevo diccionario a partir de una secuencia de claves, donde cada clave tiene un valor inicial opcional. La sintaxis es la siguiente:

```python
diccionario = dict.fromkeys(secuencia, valor_inicial)

```

Donde `secuencia` es una secuencia iterable (como una lista, tupla o rango) que contiene las claves del nuevo diccionario, y `valor_inicial` es el valor inicial que se asignará a cada clave en el nuevo diccionario (por defecto es `None` si no se proporciona).

```python
claves = ['a', 'b', 'c']
valor_inicial = 0
nuevo_diccionario = dict.fromkeys(claves, valor_inicial)
print(nuevo_diccionario)  # Salida: {'a': 0, 'b': 0, 'c': 0}

```


**Asignación de valores a claves específicas:** Puedes asignar valores a claves específicas en un diccionario utilizando la sintaxis `diccionario[clave] = valor`. Esto te permite establecer valores específicos para cada clave en el diccionario:

```python
diccionario = {}
diccionario['clave1'] = 10
diccionario['clave2'] = 20
print(diccionario)  # Salida: {'clave1': 10, 'clave2': 20}

```


**Asignación de un valor fijo a cada clave:** Si deseas asignar un valor fijo a cada clave en un diccionario, puedes hacerlo utilizando un bucle `for` o el método `fromkeys()` con un valor inicial. Por ejemplo:

```python
claves = ['a', 'b', 'c']
valor_inicial = 0
nuevo_diccionario = dict.fromkeys(claves, valor_inicial)
print(nuevo_diccionario)  # Salida: {'a': 0, 'b': 0, 'c': 0}

```

Esto creará un nuevo diccionario donde cada clave (`'a'`, `'b'` y `'c'`) tendrá el valor inicial de `0`.


## 5.2. Modificar diccionarios

### Añadir un elemento a un diccionario

Agregar un elemento al diccionario se realiza utilizando una nueva clave de índice y asignándole un valor:

```python
thisdict = {  
  "brand": "Ford",  
  "model": "Mustang",  
  "year": 1964  
}  
thisdict["color"] = "red"  
print(thisdict)
```

### 5.2.1. Modificar valores de un diccionario

Se puede modificar el valor de una propiedad accediendo a su clave y asignando un nuevo valor.

```python
persona["nombre"] = "madeval"
persona["calificaciones"][2] = 10
```

El método `update()`  actualizará el diccionario con los elementos de un dado argumento. Si el elemento no existe, se agregará el elemento.

El argumento debe ser un diccionario o un objeto iterable con pares clave:value.

```python
thisdict = {  
  "brand": "Ford",  
  "model": "Mustang",  
  "year": 1964  
}  
thisdict.update({"year": 2020})
```

### 5.2.2. Eliminar una propiedad del diccionario

`del()` puede eliminar el elemento especificado con su clave:

```python
del persona["edad"]
```

También puede eliminar el diccionario directamente

```python
thisdict = {  
  "brand": "Ford",  
  "model": "Mustang",  
  "year": 1964  
}  
del thisdict
print(thisdict) #this will cause an error because "thisdict" no longer exists.
```

`clear()` vacía el diccionario, pero no lo elimina.

```python
thisdict = {  
  "brand": "Ford",  
  "model": "Mustang",  
  "year": 1964  
}  
thisdict.clear()  
print(thisdict)
```

### 5.2.3. Extraer una propiedad del diccionario y eliminarla

`pop()` para extraer y eliminar una propiedad a la vez. `popitem()` elimina el último elemento insertado

```python
es_estudiante = persona.pop("es_estudiante") #` pop() elimina el elemento con el nombre de clave especificado:
print(f"es_estudiante: {es_estudiante}")
```



## 5.3. Combinar diccionarios

Puedes combinar dos diccionarios utilizando el método `update()`.

Ejemplo: Combinación de dos diccionarios

```python
# Sobreescribir un diccionario con otro diccionario
a = { "name": "miduev", "age": 25 }
b = { "name": "madeval", "es_estudiante": True }

a.update(b)
print(a)
```

Este código sobrescribe el diccionario `a` con los valores de `b`. Si hay claves comunes, sus valores serán actualizados.


## 5.4. Comprobar la existencia de una clave

Es posible verificar si una clave existe en un diccionario utilizando la sintaxis `"clave" in diccionario`.

Ejemplo: Comprobar la existencia de una clave

```python
thisdict = {  
  "brand": "Ford",  
  "model": "Mustang",  
  "year": 1964  
}  
if "model" in thisdict:  
  print("Yes, 'model' is one of the keys in the thisdict dictionary")
```

## 5.5. Obtener claves, valores e items

Python proporciona métodos para obtener todas las claves, todos los valores o ambos de un diccionario.

Ejemplo: Obtener claves, valores e items

```python
# Obtener todas las claves
print("
keys:")
print(persona.keys())

# Obtener todos los valores
print("
values:")
print(persona.values())

# Obtener tanto claves como valores
print("
items:")
print(persona.items())
```

- **`keys()`** devuelve todas las claves del diccionario.
- **`values()`** devuelve todos los valores del diccionario.
- **`items()`** devuelve tanto las claves como los valores como tuplas.

También se puede conseguir el valor **de una clave** con el método “`get()`”

```python
thisdict = {  
  "brand": "Ford",  
  "model": "Mustang",  
  "year": 1964  
}

x = thisdict.get("model")
```

## 5.6. Iterar sobre un diccionario

Para iterar sobre un diccionario hay varias formas:

Puedes usar el método `items()`:

```python
# Iterar sobre el diccionario
for x, y in thisdict.items():  
  print(x, y)
```

Puedes usar el método `keys()`:

```python
for x in thisdict.keys():  
  print(x)
```
Puedes usar el método `values()`:

```python
for x in thisdict.values():  
  print(x)
```

Puedes imprimir todos los valores del diccionario, uno por uno:

```python
for x in thisdict:  
  print(thisdict[x])
```

Puedes imprimir todas las claves del diccionario, uno por uno:

```python
for x in thisdict:  
  print(x)
```


## Copiar un diccionario

No puede copiar un diccionario simplemente escribiendo `dict2 = dict1`, porque: `dict2` sólo será un _referencia_ a `dict1`y cambios realizados en `dict1` también se hará automáticamente en `dict2`.

Hay formas de hacer una copia, una forma es usar el Diccionario incorporado método `copy()`.

```python
thisdict = {  
  "brand": "Ford",  
  "model": "Mustang",  
  "year": 1964  
}  
mydict = thisdict.copy()  
print(mydict)
```

Otra forma de hacer una copia es usar la función incorporada `dict()`.

```python
thisdict = {  
  "brand": "Ford",  
  "model": "Mustang",  
  "year": 1964  
}  
mydict = dict(thisdict)  
print(mydict)
```

## Anidado de diccionarios

Un diccionario puede contener diccionarios, esto se llama anidado diccionarios.

```python
# Crear un diccionario que contenga tres diccionarios:

myfamily = {  
  "child1" : {  
    "name" : "Emil",  
    "year" : 2004  
  },  
  "child2" : {  
    "name" : "Tobias",  
    "year" : 2007  
  },  
  "child3" : {  
    "name" : "Linus",  
    "year" : 2011  
  }  
}
```

O, si desea agregar tres diccionarios a un nuevo diccionario:



```python
# Cree tres diccionarios, luego cree un diccionario que contenga el otros tres diccionarios:

child1 = {  
  "name" : "Emil",  
  "year" : 2004  
}  
child2 = {  
  "name" : "Tobias",  
  "year" : 2007  
}  
child3 = {  
  "name" : "Linus",  
  "year" : 2011  
}  
  
myfamily = {  
  "child1" : child1,  
  "child2" : child2,  
  "child3" : child3  
}
```


> [!tip] Para acceder a los elementos de un diccionario anidado, utiliza el nombre de los diccionarios, comenzando con el diccionario externo:
> ```python
> Imprima el nombre del niño 2:
> 
> print(myfamily["child2"]["name"])
> ```

Puede recorrer un diccionario utilizando el `items()` método como este:

Recorre las claves y valores de todos los diccionarios anidados:

```python
for x, obj in myfamily.items():  
  print(x)  
  
  for y in obj:  
    print(y + ':', obj[y])
```

	child1
	name: Emil
	year: 2004
	child2
	name: Tobias
	year: 2007
	child3
	name: Linus
	year: 2011

# 6. Consideraciones

> [!info] Ver [[#^16e405|Tabla de características de los 4 tipos de datos]]

El prefijo `dict`, `tuple`, `list`, etc., seguido de un punto, se refiere a la clase del tipo de dato en Python. Cuando lo utilizas seguido de un punto, estás accediendo a un método o atributo de esa clase.

Por ejemplo:

- `dict.fromkeys(claves, valor_inicial)`: `dict` es la clase de los diccionarios en Python. Aquí, `fromkeys()` es un método de la clase `dict` que se utiliza para crear un nuevo diccionario a partir de una secuencia de claves.
- `tuple.count(valor)`: `tuple` es la clase de las tuplas en Python. Aquí, `count()` es un método de la clase `tuple` que se utiliza para contar el número de veces que aparece un valor en una tupla.
- `list.append(elemento)`: `list` es la clase de las listas en Python. Aquí, `append()` es un método de la clase `list` que se utiliza para agregar un elemento al final de la lista.

En resumen, cuando ves algo como `clase.metodo()` o `clase.atributo`, significa que estás utilizando un método o atributo específico de esa clase de datos en Python. Esto te permite realizar operaciones específicas o acceder a información sobre ese tipo de datos.




[^1]: Con el bucle for se utilizan la función `range()` y `len()`, para el while solo el `len()`. Esto aplica también para las listas

[^2]: The `&` operator only allows you to join sets with sets, and not with other data types like you can with the `intersection()` method.

[^3]: El `-` el operador solo le permite unir conjuntos con conjuntos, y no con otros tipos de datos

[^4]: El `^` el operador solo le permite unir conjuntos con conjuntos, y no con otros tipos de datos

[^5]: Ordenado significa que se puede consultar un elemento utilizando un índice. Si el tipo de dato no está ordenado, no se va a poder consultar un elemento utilizando su índice.


