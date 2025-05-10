---
aliases: 
tags:
  - Programación
categoria:
  - Programación orientada a objetos (POO)
subcategoria: 
nivel:
---

Ir a [[000 - Conceptos de python]] <br>
Ir a [[000 - Ejercicios prácticos con python]] <br>
Ir a [[000 - Bibliotecas de python]]

<!--INDICE-->
# Índice

- [[#1. Índice]]
- [[#2. Herencia]]
  - [[#2.1. Clase padre]]
  - [[#2.2. Clase hija]]
    - [[#2.2.1. Referencia al padre llamandolo manualmente]]
    - [[#2.2.2. Referencia al padre con super()]]
  - [[#2.3. Ejemplo completo]]
- [[#3. Polimorfismo]]
  - [[#3.1. Polimorfmismo en funciones]]
  - [[#3.2. Polimorfismo con herencia]]
  - [[#3.3. Métodos mágicos polimórficos]]
<!--/INDICE--> 

---

# 2. Herencia

La herencia nos permite definir una clase que hereda todos los métodos y propiedades de otra clase.

La clase padre es la clase de la que se hereda, también llamada clase base.

Clase hija es la clase que hereda de otra clase, también llamada clase derivada.


## 2.1. Clase padre

```python
class Person:
	def __init__(self,fname,lname):
		self.firstname = fname
		self.lastname = lname

	def printname(self):
		print(f"My name is {self.firstname} {self.lastname}")

x = person("Alvaro", "Tejada")
x.printname()
```

## 2.2. Clase hija

Una clase hija **hereda todo** de la clase padre: atributos y métodos.

Pero además, puedes:

1. **Agregar propiedades nuevas**
    
2. **Agregar métodos nuevos**
    
3. **Sobrescribir (modificar) lo que hereda**

Para crear una clase que herede la funcionalidad de otra clase, envíe la clase padre como parámetro al crear la clase hija

```python
# Crea una clase llamada Estudiante, que heredará las propiedades y métodos de la clase Persona:

class student(Person):
	Pass
	
x = student("Olivia", "Romero")
x.printname()
```

> Ahora la clase **student** tiene todos los métodos y propiedades de la clase **Person**

> [!NOTE] Nota: 
> Utiliza la palabra clave pass cuando no desees añadir ninguna otra propiedad o método a la clase.

Cuando creas una clase hija (Student) que **hereda** de una clase padre (Person), puedes:

1. **No definir __init__() en la hija** → se hereda automáticamente el del padre. ⬆️
    
2. **Definir un __init__() en la hija** → tienes que encargarte manualmente de llamar al del padre si quieres conservar su comportamiento. Excepto si usamos `super()`.

### 2.2.1. Referencia al padre llamandolo manualmente

```python
class Person:
  def __init__(self, fname, lname):
    self.firstname = fname
    self.lastname = lname

  def printname(self):
    print(self.firstname, self.lastname)

class Student(Person):
  def __init__(self, fname, lname):
    Person.__init__(self, fname, lname)

x = Student("Mike", "Olsen")
x.printname()
```

🧪 <u>¿Por qué parece que hay dos __init__() iguales?</u>

Porque sí los hay, pero en clases distintas:

Son funciones distintas, aunque se llamen igual y tengan mismos parámetros.

```python
class Person:
    def __init__(self, fname, lname):  # ← en clase padre
        ...

class Student(Person):
    def __init__(self, fname, lname):  # ← en clase hija
        ...
```

📌 <u>¿Por qué en el hijo se llama a Person.__init__()?</u>

Porque cuando redefinimos __init__() en Student, ya no se ejecuta automáticamente el del padre. 

Si queremos mantener lo que hacía Person.__init__() (guardar nombre y apellido), tenemos que llamarlo manualmente:

```python
Person.__init__(self, fname, lname)
```

Es como decir:

> “Sí, tengo mi propio __init__() aquí, pero quiero seguir usando lo que hacía el original en Person.”

### 2.2.2. Referencia al padre con super()

Es una alternativa más moderna y clara a lo de antes. `super()` hace referencia a la clase padre y llama al método que corresponda, pero es más limpio y funciona mejor con múltiples herencias. De esta forma no es necesario utilizar el nombre del elemento padre, heredará automáticamente los métodos y propiedades de su padre.

```python
class Student(Person):
    def __init__(self, fname, lname):
        super().__init__(fname, lname)
```

🧩 Conclusión:

- La clase hija puede tener su propio __init__(), pero eso **anula el del padre**.
- Si necesitas el del padre también, **debes llamarlo manualmente**, o usar super().
- Aunque parezcan iguales, los __init__() están **en clases diferentes** y no se solapan.

## 2.3. Ejemplo completo

```python
class Person:
    def __init__(self, fname, lname):
        self.firstname = fname
        self.lastname = lname

    def printname(self):
        print(self.firstname, self.lastname)

class Student(Person):  # ← Hereda de Person
    def __init__(self, fname, lname, year):
        super().__init__(fname, lname)     # Llama al constructor del padre
        self.graduationyear = year         # Nueva propiedad SOLO para Student

    def welcome(self):  # Nuevo método SOLO para Student
        print(f"Bienvenido {self.firstname} {self.lastname}, promoción {self.graduationyear}")


alumno = Student("Álvaro", "Gómez", 2025)
alumno.printname()      # ← Heredado
alumno.welcome()        # ← Método nuevo
print(alumno.graduationyear)  # ← Propiedad nueva
```

Resultado:

```
Álvaro Gómez 
Bienvenido Álvaro Gómez, promoción 2025 
2025
```

- Student **hereda** de Person, así que también tiene `printname()`.
    
- Le añadimos un nuevo **atributo**: graduationyear.
    
- Le añadimos un nuevo **método**: `welcome()`.
    
- Usamos `super().\__init__()` para no perder el comportamiento del padre.

> [!mind] **Recuerda:**
> **Una clase hija puede hacer todo lo que hace el padre**, y además puede tener lo suyo propio o incluso modificar lo heredado.


---

# 3. Polimorfismo

**Polimorfismo** significa “_muchas formas_” y en programación es la capacidad de **usar un mismo método con objetos diferentes** que se comportan de forma distinta.

```python
class Gato:
    def hablar(self):
        return "Miau"

class Perro:
    def hablar(self):
        return "Guau"

# Ambos tienen un método llamado 'hablar', pero hacen cosas distintas

animales = [Gato(), Perro()]

for animal in animales:
    print(animal.hablar())
```

➡️ Aunque `hablar()` se llama igual, **cada clase lo implementa de forma diferente**. Eso es polimorfismo.

 **📚 Lo que debes recordar:**

1. **Mismo nombre, comportamiento diferente.**
    
    - No necesitas saber exactamente qué clase estás usando, solo que tiene un método hablar().
        
    
2. **Muy útil para código flexible.**
    
    - Permite que funciones trabajen con distintos tipos de objetos, siempre que cumplan cierta “forma” (por eso se habla de _duck typing_ en Python: _“si anda como un pato y suena como un pato…”_).
        
    
3. **No necesitas herencia obligatoriamente.**
    
    - Aunque en otros lenguajes como Java el polimorfismo se basa en herencia y clases abstractas, en Python **basta con que los objetos tengan el mismo método**. No importa su linaje.

## 3.1. Polimorfmismo en funciones

Puedes crear funciones que acepten objetos de cualquier clase, siempre que tengan los métodos esperados.

```python
def hacer_hablar(animal):
    print(animal.hablar())

hacer_hablar(Gato())   # Miau
hacer_hablar(Perro())  # Guau
```

> [!tip] Esto se llama **polimorfismo dinámico** (Python no mira el tipo, sino que el método exista).


## 3.2. Polimorfismo con herencia

```python
class Animal:
    def hablar(self):
        pass  # método genérico, no hace nada

class Pato(Animal):
    def hablar(self):
        return "Cuac"

class Vaca(Animal):
    def hablar(self):
        return "Muuu"

animales = [Pato(), Vaca()]
for a in animales:
    print(a.hablar())
```

Aquí se ve cómo una **misma interfaz (hablar) es redefinida por las subclases**.

## 3.3. Métodos mágicos polimórficos

Python usa polimorfismo todo el tiempo, por ejemplo:

```python
print(len("Hola"))       # 4 (string)
print(len([1, 2, 3]))     # 3 (lista)
print(len({"a": 1}))      # 1 (diccionario)
```

→ len() es **una función polimórfica** que se adapta según el tipo.

🧩 Conclusión:

> El polimorfismo permite usar el mismo nombre de método con objetos distintos que se comportan de forma diferente. Hace que el código sea flexible, limpio y fácil de escalar. En Python, no necesitas herencia para usarlo: basta con que los objetos tengan el mismo método.