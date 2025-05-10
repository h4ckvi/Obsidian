---
aliases: 
tags: 
categoria:
  - Manipulación de datos
subcategoria:
---

# Leer archivos .txt

## **Leer el archivo completo**:

 - Puedes abrir un archivo de texto utilizando la función `open()` y luego leer todo su contenido.
 - Ejemplo:
 
 ```python
 with open('archivo.txt', 'r') as archivo:
	  contenido_completo = archivo.read()
 ```

## **Leer por líneas**:
 
 - Si deseas procesar el archivo línea por línea, utiliza el método `readlines()`.
 - Ejemplo:
 
 
 
 ```python
 with open('archivo.txt', 'r') as archivo:
	  lineas = archivo.readlines()
	  for linea in lineas:
			print(linea)
 ```
 

 
## **Leer una sola línea**:
 
 - Si solo necesitas la primera línea del archivo, usa el método `readline()`.
 - Ejemplo:
 
 
 
 ```python
 with open('archivo.txt', 'r') as archivo:
	  primera_linea = archivo.readline()
	  print(primera_linea)
 ```
 

## **Otras formas**:
   
 - Puedes iterar directamente sobre el archivo para procesar línea por línea sin cargar todo el contenido en memoria.
 - También puedes usar list comprehensions para filtrar o transformar líneas específicas.

# Escribir archivos.txt

Escribir en un archivo de texto (`.txt`) en Python es sencillo. Puedes hacerlo de varias maneras:

## **Abrir un archivo en modo escritura (`'w'`)**:
 
 - Utiliza la función `open()` para abrir un archivo en modo escritura.
 - Si el archivo no existe, se creará uno nuevo. Si ya existe, su contenido se sobrescribirá.
 - Ejemplo:
 
 
 
 ```python
 with open('mi_archivo.txt', 'w') as archivo:
	  archivo.write('Hola, mundo!')
 ```
 

 
## **Abrir un archivo en modo anexar (`'a'`)**:
 
 - Si deseas agregar contenido al final del archivo sin borrar lo existente, utiliza el modo anexar.
 - Ejemplo:
 
 
 
 ```python
 with open('mi_archivo.txt', 'a') as archivo:
	  archivo.write('\n¡Esto es una nueva línea!')
 ```
 

 
## **Usar `writelines()` para escribir varias líneas**:
 
 - Puedes escribir una lista de cadenas en el archivo utilizando `writelines()`.
 - Recuerda agregar manualmente los caracteres de nueva línea (`'\n'`) si deseas separar las líneas.
 - Ejemplo:
 
 
 
 ```python
 lineas = ['Línea ## ', 'Línea 2', 'Línea 3  ']
 with open('mi_archivo.txt', 'w') as archivo:
	  archivo.writelines('\n'.join(lineas))
 ```

> [!faq]- ¿Qué es `.join(lineas)` y por qué se ha usado en el ejemplo?
> 
> En el ejemplo que proporcioné, utilicé `.join(lineas)` para convertir la lista de cadenas `lineas` en una sola cadena, donde cada elemento de la lista está separado por un carácter de nueva línea (`'\n'`). Esto es necesario porque el método `writelines()` espera una secuencia de cadenas (como una lista) para escribir en el archivo.
> 
> Aquí está el análisis paso a paso:
> 
> 1. **Creación de la lista `lineas`**:
>  
> - Supongamos que tenemos la siguiente lista:
>   
> ```python
> lineas = ['Línea 1', 'Línea 2', 'Línea ## ']
> ```
>   
> 2. **Uso de `.join()` para combinar las líneas**:
>  
>- El método `.join()` toma una secuencia de cadenas y las concatena utilizando la cadena proporcionada como separador.
> - En nuestro caso, queremos unir las líneas con un carácter de nueva línea (`'\n'`):
>   
> ```python
> contenido_completo = '\n'.join(lineas)
> ``` 
> - Esto crea una sola cadena con las líneas separadas por saltos de línea:
>  
> ```python
> 'Línea 1\nLínea 2\nLínea ## '
> ```
>  
> ## . **Escribir en el archivo**:
>  
> - Luego utilizamos `contenido_completo` en el método `writelines()` para escribir todas las líneas en el archivo.
> 
> En resumen, `.join(lineas)` es necesario para formatear correctamente las líneas antes de escribirlas en el archivo. Si tienes más preguntas, no dudes en preguntar. 📄🐍

## **Cerrar el archivo automáticamente**:
 
Al usar `with`, el archivo se cierra automáticamente al salir del bloque.
Esto garantiza que los recursos se liberen correctamente.

Recuerda reemplazar `'mi_archivo.txt'` con la ruta real de tu archivo. ¡Buena suerte escribiendo en archivos de texto en Python! 📄🐍.

# Palabra clave **”with”**

La palabra clave **`with`** en Python se utiliza en el contexto de la gestión de recursos, como archivos, conexiones de red o bases de datos. A continuación, te explico su significado y uso:

## **Significado de `with`**:
 
 - `with` crea un **contexto de manejo de recursos**. Esto significa que se encarga automáticamente de abrir y cerrar el recurso (como un archivo) de manera segura.
 - Cuando utilizas `with`, no necesitas preocuparte por cerrar explícitamente el recurso después de usarlo.

## **Uso de `with` con archivos**:
 
 - Al abrir un archivo con `with`, el archivo se cierra automáticamente al salir del bloque `with`.
 - Es una práctica recomendada utilizar `with` al trabajar con archivos para evitar posibles errores y asegurar que los recursos se liberen correctamente.

## **Ejemplo de uso de `with` para abrir un archivo**:
 
 
 
 ```python
 # Abre el archivo 'mi_archivo.txt' en modo lectura ('r')
 with open('mi_archivo.txt', 'r', encoding="UTF-8") as archivo:
	  contenido = archivo.read()
	  # Realiza operaciones con el contenido del archivo
 
 # Fuera del bloque 'with', el archivo se cierra automáticamente
 ```
 
 
## **¿Es obligatorio usar `with`?**:
 
 - No es estrictamente obligatorio, pero es altamente recomendado.
 - Si no usas `with`, debes recordar cerrar el archivo manualmente con `archivo.close()`. Sin embargo, esto puede llevar a errores si olvidas cerrarlo.

En resumen, `with` es una excelente práctica para trabajar con recursos que necesitan ser liberados correctamente, como archivos. Siempre que puedas, utiliza `with` para garantizar una gestión segura de recursos. 📄🐍

