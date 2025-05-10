---
aliases: 
link: 
tags: 
categoria:
  - modulos y paquetes en python
subcategoria:
---

# Acceder a un módulo dentro de otra carpeta en la misma ruta

```python
import funciones_buenas.saludar as m_saludar
```

# Como importar módulos que no están en nuestra ruta

Tenemos que usar `sys.path`, que es una lista de directorios en los que Python busca para encontrar módulos y paquetes cuando se realizan importaciones. Cuando importas un módulo en Python, el intérprete busca ese módulo en los directorios especificados en `sys.path`.

La razón principal por la que a veces necesitas usar `sys.path` es cuando estás trabajando con módulos que no están en los directorios estándar de Python o en el directorio actual de tu programa. Esto puede ocurrir, por ejemplo, cuando estás trabajando en un proyecto que tiene una estructura de directorios específica y necesitas importar módulos desde diferentes ubicaciones dentro de ese proyecto.

Agregar una ruta al `sys.path` te permite especificar manualmente dónde Python debe buscar módulos y paquetes durante la importación. Esto te da flexibilidad para organizar tu código en diferentes ubicaciones y estructuras de directorios.

Por ejemplo, si estás trabajando en un proyecto y tienes módulos en una carpeta diferente a la que estás ejecutando tu script, necesitarás agregar esa ruta al `sys.path` para que Python pueda encontrar esos módulos durante la importación.


```python
import sys 
sys.path.append('/ruta/a/la/carpeta/de/los/modulos')
```

Después de agregar la ruta al `sys.path`, puedes importar los módulos como de costumbre:

```python
import modulo
```





