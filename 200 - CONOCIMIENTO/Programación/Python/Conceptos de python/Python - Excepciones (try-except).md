---
aliases: 
tags:
  - Programación
categoria:
  - Manejo de errores y depuración
subcategoria: 
nivel:
---

Ver [[nota SILO correspondiente]]
Ver [[MOC correspondiente]]

# Manejo de errores en python

- El bloque `try` permite comprobar si hay errores en un bloque de código.

- El bloque `except` permite gestionar el error.

- El bloque `else` permite ejecutar código cuando no hay error.

- El bloque `finally` permite ejecutar código, independientemente del resultado de los bloques try y except.

## Bloques try y except

Cuando se produce un error, o excepción como lo llamamos, Python normalmente se detendrá y generará un mensaje de error.

Estas excepciones pueden ser manejadas usando la sentencia try:

```python
# Manejo de errores al pedir un número positivo
numero = -1

while numero < 0:
  try:
      numero = int(input("Escribe un número positivo: "))
      if numero < 0:
          print("El número debe ser positivo. Intenta otra vez.")
  except ValueError:
      print("Lo que introduces debe ser un número válido.")

print(f"El número que has introducido es {numero}")
```

Dado que el bloque try produce un error, se ejecutará el bloque except.

Sin el bloque try, el programa se bloqueará y generará un error:

```python
try:
  print(x)
except:
  print("An exception occurred")
```

	An exception occurred

---

```python
print(x)
```

	#This will raise an exception, because x is not defined:
	​
	print(x)
	​
	Traceback (most recent call last):
	  File "demo_try_except_error.py", line 3, in <module>
	    print(x)
	NameError: name 'x' is not defined

## Bloque else

`else` Se usa par definir un código personalizado si no se han encontrado errores.

```python
# En este ejemplo, try no genera ningún error

try:  
  print("Hello")  
except:  
  print("Something went wrong")  
else:  
  print("Nothing went wrong")
```

	Hello  
	Nothing went wrong



## Bloque finally

El bloque finally, si se especifica, se ejecutará independientemente de si el bloque try genera un error o no.

```python
try:  
  print(x)  
except:  
  print("Something went wrong")  
finally:  
  print("The 'try except' is finished")
```

	Something went wrong  
	The 'try except' is finished

Esto puede ser útil para cerrar objetos y limpiar recursos:

```python
# Intenta abrir y escribir en un archivo que no es escribible

try:  
  f = open("demofile.txt")  
  try:  
    f.write("Lorum Ipsum")  
  except:  
    print("Something went wrong when writing to the file")  
  finally:  
    f.close()  
except:  
  print("Something went wrong when opening the file")
```

	El programa puede continuar, sin dejar abierto el objeto de archivo.

# Provocar errores con raise

La palabra clave `raise` se utiliza para lanzar una excepción.

Puede definir el tipo de error que se producirá y el texto que se mostrará al usuario.

```python
# Genera un error y detiene el programa si x es menor que 0:
x = -1

if x < 0:
  raise Exception("Sorry, no numbers below zero")
```

```
Traceback (most recent call last):  
  File "demo_ref_keyword_raise.py", line 4, in <module>  
    raise Exception("Sorry, no numbers below zero")  
Exception: Sorry, no numbers below zero
```

---

```python
x = "hello"

if not type(x) is int:
  raise TypeError("Only integers are allowed")

# También se puede escribir así:
if type(x) is not int:

# Y también, de forma más flexible y profesional: 
if not isinstance(x, int):  # más flexible y profesional
```

```  
Traceback (most recent call last):  
  File "demo_ref_keyword_raise2.py", line 4, in <module>  
    raise TypeError("Only integers are allowed")  
TypeError: Only integers are allowed
```

# La importancia de controlar los errores

Es recomendable envolver el código en un bloque `try-except` para manejar posibles errores durante la petición. Esto previene que tu programa se rompa en caso de que la URL sea incorrecta o haya otros problemas:

Manejo de Errores

```python
try:
	response = urllib.request.urlopen(url)
except urllib.error.HTTPError as e:
	    print(f'Error en la solicitud: {e.code}')
except urllib.error.URLError as e:
	    print(f'Error en la URL: {e.reason}')
```

# 


# Tabla de excepciones (errores) en python

La siguiente tabla muestra las excepciones incorporadas que suelen aparecer en Python:

| Exception             | Description                                                                       |
|-----------------------|-----------------------------------------------------------------------------------|
| ArithmeticError       | Raised when an error occurs in numeric calculations                               |
| AssertionError        | Raised when an assert statement fails                                             |
| AttributeError        | Raised when attribute reference or assignment fails                               |
| Exception             | Base class for all exceptions                                                     |
| EOFError              | Raised when the input() method hits an "end of file" condition (EOF)              |
| FloatingPointError    | Raised when a floating point calculation fails                                    |
| GeneratorExit         | Raised when a generator is closed (with the close() method)                       |
| ImportError           | Raised when an imported module does not exist                                     |
| IndentationError      | Raised when indentation is not correct                                            |
| IndexError            | Raised when an index of a sequence does not exist                                 |
| KeyError              | Raised when a key does not exist in a dictionary                                  |
| KeyboardInterrupt     | Raised when the user presses Ctrl+c, Ctrl+z or Delete                             |
| LookupError           | Raised when errors raised cant be found                                           |
| MemoryError           | Raised when a program runs out of memory                                          |
| NameError             | Raised when a variable does not exist                                             |
| NotImplementedError   | Raised when an abstract method requires an inherited class to override the method |
| OSError               | Raised when a system related operation causes an error                            |
| OverflowError         | Raised when the result of a numeric calculation is too large                      |
| ReferenceError        | Raised when a weak reference object does not exist                                |
| RuntimeError          | Raised when an error occurs that do not belong to any specific exceptions         |
| StopIteration         | Raised when the next() method of an iterator has no further values                |
| SyntaxError           | Raised when a syntax error occurs                                                 |
| TabError              | Raised when indentation consists of tabs or spaces                                |
| SystemError           | Raised when a system error occurs                                                 |
| SystemExit            | Raised when the sys.exit() function is called                                     |
| TypeError             | Raised when two different types are combined                                      |
| UnboundLocalError     | Raised when a local variable is referenced before assignment                      |
| UnicodeError          | Raised when a unicode problem occurs                                              |
| UnicodeEncodeError    | Raised when a unicode encoding problem occurs                                     |
| UnicodeDecodeError    | Raised when a unicode decoding problem occurs                                     |
| UnicodeTranslateError | Raised when a unicode translation problem occurs                                  |
| ValueError            | Raised when there is a wrong value in a specified data type                       |
| ZeroDivisionError     | Raised when the second operator in a division is zero                             |



