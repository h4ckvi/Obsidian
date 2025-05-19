---
aliases: 
link: 
tags: 
categoria:
  - Control de flujo en python
subcategoria:
---

se utiliza para ejecutar un conjunto de operaciones **mientras una condición particular sea verdadera**. Cuando la condición se vuelve falsa, la ejecución sale inmediatamente del bucle, y se ejecuta la primera instrucción después del bucle **`while`**.

Aquí tienes una explicación más detallada:

# 1. Sintaxis básica del bucle `while`
 
La estructura básica de un bucle **`while`** se muestra a continuación:
 
 ```python
 while <condición>:
	  <instrucción(es)>
 ```
 
 
 - `<instrucción(es)>` representa el bloque que se ejecutará repetidamente, a menudo llamado el cuerpo del bucle. Este bloque está indentado, al igual que en una sentencia `if`.
- Recuerda: Todas las estructuras de control en Python utilizan la indentación para definir bloques.
 
## 1.1 Bucles anidados

![[Python - For loop#2.1 Bucles anidados (afecta a while, for e if)]]

# 2. Funcionamiento del bucle `while`:
 
 - La expresión de control, `<condición>`, generalmente involucra una o más variables que se inicializan antes de comenzar el bucle y luego se modifican en algún lugar dentro del cuerpo del bucle.
 - Cuando se encuentra un bucle **`while`**, primero se evalúa `<condición>` en contexto booleano. Si es verdadera, se ejecuta el cuerpo del bucle. Luego, se verifica nuevamente `<condición>`, y si sigue siendo verdadera, se ejecuta el cuerpo nuevamente. Esto continúa hasta que `<condición>` se vuelva falsa, momento en el que la ejecución del programa avanza a la primera instrucción después del cuerpo del bucle.

Ejemplo de bucle `while`:
  
 ```python
# Ejemplo 1 de bucle sencillo:
n = 5
while n > 0:
	n -= 1
	print(n)

# Ejemplo 2:

contador = 0

while contador <= 5:
	print(contador)
	contador += 1  # Se actualiza el contador. Es importante incrementar para evitar un bucle infinito
# El bucle termina cuando contador >=5 d
 ```
 
 - Lo que sucede en este ejemplo:
	  
	  1. Inicialmente, `n` es 5.
	  2. La expresión en la cabecera del bucle **`while`** en la línea 2 es `n > 0`, que es verdadera, por lo que se ejecuta el cuerpo del bucle.
	  3. El resultado impreso es:
			
			```
			4
			3
			2
			1
			0
			```
			
 - El bucle continúa hasta que `n` se vuelve 0.
	  

**`while`** es útil cuando no sabemos cuántas veces queremos repetir una acción, pero queremos seguir haciéndolo mientras se cumpla una condición específica. 

# 3. `Break` para salir de un bucle `while`

Podemos usar `break` para **interrumpir la ejecución** del bucle cuando se cumpla una condición específica.

```python
print("\n Bucle while con break:")
contador = 0

# Ejemplo de un uso de Break para salir de un bucle

while True:
  print(contador)
  contador += 1
  if contador == 5:
      break  # Sale del bucle

# Ejemplo de otro Break para salir del bucle
contador = 0

while contador <= 100:
	contador += 1
	print(contador)
	if contador % 5 == 0:
		print("El número es múltiplo de 5")
		break
```

**Conclusión**

- `while` repite un bloque **mientras** la condición sea verdadera.
- `break` **detiene** completamente el bucle.

La diferencia clave es que break te permite salir del bucle en cualquier momento, sin necesidad de que la condición principal del while se cumpla. Esto es útil cuando quieres terminar el bucle bajo ciertas condiciones internas sin modificar la condición principal.


# 4.  `Continue` para saltar una iteración

continue se usa dentro de un bucle para **saltar la iteración actual y pasar directamente a la siguiente**, sin ejecutar el resto del código dentro del bucle en esa iteración.


```python
num = 0
while num < 5:
    num += 1
    if num % 2 == 0:
        continue  # Salta el print y vuelve al inicio del bucle
    print(num)
```

```
1
3
5
```

Aquí, cuando num es par, continue hace que se pase a la siguiente iteración sin ejecutar print(num).

1. **Evitar código innecesario** en algunas iteraciones.

2. **Filtrar elementos** en bucles sin necesidad de estructuras más complejas.

3. **Optimizar el flujo del bucle**, haciendo que ciertas condiciones no ejecuten código extra.

  

Si necesitas **salir completamente** del bucle, usa break. Si solo quieres **saltar una iteración y seguir con la siguiente**, usa continue.

# 5. `Else` en un bucle while

En Python, el else en un bucle while se ejecuta solo cuando la condición del while se vuelve falsa de manera natural, es decir, sin que el bucle se interrumpa con un break.

1.	Ejecutar un bloque de código si el bucle termina sin interrupciones:

```python
x = 0
while x < 5:
    print(x)
    x += 1
else:
    print("El bucle terminó sin interrupciones.")
```

```
0  
1  
2  
3  
4  
El bucle terminó sin interrupciones.
```

2.	Distinguir entre terminación normal e interrupción con break:

```python
x = 0
while x < 5:
    if x == 3:
        print("Bucle interrumpido en 3")
        break
    print(x)
    x += 1
else:
    print("El bucle terminó normalmente.")
```

```
0  
1  
2  
Bucle interrumpido en 3
```

Como se usó break, el else no se ejecuta.

1.	Validación de búsqueda exitosa en un bucle:

```python
valores = [1, 2, 3, 4, 5]
objetivo = 6
i = 0

while i < len(valores):
    if valores[i] == objetivo:
        print("Valor encontrado")
        break
    i += 1
else:
    print("Valor no encontrado")
```

```
Valor no encontrado
```

Si objetivo estuviera en la lista, el break lo detendría y el else no se ejecutaría.

 
> [!NOTE] El else en while es útil para ejecutar código solo si el bucle no se interrumpe con break.


# 6. Solicitar datos al usuario en un bucle while

Los bucles `while` son útiles cuando necesitamos **solicitar datos al usuario** hasta que ingrese un valor válido.

## Pedir un número positivo

El siguiente código **pide un número positivo** al usuario y no le deja continuar hasta que lo introduzca correctamente:

Ejemplo: Solicitar un número positivo

```python
# Pedir un número positivo al usuario
numero = -1

while numero < 0:
  numero = int(input("Escribe un número positivo: "))
  if numero < 0:
      print("El número debe ser positivo. Intenta otra vez.")

print(f"El número que has introducido es {numero}")
```

