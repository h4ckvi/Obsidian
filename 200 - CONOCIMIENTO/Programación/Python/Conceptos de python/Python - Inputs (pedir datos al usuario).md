---
aliases: 
link: 
tags: 
categoria:
  - Manipulación de datos
subcategoria:
---

Es una función que nos permite pedirle un dato al usuario, así de sencillo.

> [!important] Input SIEMPRE nos devuelve un tipo *texto*

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












