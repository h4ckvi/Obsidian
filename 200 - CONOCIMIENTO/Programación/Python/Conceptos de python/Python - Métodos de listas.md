---
aliases: 
link: 
tags: 
categoria:
  - Manipulación de datos
subcategoria:
---

| Method                                                             | Description                                                                  |
| ------------------------------------------------------------------ | ---------------------------------------------------------------------------- |
| [append()](https://www.w3schools.com/python/ref_list_append.asp)   | Adds an element at the end of the list                                       |
| [clear()](https://www.w3schools.com/python/ref_list_clear.asp)     | Removes all the elements from the list                                       |
| [copy()](https://www.w3schools.com/python/ref_list_copy.asp)       | Returns a copy of the list                                                   |
| [count()](https://www.w3schools.com/python/ref_list_count.asp)     | Returns the number of elements with the specified value                      |
| [extend()](https://www.w3schools.com/python/ref_list_extend.asp)   | Add the elements of a list (or any iterable), to the end of the current list |
| [index()](https://www.w3schools.com/python/ref_list_index.asp)     | Returns the index of the first element with the specified value              |
| [insert()](https://www.w3schools.com/python/ref_list_insert.asp)   | Adds an element at the specified position                                    |
| [pop()](https://www.w3schools.com/python/ref_list_pop.asp)         | Removes the element at the specified position                                |
| [remove()](https://www.w3schools.com/python/ref_list_remove.asp)   | Removes the item with the specified value                                    |
| [reverse()](https://www.w3schools.com/python/ref_list_reverse.asp) | Reverses the order of the list                                               |
| [sort()](https://www.w3schools.com/python/ref_list_sort.asp)       | Sorts the list                                                               |

# 1. LIST()

```python
# Creando una lista a través de una tupla

lista = list(["Hola", "Alvaro", 26])
print(type(lista))
```

# 2. LEN()

```python
# Cuando se trata de listas, la función `len` devuelve la cantidad de elementos

lista = ("Buenas", 1.34, "Álvaro", 45)
print(len(lista))
```

# 3. APPEND(), INSERT() Y EXTEND()

```python
lista = ["Buenas", 1.34, "Álvaro", 45]

# Agregando un elemento a la lista, al final

lista.append("jajaj")
print(lista)

# Agregando un elemento a la lista en un elemento concreto

lista.insert(2,"Que tal")
print(lista)

# Agregando varios elementos a la lista (agregar una lista a una lista)
# Si queremos agregar solo uno utilizaríamos append

lista.extend(['que cojones', 55555, True])
print(lista)

# Usa el `extend()` método para agregar list2 al final de list1:

list1 = ["a", "b" , "c"]  
list2 = [1, 2, 3]  
  
list1.extend(list2)  
print(list1)

# Concatena listas. 

nums = [1, 2, 3]
nums + [4, 5] # es [1, 2, 3, 4, 5]

```


> [!info] Como puedes ver, `+` no modifica `nums`, pero `append` sí.


# 4. POP(), REMOVE() Y CLEAR()

```python

lista = ["Buenas", 1.34, "Álvaro", 45]

# Eliminar un elemento de la lista por su índice

lista.pop(2) # Elimina el elemento de índice 2
print(lista)
lista.pop(-1) # Elimina el último elemento. Es el utilizado por defecto en lista.pop()
print(lista)
lista.pop(-2) # Elimina el penúltimo elemento
print(lista)


# Remover un elemento de la lista por su VALOR. Elimina el primnero que encuentra, no todos.  

lista = ["Buenas", 1.34, "Álvaro", 45]
 
lista.remove(1.34)
print(lista)

# Eliminar TODOS los elementos de la lista

lista = ["Buenas", 1.34, "Álvaro", 45]

lista.clear()
print(lista)


```


> [!warning] OJO con la diferencia entre pop y remove, uno es para eliminar por índice y el otro por el valor en sí



# 5. SORT() Y REVERSE()

• `sort()`: Es un `método` de listas que las modifica en su lugar. No devuelve nada (None).

• `sorted()`: Es una `función` que devuelve una nueva lista ordenada sin modificar la original.

```python
# Ordenar la lista de manera ascentente (si le ponemos el parámetro reverse=true lo ordena al revés, aunque no esté ordenado lo pone al revés)
# Lo que menos vale son los False, luego los True, y después empieza a ordenar los números


lista = [12.5, 45, 23, 195, True, False, False]
lista.sort() 

print(lista)

lista.reverse() 
print(lista)

# Nos va a dar un error porque las cadenas "str" no se pueden ordenar

lista = ["Buenas", 1.34, "Álvaro", 45]
lista.sort()

print(lista) 

frutas = ["naranja", "Manzana", "pera", "plátano"]
frutas.sort()  # Modifica la lista original

print(frutas)  # ['Manzana', 'naranja', 'pera', 'plátano']

# Utilización de sorted().

frutas2 = ["naranja", "Manzana", "pera", "plátano"]
nueva_lista = sorted(frutas2)  # Devuelve una nueva lista ordenada

print(nueva_lista)  # ['Manzana', 'naranja', 'pera', 'plátano']
print(frutas2)  # La original sigue igual

# Ordenar sin diferenciar mayúsculas o minúsculas
# Por defecto, Python ordena primero las mayúsculas y luego las minúsculas según la tabla ASCII. Para evitarlo, usa key=str.lower:

frutas = ["naranja", "Manzana", "pera", "plátano"]
frutas.sort(key=str.lower)  # Modifica la lista original

print(frutas)  # ['Manzana', 'naranja', 'pera', 'plátano']

# Esto convierte temporalmente las palabras a minúsculas solo para comparar, sin modificar la lista real.

frutas2 = ["naranja", "Manzana", "pera", "plátano"]
nueva_lista = sorted(frutas2, key=str.lower)  # Crea una nueva lista ordenada

print(nueva_lista)  # ['Manzana', 'naranja', 'pera', 'plátano']


thislist = [100, 50, 65, 82, 23]  
thislist.sort(reverse = True)  

print(thislist)
```


## 5.1. 🔑  Funciones clave (key) para ordenar:

Cuando usas .sort() o sorted() en una lista, **Python ordena por defecto los valores “tal cual” están**.

Pero a veces quieres **ordenar usando una lógica especial**, no el valor directo. Ahí entra el parámetro key=, donde puedes decirle a Python:

> “Ordena según este criterio que yo te doy en forma de función”

--- start-multi-column: ID_6vas

```column-settings
Number of Columns: 2
Largest Column: standard
```


```python
thislist = ["banana", "Orange", "Kiwi", "cherry"]
thislist.sort(key=str.lower)
```

🔎 ¿Qué pasa aquí?

• Sin key=str.lower, se ordena por mayúsculas primero (como hace el alfabeto en ASCII).

• Con key=str.lower, le dices:

> “Ordena cada palabra como si todas fueran minúsculas”.

➡️ Así evitas que "Orange" vaya antes que "banana" solo por ser mayúscula.


--- column-break ---

```python
def myfunc(n):
  return abs(n - 50)

thislist = [100, 50, 65, 82, 23]
thislist.sort(key=myfunc)
```

🔎 ¿Qué pasa aquí?

• key=myfunc le dice a .sort():

> “Ordena los números según lo que devuelva myfunc(n)”.  

Y myfunc(n) devuelve **la distancia a 50** (abs(n - 50)).  

Entonces, el número más cercano a 50 es el primero, y el más lejano el último.


--- end-multi-column




# 6. INDEX()


**`index`**: Devuelve el primer índice de un valor en una lista utilizando la sintaxis

```python
alguna_lista.index(valor)
```

Genera un error si el valor no está ahí. Por ejemplo, ejecute esta línea en la ventana de comandos:

```python
[7, 8, 9, 8].index(8)
```

# 7. COUNT()

**`count`**: Devuelve el número de veces que el argumento aparece en la lista utilizando la sintaxis

```python
alguna_lista.count(valor)
```

Por ejemplo, ejecute esta línea en la ventana de comandos:

```python
[1, 2, 3, 2, 7, 2, 5].count(2)
```

Usa la palabra clave `in` para verificar si un elemento existe en la lista.

```python
# Verificar si un elemento está en la lista
animals = ['🐶', '🐼', '🐨', '🐶']
print('🐼' in animals)  # -> True
print('🐹' in animals)  # -> False
```

---

# 8. AMPLIACIÓN DE CONCEPTOS Y TIPS PARA LISTAS

> [!tip]- Tips: Trabajar con el último elemento de la lista
> trabajar con el último elemento mediante `x[len(x) - 1]` es un poco engorroso. Lo mismo se puede conseguir con `x[-1]`. Del mismo modo, el penúltimo elemento `x[len(x) - 2]` puede escribirse como `x[-2]`, y así sucesivamente. Python también nos permite contar el índice hacia atrás, empezando por el último elemento con `-1`:
> 
> | Indice         | Primer ítem | Segundo ítem  | Tercer ítem   | ... | Anteúltimo ítem | Último ítem  |
> | -------------- | ----------- | ------------- | ------------- | --- | --------------- | ------------ |
> | Hacia adelante | `0`         | `1`           | `2`           | ... | `len(x) - 2`    | `len(x) - 1` |
> | Hacia atrás    | `-len(x)`   | `-len(x) + 1` | `-len(x) + 2` | ... | `-2`            | `-1`         |
> 


> [!tip]- Modificar mientras se itera
> Para reiterar, **_nunca modifiques algo mientras iteras sobre él_**. Tus opciones son:
>
> - Modificar una copia
> - Iterar sobre una copia
> - No modificar nada y hacer una nueva versión.