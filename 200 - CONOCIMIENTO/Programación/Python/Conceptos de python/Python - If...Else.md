---
aliases: 
link: 
tags: 
categoria:
  - Control de flujo en python
subcategoria:
---
# if y elif (else if)

Un condicional en programación se utiliza para tomar decisiones basadas en una condición dada. En Python, la estructura básica de un condicional utiliza las palabras clave `if`, `elif` (else if), y `else`.  `elif` es la forma en que Python dice "si las condiciones anteriores no eran ciertas, entonces prueba esta condición".


Aquí está la estructura general:

```python
if condicion_1:
    # Código a ejecutar si condicion_1 es True
elif condicion_2:
    # Código a ejecutar si condicion_1 es False y condicion_2 es True
else:
    # Código a ejecutar si todas las condiciones anteriores son False
```

Ejemplo:

```python
edad = 25

if edad < 18:
    print("Eres menor de edad.")
elif edad >= 18 and edad < 65:
    print("Eres mayor de edad, pero aún no estás jubilado.")
else:
    print("Eres jubilado.")
```

En este ejemplo, el programa evalúa las condiciones en orden. Si la edad es menor de 18, imprime "Eres menor de edad". Si no, verifica si la edad está entre 18 y 65 (inclusive) e imprime "Eres mayor de edad, pero aún no estás jubilado". Si ninguna de estas condiciones es True, imprime "Eres jubilado".

> [!warning] El `else` NO es obligatorio ponerlo, sólo si queremos mostrar algo en caso contrario.


> [!NOTE] Es común tener una cadena de cláusulas `elif` cuando quieres que se ejecute uno de muchos cuerpos, como en este caso. En general, código como este:
> ```python
> if X:
>     ...
> else:
>     if Y:
>         ...
>     else:
>         if Z:
>             ...
>         else:
>             ...
> ```
> puede reescribirse así:
> ```python
> if X:
>     ...
> elif Y:
>     ...
> elif Z:
>     ...
> else:
>     ...
> ```



# if anidado

```python
usuario_autenticado = True
usuario_admin = False

if usuario_autenticado:
    print("Bienvenido a la aplicación.")

    if usuario_admin:
        print("Acceso total concedido. ¡Eres un administrador!")
    else:
        print("Acceso limitado. Eres un usuario estándar.")
else:
    print("Debes iniciar sesión para acceder.")
```

- Verificamos si el usuario está autenticado.
- Si está autenticado, se imprime un mensaje de bienvenida.
    - Luego, se verifica si el usuario es un administrador.
        - Si es un administrador, se imprime un mensaje especial.
        - Si no es un administrador, se imprime un mensaje para un usuario estándar.
- Si el usuario no está autenticado, se imprime un mensaje para iniciar sesión.


# Operadores ternarios o expresiones condicionales

Las **condiciones ternarias** en Python son una forma compacta de escribir una declaración `if-else` en una sola línea. Son útiles para tomar decisiones simples y asignar valores dependiendo de una condición.

## Sintaxis:

```python
valor = valor_si_verdadero if condicion else valor_si_falso`
```

## Ejemplos:

```python
edad = 18 
mensaje = "Eres mayor de edad" if edad >= 18 else "Eres menor de edad" print(mensaje)  # Salida: Eres mayor de edad`
```

```python
a = 330  
b = 330  
print("A") if a > b else print("=") if a == b else print("B")
```

## ¿Cuándo usarlas?

1. **Condiciones simples:** Cuando solo necesitas tomar una decisión sencilla y clara.
2. **Código más legible:** Para evitar varias líneas de un `if-else` que solo asignan valores o realizan tareas cortas.
3. **Evitar redundancia:** Cuando la lógica es breve y directa.

## Cuándo **no** usarlas:

- Cuando la lógica es compleja o contiene múltiples pasos, ya que puede reducir la claridad del código.

# Cadenas de texto y números sobre condiciones booleanas:

Las cadenas de texto vacías, cuando se ponen en una condición da “False”. Ejemplo:

```python
nombre = ""
if nombre:
	print("El nombre no es vacío") # No se va a pintar porque da False
```

Los números, cuando se evalúan en una condición booleana sabemos que todos excepto el 0 es True, por tanto el 0 es False. Ejemplo

```python
numero = 0
if numero: #False
	print("Aquí no estará nunca")
```




