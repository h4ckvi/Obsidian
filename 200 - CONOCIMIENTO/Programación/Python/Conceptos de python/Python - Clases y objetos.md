---
aliases:
  - clases en python
tags:
  - Programación
categoria:
  - Programación orientada a objetos (POO)
subcategoria: 
nivel: []
---

<!--INDICE-->
# Índice

- [[#1. ¿Qué son las Clases?]]
  - [[#1.1. Atributos y Métodos]]
- [[#2. Creando Instancias]]
  - [[#2.1. Encapsulando Lógica]]
- [[#3. Resumiendo]]
- [[#4. 🔒 Encapsulamiento en Python]]
  - [[#4.1. ¿Por qué es Importante el Encapsulamiento?]]
    - [[#4.1.1. Ejemplo de Encapsulamiento en Clases]]
  - [[#4.2. Conclusión]]
<!--/INDICE-->




Ver [[000 - Conceptos de python]]

A medida que construimos aplicaciones más complejas, es esencial tener la capacidad de **organizar nuestro código** y **reutilizar lógica** de manera eficiente. Aquí, aprenderemos cómo las clases actúan como **plantillas** para crear objetos, facilitando la encapsulación de datos y métodos que se relacionan entre sí.

Diferencia entre <font color="#00b0f0">clase</font> y <font color="#00b050">objeto</font>:

> Una **<font color="#00b0f0">clase</font>** es una plantilla.

> Un **<font color="#00b050">objeto</font>** es una instancia concreta creada a partir de esa plantilla.

# 1. ¿Qué son las Clases?

Las clases son fundamentalmente **modelos** que te permiten definir un conjunto de propiedades y funciones relacionadas. Imagina que estamos creando un **coche**:

- **Clase**: Es la planta donde fabricamos coches.
- **Objeto**: Es el coche específico que hemos creado.

## Método `_init()_` 

Las clases combinan atributos (propiedades) y métodos (funciones) en un solo lugar. Por ejemplo, al definir un coche, sus atributos pueden incluir:

- Marca
- Modelo
- Color

Los objetos también pueden contener métodos. Los métodos en los objetos son funciones que pertenecen al objeto.

```python
class Coche:
	def __init__(self, marca, modelo, color):
	self.marca = marca
	self.modelo = modelo
	self.color = color

	def arrancar(self): 
	return f'El coche {self.marca} {self.modelo} ha arrancado.'
```


> [!info] ¿Qué es el parámetro `self()`?
> El parámetro self es una referencia a la instancia actual de la clase, y se utiliza para acceder a variables que pertenecen a la clase.
> 
> No tiene por qué llamarse self, puedes llamarlo como quieras, pero tiene que ser el primer parámetro de cualquier función de la clase


## Método `_str_()` 

```python
def __str__(self):
    return f"{self.marca} {self.modelo} en color {self.color}"
```

> Útil para depurar o mostrar objetos de forma legible.

## Métodos adicionales

Puedes tener métodos personalizados además de __init__, como:

```python
def pintar(self, nuevo_color):
    self.color = nuevo_color
```

> Ejemplo de cómo los objetos pueden **modificar su estado**.


##  Palabra clave `pass`

```python
class Vehiculo:
    pass
```

> Por si quieres dejar clases vacías como estructura inicial (opr alguna razón)

# 2. Creando Instancias

Cuando creamos una instancia de una clase, estamos utilizando esa plantilla para **fabricar** un objeto específico. Por ejemplo, podemos tener múltiples coches, pero cada uno tendrá características diferentes:

```python
mi_coche = Coche('Toyota', 'Corolla', 'Rojo')
mi_coche2 = Coche('Ford', 'Fiesta', 'Azul')

print(mi_coche.arrancar())  # Salida: El coche Toyota Corolla ha arrancado.
print(mi_coche2.arrancar())  # Salida: El coche Ford Fiesta ha arrancado.
```

## 2.1. Encapsulando Lógica

Las clases nos permiten **encapsular la lógica** de una manera que podemos reutilizar. Por ejemplo, cada coche puede arrancar de forma similar, pero los detalles específicos de cada modelo pueden variar.

Ahora, si consideramos que ambos coches arrancan, pero el resultado nos muestra sus diferencias, ¡ese es el poder de las clases!

# 3. Resumiendo

Las clases en Python son herramientas poderosas que te permiten organizar tu código, agrupar datos y funciones, y reutilizar lógica de manera eficiente. En esta lección, hemos aprendido:

- ¿Qué son las clases y cómo funcionan?
- La diferencia entre atributos y métodos.
- Cómo crear instancias de una clase.

# 4. 🔒 Encapsulamiento en Python

El concepto de **encapsulamiento** es fundamental en la programación orientada a objetos. Su objetivo principal es **ocultar los detalles internos** de una clase y mostrar solo la interfaz pública. Esto significa que, al interactuar con una clase, no necesitas conocer la implementación interna; solo tienes que saber cómo utilizarla.

## 4.1. ¿Por qué es Importante el Encapsulamiento?

Imagina un coche: al usarlo, solo necesitas saber cómo arrancarlo y conducirlo. No es necesario entender cómo funciona el motor o los sistemas eléctricos internos. Esto es precisamente lo que logramos con el encapsulamiento: al igual que el coche, ocultamos la complejidad y proporcionamos una interfaz sencilla de usar.

### 4.1.1. Ejemplo de Encapsulamiento en Clases

En Python, puedes utilizar métodos y atributos privados para asegurar que los detalles internos de la clase no sean accesibles desde fuera.

Ejemplo de Clase Coche

```python
class Coche:
	def __init__(self):
	   self.__motor_encendido = False
	def arrancar(self):
		self.__motor_encendido = True
		
	 print('El coche ha arrancado')
	 
	def estado_motor(self):
	   
	return self.__motor_encendido
```

En este ejemplo, el atributo `__motor_encendido` es privado. Solo puede ser modificado por el método `arrancar`, asegurando que el estado del motor no pueda ser manipulado desde fuera de la clase.

## 4.2. Conclusión

El encapsulamiento no solo protege tus datos, sino que también mejora la **mantenibilidad** del código. Al ocultar la implementación y exponer solo lo necesario, creas un código más limpio y fácil de entender. ¡Domina este concepto y lleva tus clases en Python al siguiente nivel!


