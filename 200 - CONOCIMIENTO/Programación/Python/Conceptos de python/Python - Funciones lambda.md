---
aliases: 
link: 
tags: 
categoria:
  - Funciones de python
subcategoria:
---

# Funciones Lambda:

- Una función lambda es una **función anónima** y pequeña que se crea utilizando la palabra clave **`lambda`**.
- A diferencia de las funciones definidas con **`def`**, las funciones lambda no tienen un nombre explícito.
- Se utilizan para crear funciones simples y concisas en una sola línea.
- La sintaxis básica de una función lambda es: `lambda argumentos: expresión`.

## Ejemplo de función lambda:


```python
# Función lambda que suma dos números
suma = lambda a, b: a + b

resultado = suma(3, 5)
print(f"Resultado de la suma: {resultado}")  # Resultado: 8
```

En este ejemplo, la función lambda toma dos argumentos (`a` y `b`) y devuelve su suma.

## ¿Por qué usar funciones lambda?

El poder de lambda se muestra mejor cuando se utilizan como una función anónima dentro de otra función.

Digamos que tienes una definición de función que toma un argumento, y ese argumento se multiplicará por un número desconocido:

```python
def myfunc(n):  
  return lambda a : a * n
```

Usa esa definición de función para hacer una función que siempre duplique el número que envías:

```python
def myfunc(n):  
  return lambda a : a * n  
  
mytripler = myfunc(3)  
  
print(mytripler(11))
```

### 🔍 ¿Qué ocurre aquí?

```python
mytripler = myfunc(3)
```

Esto significa que mytripler es, ahora, una función y adquiere el valor de  `myfunc(3)`, que devuelve  `lambda a: a * 3`. 

```python
mytripler = lambda a : a * 3
```

Esa función **queda almacenada en mytripler**. Lo que quiere decir que mytripler es ahora:

```python
mytripler(a) = a * 3
```

Como mytripler es ahora esa función lambda (lambda a: a * 3), al pasarle 11, hace la operación:

---

La clave está en cómo funcionan las **funciones que devuelven funciones** (funciones de orden superior) y el concepto de **closure (cierre)** en Python.

### **📌 ¿Por qué ocurre esto?**

  

Porque cuando defines una función dentro de otra, la interna **recuerda** el valor de las variables externas aunque ya hayan “desaparecido” del contexto.

Eso se llama **closure**.