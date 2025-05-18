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

# Manejo de errores con `try-except`

- El bloque `try` permite comprobar si hay errores en un bloque de código.

- El bloque `except` permite gestionar el error.

- El bloque `else` permite ejecutar código cuando no hay error.

- El bloque `finally` permite ejecutar código, independientemente del resultado de los bloques try y except.

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


	Result Size: 1075 x 1242
	#This will raise an exception, because x is not defined:
	​
	print(x)
	​
	Traceback (most recent call last):
	  File "demo_try_except_error.py", line 3, in <module>
	    print(x)
	NameError: name 'x' is not defined

# Importancia del Control de Errores

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



