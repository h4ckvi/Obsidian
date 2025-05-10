---
aliases: 
link: 
tags:
  - cursopython
  - datossimples
categoria:
  - Fundamentos de Python
subcategoria:
---

| Tipo                | Valor                        |
| ------------------- | ---------------------------- |
| Tipo de Texto:      | str                          |
| Tipos Numéricos:    | int, float, complex          |
| Tipos de Secuencia: | list, tuple, range           |
| Tipo de Mapeo:      | dict                         |
| Establecer Tipos:   | set, frozenset               |
| Tipo Booleano:      | bool                         |
| Tipos Binarios:     | bytes, bytearray, memoryview |
| Ninguno Tipo:       | NoneType                     |


| x = "Hello World"                            | str        |
| -------------------------------------------- | ---------- |
| x = 20                                       | int        |
| x = 20.5                                     | float      |
| x = 1j                                       | complex    |
| x = ["apple", "banana", "cherry"]            | list       |
| x = ("apple", "banana", "cherry")            | tuple      |
| x = range(6)                                 | range      |
| x = {"name" : "John", "age" : 36}            | dict       |
| x = {"apple", "banana", "cherry"}            | set        |
| x = frozenset({"apple", "banana", "cherry"}) | frozenset  |
| x = True                                     | bool       |
| x = b"Hello"                                 | bytes      |
| x = bytearray(5)                             | bytearray  |
| x = memoryview(bytes(5))                     | memoryview |
| x = None                                     | NoneType   |


Los comentarios en Python comienzan con `#` . **No soporta** comentarios multilínea, cada línea de un bloque de comentarios tiene que empezar por `#`.

# Conceptos generales sobre tipos de datos

## Datos compuestos:

Datos que tienen dentro otros datos y que podemos agrupar.

## Matriz de datos:

Es un conjunto de datos, una lista sería una matriz

## Métodos:

Un método es una función que está asociada a un objeto específico en la programación orientada a objetos. Los métodos se llaman utilizando la sintaxis `objeto.metodo()`. Ejemplo: `lista.append(elemento)` donde `append()` es un método asociado a la clase `list`.

## Funciones:

- **Funciones incorporadas (built-in functions)**:   Son funciones que vienen predefinidas en Python y están disponibles para su uso sin necesidad de importar ningún módulo adicional. Ejemplos comunes incluyen `print()`, `len()`, `range()`, entre otros. </p>

- **Funciones definidas por el usuario**:  Son funciones que defines tú mismo en tu programa para realizar tareas específicas. Se definen utilizando la palabra clave `def` seguida del nombre de la función y su cuerpo. Por ejemplo: </p>

- **Funciones anónimas (lambda functions)**:  Son funciones pequeñas y anónimas que se definen sin un nombre utilizando la palabra clave `lambda`. Son útiles para operaciones simples y se utilizan principalmente en combinación con funciones de orden superior (como `map()`, `filter()`, `sorted()`, etc.).</p>

- **Funciones recursivas:** Son funciones que se llaman a sí mismas durante su ejecución. Se utilizan para resolver problemas que se pueden dividir en subproblemas más pequeños. Por ejemplo, la función factorial se puede definir de forma recursiva:</p>
 
- **Funciones de generador (generator functions)**:  Son funciones que contienen una o más expresiones `yield` y devuelven un iterador (un generador) en lugar de un solo valor. Permiten iterar sobre un conjunto de valores de forma eficiente. Por ejemplo:</p>

- **Atributos: **
  
  Un atributo es una variable asociada a un objeto que almacena datos específicos sobre ese objeto. Se accede utilizando la sintaxis `objeto.atributo`. Ejemplo: `cadena.length` donde `length` es un atributo que almacena la longitud de la cadena de caracteres </p>


# Cadenas de texto o strings  (`str`)

Las cadenas de texto (`str`) se utilizan para representar texto. Estas pueden ser simples, vacías, numéricas o incluso multilínea.


```python
print(type("Hola"))  # str
print(type(""))  # str
print(type("123"))  # str
print(type(""" 
Multilinea 
"""))  # str
```

Tenemos cadenas simples y complejas, dependiendo de si queremos crear strings de una línea o de varias.

```python
"string" # Cadena de texto simple, para una sola línea
'string' # Cadena de texto simple, para una sola línea

"""tus datos son:
        nombre: Alvaro
        apellido: Tejada""" # Cadena de texto compleja, para strings de más de una línea

'''tus datos son:
        nombre: Alvaro
        apellido: Tejada''' # Cadena de texto compleja, para strings de más de una línea
```

## Cómo escapar caracteres inválidos en una string

Con la barra invertida + caractger que queremos mostrar sin compilar.

```python
txt = "We are the so-called \"Vikings\" from the north."
```

Otros caracteres de escape usados:

| Code | Result          |
| ---- | --------------- |
| \'   | Single Quote    |
| \\   | Backslash       |
| \n   | New Line        |
| \r   | Carriage Return |
| \t   | Tab             |
| \b   | Backspace       |
| \f   | Form Feed       |
| \ooo | Octal value     |
| \xhh | Hex value       |


# Numeros enteros (`int`)

El tipo `int` se utiliza para representar números enteros, positivos, negativos o incluso valores extremadamente grandes.


```python
print(type(10))  # int
print(type(0))   # int
print(type(-5))  # int
print(type(7238424723784278934789239874))  # int
```

# Numeros flotantes con decimales (`float`)

Los números con decimales o en notación científica se representan con el tipo `float`.


```python
print(type(3.14))  # float
print(type(1.0))   # float
print(type(1e3))   # float, notación científica
```

