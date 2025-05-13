---
aliases:
  - fechas, manejo de fechas
tags:
  - Programación
categoria:
  - Manejo de datos en Python
subcategoria: 
nivel:
  - principiante
---

Ver [[nota SILO correspondiente]]
Ver [[MOC correspondiente]]

# 📅 Introducción a las Fechas en Python

Una fecha en Python no es un tipo de dato propio, pero podemos importar un módulo llamado datetime para trabajar con fechas como objetos fecha.

## 1. Trabajando con `datetime`

Para comenzar a usar fechas en Python, primero necesitamos importar el módulo `datetime`. Este módulo ofrece varias funciones útiles, entre ellas `datetime` y `timedelta`.

Veamos cómo obtener la fecha y hora actual:

Ejemplo: Fecha y Hora Actual

```python
from datetime import datetime

# Obtener la fecha y hora actual
ahora = datetime.now()
print('Fecha y hora actual:', ahora)
```

## 2. Creando Fechas Específicas

A veces, es necesario trabajar con fechas en un momento específico. Afortunadamente, crear una fecha en Python es muy simple:

Ejemplo: Fecha Específica

```python
from datetime import datetime

# Crear una fecha específica
fecha_especifica = datetime(2025, 2, 12, 15, 30)  # 12 de febrero de 2025, 15:30
print('Fecha específica:', fecha_especifica)
```

Como puedes ver, simplemente tienes que especificar el año, mes, día, hora, minuto y segundo, en ese orden. ¡No te preocupes por compensaciones de meses como en otros lenguajes!

### Conclusión

El módulo `datetime` en Python facilita el trabajo con fechas y horas. Ya sea que necesites la fecha y hora actuales o crear instancias específicas, Python lo hace sencillo y directo.


#  📅 Formateando Fechas en Python

En esta lección aprenderás a **formatear fechas** en Python, algo esencial para cualquier aplicación que manipule datos temporales. Verás cómo utilizar el método `strftime` para obtener representaciones más legibles de las fechas.

## 1. ¿Por qué formatear fechas?

Al trabajar con fechas en Python, a menudo queremos representar estos datos de una manera que tenga sentido para el usuario. Con el método `strftime`, puedes convertir un objeto `datetime` en una cadena con el formato que desees. ¡Es más fácil de lo que parece!

## 2. Obtener el formato adecuado

Para formatear efectivamente, necesitas especificar el formato deseado. Puedes consultar la documentación de Python para ver todos los códigos de formato disponibles. Por ejemplo:

- **%d**: Día del mes (01 a 31)
- **%m**: Mes (01 a 12)
- **%Y**: Año con cuatro dígitos
- **%y**: Año con dos dígitos

## 3. Ejemplo Práctico

Veamos un ejemplo sobre cómo podrías formatear la fecha actual utilizando estos códigos:

Código para Formatear la Fecha Actual

```python
from datetime import datetime
fecha_actual = datetime.now()
formato_fecha = fecha_actual.strftime('%d/%m/%Y')
print(formato_fecha)
```

En este código, estamos importando `datetime` y luego obteniendo la fecha y hora actual. Utilizamos `strftime` para formatear la fecha al formato `día/mes/año`.

## 4. Personaliza tus formatos

Además, puedes personalizar tus formatos de acuerdo con tus preferencias. Con solo cambiar el string de formato, puedes obtener resultados como “2023-10-01” o “01-Oct-2023”.

### Añadiendo el Tiempo

Ahora, si quieres incluir la hora, simplemente añade otros códigos:

Código para Formatear Fecha y Hora

```python
formato_fecha_y_hora = fecha_actual.strftime('%d/%m/%Y %H:%M:%S')\nprint(formato_fecha_y_hora)
```

Roles de los códigos:

- **%H**: Hora (00 a 23)
- **%M**: Minutos (00 a 59)
- **%S**: Segundos (00 a 59)

## Resumen

El formateo de fechas en Python es una herramienta poderosa que te permite presentar tus datos de manera clara y útil. Con un poco de práctica, podrás manipular fechas como un profesional. ¡No olvides revisar la documentación para explorar más opciones de formato!


# 🗓️ Operaciones con Fechas en Python

En esta lección, aprenderás a **manipular fechas** de manera increíblemente fácil con Python. Desde sumar y restar días hasta **horas** y **meses**, las posibilidades son fascinantes. Imagina que necesitas calcular el día de ayer o la fecha de mañana; ¡con Python esto es pan comido!

## 1. Trabajando con `datetime`

La librería `datetime` de Python te permite trabajar con fechas y horas de forma sencilla. Con el módulo `timedelta`, puedes realizar operaciones como restar o sumar días, horas, o incluso segundos.

### Resta de Fechas

Para obtener la fecha de ayer, puedes usar el siguiente código:

Ejemplo: Resta de 1 Día

```python
from datetime import datetime, timedelta

# Obtener la fecha actual
fecha_hoy = datetime.now()

# Calcular la fecha de ayer
fecha_ayer = fecha_hoy - timedelta(days=1)

print(fecha_ayer)
```

