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

- El bloque try permite comprobar si hay errores en un bloque de código.

- El bloque except permite gestionar el error.

- El bloque else permite ejecutar código cuando no hay error.

- El bloque finally permite ejecutar código, independientemente del resultado de los bloques try y except.

Ejemplo: Validar entrada con try-except

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


# 

```

```






