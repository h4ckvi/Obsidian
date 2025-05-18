---
aliases:
  - inputs python
link: 
tags: 
categoria:
  - Manipulación de datos
subcategoria:
---

Es una función que nos permite pedirle un dato al usuario, así de sencillo. 

Python detiene la ejecución cuando llega a la función input(), y continúa cuando el usuario ha dado alguna entrada.

Se permiten tantos inputs como quieras. 

```python
name = input("Enter your name:")  
print(f"Hello {name}")  
fav1 = input("What is your favorite animal:")  
fav2 = input("What is your favorite color:")  
fav3 = input("What is your favorite number:")  
print(f"Do you want a {fav2} {fav1} with {fav3} legs?")
```

> [!note] Input SIEMPRE nos devuelve un tipo *texto*

# Input nombres

```python
# Pedirle un dato al usuario

nombre = input("Ingresa tu nombre: ")

# Mostrando el dato

print(f'el nombre es: {nombre}')
```


# input números

Como la función “input” siempre devuelve tipo texto debemos cambiar a tipo “int” para hacer los cálculos correctamente.

Si sabemos que vamos a trabajar con numeros decimales tenemos que cambiar a tipo “float”, porque si no nos va a dar error.

```python
# Pedirle un número al usuario (recuerda que devuelve un tipo texto)

numero = input("Ingresa tu numero favorito: ")

# Cambiamos a tipo "int" y multiplicamos el número por 2

resultado = int(numero)*2

# Mostrando el resultado

print(resultado)
```

Otro ejemplo: 

```python
x = input("Enter a number:")  
  
#find the square root of the number:  
y = math.sqrt(float(x))  
  
print(f"The square root of {x} is {y}")
```












