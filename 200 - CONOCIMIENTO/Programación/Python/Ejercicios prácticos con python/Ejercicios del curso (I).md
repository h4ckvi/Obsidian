---
nivel:
  - principiante
---

# Sacar máximos, mínimos y promedios

```python
# Promedio de duración

otros_cursos_min = 2.5
otros_cursos_max = 7
otros_cursos_promedio = 4
dalto_curso = 1.5

# Diferencias de duración

diferencia_curso_min = 100 - dalto_curso / otros_cursos_min * 100
diferencia_curso_max =  100 - dalto_curso / otros_cursos_max * 100
diferencia_curso_promedio = 100 - dalto_curso / otros_cursos_promedio * 100

# Resultados

print(f'El curso de Dalto dura un {diferencia_curso_min}% menos que el más rápido')
print(f'El curso de Dalto dura un {round(diferencia_curso_max, 2)}% menos que el más lento')
print(f'El curso de Dalto dura un {diferencia_curso_promedio}% menos que la media')

# Duración de crudos

crudo_dalto = 3.5
crudo_promedio = 5

diferencia_crudo_dalto = 100 - dalto_curso / crudo_dalto * 100
diferenci_crudo_promedio = 100 - otros_cursos_promedio / crudo_promedio * 100

print(f'El curso de dalto es un {round(diferencia_crudo_dalto,2)}% más eficiente')
print(f'Otros cursos son un {diferenci_crudo_promedio}% más eficiente')


# Mostrando diferencias si los cursos duraran 10 horas. ¿Cuánto equivaldrían?

print(f' Ver 10 horas del curso de dalto equivale a ver {round(otros_cursos_promedio / dalto_curso * 10,1)} horas de otros cursos')
print(f'Ver 10 horas de otros cursos equivale a ver {round(dalto_curso / otros_cursos_promedio * 10,1)} horas del curso de Dalto')
```

	El curso de Dalto dura un 40.0% menos que el más rápido
	El curso de Dalto dura un 78.57% menos que el más lento
	El curso de Dalto dura un 62.5% menos que la media
	El curso de dalto es un 57.14% más eficiente
	Otros cursos son un 20.0% más eficiente
	Ver 10 horas del curso de dalto equivale a ver 26.7 horas de otros cursos
	Ver 10 horas de otros cursos equivale a ver 3.8 horas del curso de Dalto
	PS C:\Users\BetaV\Documents\Curso python Dalto> 

# Conteo de palabras y velocidad

Pedirle a un usuario que habla a 2 palabras / min que diga cualquier texto real y calcular:

1. Cuánto tardaría en decir esa frase
2. Cuántas palabras dijo
3. Si tarda más de  1 minuto decirle “Oye, que tampoco quiero un testamento”
4. Si Dalto habla un 30% más rápido, ¿cuánto tardaría él en decirlo?

```python
frase = input("Ingresa la frase a contar: ")
separar_las_palabras = frase.split(" ")
total_palabras = len(separar_las_palabras)

if total_palabras > 25:
    print("Oye, que tampoco quiero un testamento")
else:
    print(f'Esta frase contiene un total de {total_palabras} palabras. \n Una persona normal las diría en {total_palabras/2} segundos. \n Dalto las diría en {(total_palabras/2)*0.7} segundos')
```

