
Aquí tienes una serie de ejercicios de Regex en Python, organizados de **fácil a difícil**, para que practiques progresivamente.

# 🏋️‍♂️ Ejercicios de Regex en Python

A continuación, tienes ejercicios para practicar `re.search()`, `re.findall()`, `re.finditer()`, `group()`, `start()`, `end()` y `span()`. 

> 📌 **Instrucciones**:  
> - Intenta resolver cada ejercicio antes de mirar la solución.  
> - Usa los métodos `group()`, `start()`, `end()` y `span()` donde sea necesario.  
> - Usa `re.search()`, `re.findall()`, `re.finditer()` o `re.sub()` según corresponda.  

---

# ✅ Ejercicio 1: Encuentra un número en una cadena  
Dado el siguiente texto, encuentra el **primer número** usando `re.search()` y muestra su posición.

```python
import re

texto = "El producto cuesta 250 euros."

# Escribe aquí tu regex
````

**Salida esperada:**

```
Número encontrado: 250
Posición: (17, 20)
```

  

---

# **✅ Ejercicio 2: Extraer todas las palabras en una lista**

  

Extrae todas las palabras de una cadena usando re.findall().

```python
import re

texto = "Python es un lenguaje poderoso y fácil de aprender."

# Escribe aquí tu regex
```

**Salida esperada:**

```
['Python', 'es', 'un', 'lenguaje', 'poderoso', 'y', 'fácil', 'de', 'aprender']
```

  

---

# **✅ Ejercicio 3: Extraer correos electrónicos**

  

Encuentra y extrae todas las direcciones de correo electrónico de la siguiente cadena.

```python
import re

texto = "Mis correos son ejemplo@mail.com y otro.email@dominio.org, escríbeme."

# Escribe aquí tu regex
```

**Salida esperada:**

```
['ejemplo@mail.com', 'otro.email@dominio.org']
```

  

---

# **✅ Ejercicio 4: Buscar y mostrar fechas**

  

Dado un texto, encuentra todas las fechas en formato DD/MM/AAAA.

```python
import re

texto = "Las reuniones son el 15/06/2023, 01/01/2024 y 25/12/2022."

# Escribe aquí tu regex
```

**Salida esperada:**

```
['15/06/2023', '01/01/2024', '25/12/2022']
```

  

---

# **✅ Ejercicio 5: Validar un número de teléfono**

  

Crea una regex para verificar si una cadena contiene un **número de teléfono válido** en el formato +34 600 123 456.

```python
import re

telefono = "+34 678 987 654"

# Escribe aquí tu regex
```

**Salida esperada:**

```
Número válido: +34 678 987 654
```

  

---

# **✅ Ejercicio 6: Reemplazar palabras**

  

Reemplaza todas las ocurrencias de la palabra "Python" por "JavaScript" en el siguiente texto.

```python
import re

texto = "Python es genial. Python me encanta."

# Escribe aquí tu regex
```

**Salida esperada:**

```
"JavaScript es genial. JavaScript me encanta."
```

  

---

# **✅ Ejercicio 7: Extraer etiquetas HTML**

  

Dado el siguiente código HTML, extrae todos los nombres de las etiquetas (sin los atributos ni contenido).

```python
import re

html = "<div><p class='text'>Hola</p><a href='#'>Link</a></div>"

# Escribe aquí tu regex
```

**Salida esperada:**

```
['div', 'p', 'a', 'div']
```

  

---

# **✅ Ejercicio 8: Validar contraseñas seguras**

  

Crea una regex para validar contraseñas seguras que cumplan estas condiciones:

• Al menos **8 caracteres**

• Al menos **una letra mayúscula**

• Al menos **un número**

• Al menos **un carácter especial (@, #, $, %, &)**

```python
import re

password = "Clave@123"

# Escribe aquí tu regex
```

**Salida esperada:**

```
Contraseña válida: Clave@123
```

  

---

# **✅ Ejercicio 9: Encontrar hashtags en un texto**

  

Dado un texto, extrae todos los hashtags (#palabra).

```python
import re

texto = "Me encanta #Python y #Regex!"

# Escribe aquí tu regex
```

**Salida esperada:**

```
['#Python', '#Regex']
```

  

---

# **✅ Ejercicio 10: Buscar enlaces en un texto**

  

Extrae todos los enlaces de una cadena que contenga URLs.

```python
import re

texto = "Aquí tienes https://example.com y también http://otro.com."

# Escribe aquí tu regex
```

**Salida esperada:**

```
['https://example.com', 'http://otro.com']
```

  

---

Estos ejercicios están organizados de forma progresiva para que mejores tu dominio de **expresiones regulares en Python**. 🚀 ¡Practica y diviértete!

```
Este formato está listo para copiar y pegar en tu nota de Obsidian. 💪
```