###  Suma de Fechas

Del mismo modo, si deseas saber la fecha de mañana, la operación es igual de sencilla:

Ejemplo: Suma de 1 Día

```python
from datetime import datetime, timedelta

# Obtener la fecha actual
fecha_hoy = datetime.now()

# Calcular la fecha de mañana
fecha_manana = fecha_hoy + timedelta(days=1)

print(fecha_manana)
```

## 2. Trabajar con Horas y Más

Además de días, puedes realizar operaciones con horas, semanas, y ¡sí! incluso medios días:

Ejemplo: Suma de Horas

```python
from datetime import datetime, timedelta

# Obtener la fecha actual
fecha_hoy = datetime.now()

# Calcular la fecha dos horas después
nueva_fecha = fecha_hoy + timedelta(hours=2)

print(nueva_fecha)
```

# 📅 Calculando la Diferencia entre Dos Fechas

En esta lección, aprenderemos a **calcular la diferencia entre dos fechas** utilizando Python. Manejar fechas puede parecer complicado, pero ¡te sorprenderás de lo sencillo que es!

## 1. Creando Fechas con `datetime`

Para empezar, utilizamos el módulo `datetime` que ya viene incluido en Python. Al crear un objeto de fecha, podemos acceder a sus propiedades como el año, mes, hora, minuto y más.

### Accediendo a las Propiedades de una Fecha

Aquí tienes un pequeño ejemplo de cómo puedes acceder a las propiedades de un objeto de fecha:

Ejemplo de Propiedades de Fechas

```python
import datetime

now = datetime.datetime.now()
print('Año:', now.year)
print('Mes:', now.month)
print('Día:', now.day)
```

## 2. Calculando la Diferencia

Una de las funcionalidades más poderosas que ofrece el módulo `datetime` es la capacidad de calcular la diferencia entre dos fechas, utilizando la resta.

### Ejemplo de Cálculo de Diferencia

Imagina que quieres saber cuántos días faltan para tu cumpleaños:

Ejemplo de Cálculo de Diferencia

```python
import datetime

# Fecha de hoy
hoy = datetime.datetime.now()

# Mi cumpleaños
cumpleanos = datetime.datetime(hoy.year, 3, 30)  # Cambia la fecha según tu cumpleaños

# Calculando la diferencia
diferencia = cumpleanos - hoy
print('Días hasta mi cumpleaños:', diferencia.days)
```

## 3. ¿Qué es un `timedelta`?

Cuando restamos una fecha de otra, el resultado es un objeto `timedelta`, que representa la diferencia en días, segundos y microsegundos. Esto nos da un montón de información útil acerca de la diferencia entre dos fechas. ¡Así que podrás conocer exactamente cuántos días han pasado o faltan!

### Accediendo a Atributos de `timedelta`

Puedes acceder fácilmente a la cantidad de días, segundos, y más del `timedelta` generado:

Accediendo a `timedelta`

```python
print('Días de diferencia:', diferencia.days)
print('Segundos de diferencia:', diferencia.seconds)
```

Como puedes ver, gestionar fechas en Python es bastante accesible y, sobre todo, ¡divertido! Sigue practicando y verás cómo se convierte en una segunda naturaleza.

# 🌍 Cambiando el Idioma de la Fecha en Python

En esta lección, aprenderás cómo **personalizar el idioma de las fechas** al trabajar con Python. Si alguna vez te has encontrado con que los nombres de los días de la semana o los meses aparecen en inglés, esta clase te mostrará cómo cambiarlos a tu idioma preferido utilizando la biblioteca `locale`.

## 1. Formateando Fechas

Primero, es importante saber que Python permite formatear fechas usando el módulo `locale`. Aquí tienes un ejemplo de cómo establecer el idioma:

Ejemplo de Configuración de Locale

```python
import locale

# Cambiar a español de España
locale.setlocale(locale.LC_TIME, 'es_ES.UTF-8')

from datetime import datetime
fecha = datetime.now()
print(fecha.strftime('%A, %B %Y'))
```

Cuando ejecutas el código anterior, verás que los nombres se muestran correctamente en español. Por ejemplo, “miércoles, marzo 2025”.

## 2. Consideraciones Lingüísticas

Un punto importante a tener en cuenta es que **en español, los días de la semana y los nombres de los meses se escriben en minúscula**, a menos que estén al principio de una oración. Esto puede sorprender a muchos, pero es una regla gramatical según la Real Academia Española.

### Errores Comunes

Es común escuchar que “Python está roto” si los nombres no aparecen en mayúscula. No te preocupes, ¡no es un error! Simplemente es la forma correcta en que Python muestra estas cadenas.

Si prefieres que se capitalice la primera letra, puedes hacerlo utilizando funciones adicionales que ya hemos aprendido en clases anteriores.

En resumen, esta lección no solo es valiosa para tus habilidades de programación, sino también para ampliar tu conocimiento del idioma. ¡Diviértete programando y aprendiendo!