# Booleanos (`bool`)

Los valores `True` y `False` pertenecen al tipo `bool`, útil para trabajar con lógica booleana.


```python
print(type(True))  # bool
print(type(False))  # bool
print(type(1 < 2))  # bool
```

> [!NOTE] Casi cualquier valor es evaluado para `True` si es así tiene algún tipo de contenido.
> 
> - Cualquier cadena es `True`, excepto las cadenas vacías.
> 
> - Cualquier número es `True`, excepto `0`.
> 
> - Cualquier lista, tupla, conjunto y diccionario son `True`, excepto vacíos.
> 
> ```python
> bool("abc")  
> bool(123)  
> bool(["apple", "cherry", "banana"])````


> [!NOTE] De hecho, no hay muchos valores que evalúen `False`, excepto valores vacíos, tales como `()`, `[]`, `{}`, `""`, el número `0`, y el valor `None`. Y por supuesto el valor `False` evalúa a `False`.
> ```python
> bool(False)  # False
> bool(None)  # False
> bool(0)  # False
> bool("")  # False
> bool(()) # False 
> bool([]) # False 
> bool({})# False```



> [!NOTE] Python también tiene muchas funciones integradas que devuelven un valor booleano, como el `isinstance()` función, que se puede utilizar para determinar si un objeto es de un determinado tipo de datos:
> 
> Compruebe si un objeto es un número entero o no:
> 
> ```python
> x = 200  
> print(isinstance(x, int))```


> [!NOTE] Puede ejecutar código basado en la respuesta booleana de una función:
> 
> Imprimir "YES!" si la función devuelve True, imprima "NO!":
> 
> ```python
> def myFunction() :  
>   return True  
>   
> if myFunction():  
>   print("YES!")  
> else:  
>   print("NO!")```

# Números complejos (`complex`)

El tipo `complex` se utiliza para representar números complejos, que tienen una parte real y una imaginaria.

```python
print(type(1 + 2j))  # complex
```

# Sin ningún valor (`NoneType`)

El tipo `NoneType` tiene un único valor, `None`, que representa la ausencia de un valor o la nada.

```python
print(type(None))  # NoneType
```


# 💡 Tips y consejos con tipos de datos

- `int()` **trunca** un float, eliminando la parte decimal.
    
- El resultado de convertir `3.99` a entero es `3`.
    
- Si necesitas redondear, puedes usar `round()`.


> [!faq]- ¿Cómo ver una lista de todos los atributos válidos para el objeto que estamos pasando?
> Con la función `DIR`
>> [!example]- Ejemplos:
>> ```pthon
>> 
>> dir(str) 
>> 
>> ['__add__', '__class__', '__contains__', '__delattr__', '__dir__', '__doc__', '__eq__', '__format__', '__ge__', '__getattribute__', '__getitem__', '__getnewargs__', '__getstate__', '__gt__', '__hash__', '__init__', '__init_subclass__', '__iter__', '__le__', '__len__', '__lt__', '__mod__', '__mul__', '__ne__', '__new__', '__reduce__', '__reduce_ex__', '__repr__', '__rmod__', '__rmul__', '__setattr__', '__sizeof__', '__str__', '__subclasshook__', 'capitalize', 'casefold', 'center', 'count', 'encode', 'endswith', 'expandtabs', 'find', 'format', 'format_map', 'index', 'isalnum', 'isalpha', 'isascii', 'isdecimal', 'isdigit', 'isidentifier', 'islower', 'isnumeric', 'isprintable', 'isspace', 'istitle', 'isupper', 'join', 'ljust', 'lower', 'lstrip', 'maketrans', 'partition', 'removeprefix', 'removesuffix', 'replace', 'rfind', 'rindex', 'rjust', 'rpartition', 'rsplit', 'rstrip', 'split', 'splitlines', 'startswith', 'strip', 'swapcase', 'title', 'translate', 'upper', 'zfill']
>> 
>> dir(tuple) 
>> 
>> ['__add__', '__class__', '__class_getitem__', '__contains__', '__delattr__', '__dir__', '__doc__', '__eq__', '__format__', '__ge__', '__getattribute__', '__getitem__', '__getnewargs__', '__getstate__', '__gt__', '__hash__', '__init__', '__init_subclass__', '__iter__', '__le__', '__len__', '__lt__', '__mul__', '__ne__', '__new__', '__reduce__', '__reduce_ex__', '__repr__', '__rmul__', '__setattr__', '__sizeof__', '__str__', '__subclasshook__', 'count', 'index']
>> 
>> dir(()) 
>> 
>>['__add__', '__class__', '__class_getitem__', '__contains__', '__delattr__', '__dir__', '__doc__', '__eq__', '__format__', '__ge__', '__getattribute__', '__getitem__', '__getnewargs__', '__getstate__', '__gt__', '__hash__', '__init__', '__init_subclass__', '__iter__', '__le__', '__len__', '__lt__', '__mul__', '__ne__', '__new__', '__reduce__', '__reduce_ex__', '__repr__', '__rmul__', '__setattr__', '__sizeof__', '__str__', '__subclasshook__', 'count', 'index']
>> ```

> [!faq]- ¿Cómo saber el tipo de dato con una función?
> 
> ```python
> tipo_de_dato = type(5)
> tipo_de_dato2 = type(“Hola maestro”)
> tipo_de_dato3 = type([1,”Hola”])
> tipo_de_dato4 = type((“Que tal”, “25.0”, True))
> print(tipo_de_dato, tipo_de_dato2, tipo_de_dato3, tipo_de_dato4)
> ```### 