---
nivel:
  - principiante
---

Tenemos una clase con 1 asistente y 1 profesor
1. Pedir la edad de los compañeros que vinieron hoy a clase y ordenar los datos de menor a mayor
2. El mayor es el profesor y el menor es el asistente: ¿Quién es quien?

---

```python
def contar_alumnos(cantidad_de_alumnos):
    
    #Definimos la lista de los alumnos
    alumnos = []
    #Hacemos un bucle donde recogeremos en forma de tupla el nombre y la edad de cada alumno
    for i in range(cantidad_de_alumnos):
        nombre = input("Ingrese el nombre del alumno: ") 
        edad = int(input("Ingrese la edad del alumno: "))
        alumno = (nombre,edad)
        alumnos.append(alumno)
    #Los ordenamos con una función lambda
    alumnos.sort(key=lambda x:x[1])
    #Guardamos mediante índices en una variable quién va aser el asistente y quién el profesor
    asistente = alumnos[0][0]
    profesor = alumnos[-1][0] 
    #retornamos los valores 
    return asistente,profesor

#Desempaquetamos la función guardando los resultados en ese orden
asistente,profesor = contar_alumnos(3)
print(f'El asistente es: {asistente} y su jefe es {profesor}')
```


---

Creamos una función que muestre la serie de Fibonacci entre el 0 y el número que le pasemos:

```python
def fibonacci(num):
	a+b=0,1
	lista_fibonacci = []
	for i in range(num):
		if b > num: return lista_fibonacci
		else:
			fibonacci_lista.append(b)
			a+b = a,a+b
	resultado = lista_fibonacci
print(lista_fibonacci)
```

