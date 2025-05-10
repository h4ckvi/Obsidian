---
aliases: 
link: 
tags: 
categoria:
  - Manipulación de datos
subcategoria:
---

| Method       | Description                                                                                                 |
|--------------|-------------------------------------------------------------------------------------------------------------|
| clear()      | Removes all the elements from the dictionary                                                                |
| copy()       | Returns a copy of the dictionary                                                                            |
| fromkeys()   | Returns a dictionary with the specified keys and value                                                      |
| get()        | Returns the value of the specified key                                                                      |
| items()      | Returns a list containing a tuple for each key value pair                                                   |
| keys()       | Returns a list containing the dictionary's keys                                                             |
| pop()        | Removes the element with the specified key                                                                  |
| popitem()    | Removes the last inserted key-value pair                                                                    |
| setdefault() | Returns the value of the specified key. If the key does not exist: insert the key, with the specified value |
| update()     | Updates the dictionary with the specified key-value pairs                                                   |
| values()     | Returns a list of all the values in the dictionary                                                          |


# keys()

Nos devuelve un objeto *”dict_item”*

```python
diccionario = {
    "nombre" : "Alvaro",
    "apellido" : "Tejada Rodriguez",
    "subs" : 4500
}

claves = diccionario.keys() # Devuelve las llaves del diccionario en forma de lista

print(claves)
```

# get()

Si no le pasamos el `.get()` nos dará un error y bloqueará el programa, al pasárselo nos devolverá un *“none”* y el programa continua.

Si la llave no tiene valor, parecido al *undefined* de javascript

```python
diccionario = {
    "nombre" : "Alvaro",
    "apellido" : "Tejada Rodriguez",
    "subs" : 4500
}

claves = diccionario.get("nombre") # Devuelve el valor de la clave que le pasamos

print(claves)
```
# clear()

```python
diccionario = {
    "nombre" : "Alvaro",
    "apellido" : "Tejada Rodriguez",
    "subs" : 4500
}

# Eliminando todo el diccionario

claves = diccionario.clear() 
print(claves)
```

# pop()

```python
diccionario = {
    "nombre" : "Alvaro",
    "apellido" : "Tejada",
    "subs" : 4500
}

# Eliminando un elemento del diccionario

diccionario.pop("apellido")
print(diccionario)
```

# items()

Los items de un diccionario son iterables siempre que usemos el método *”items*.

```python
diccionario = {
    "nombre" : "Alvaro",
    "apellido" : "Tejada",
    "subs" : 4500
}

# Obteniendo un elemento dict_items iterable
# Este sí es iterable, de la otra forma NO

diccionario_iterable = diccionario.items()
print(diccionario_iterable)
```
