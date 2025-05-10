---
aliases: 
link: 
tags: 
categoria:
  - modulos y paquetes en python
subcategoria:
---

# ¿Qué es un módulo?

Un módulo en Python es un archivo que contiene definiciones y declaraciones de Python, como funciones, clases y variables. Estos archivos tienen extensión `.py` y pueden ser importados en otros programas Python para reutilizar el código.

# ¿Cómo se utiliza un módulo?

1. **Importación de un módulo:** Puedes importar un módulo en tu programa Python utilizando la palabra clave `import` seguida del nombre del módulo. Por ejemplo:
    
```python
import mi_modulo
```
    
2. **Acceso a los elementos del módulo:** Una vez que has importado un módulo, puedes acceder a sus funciones, clases y variables utilizando la sintaxis `nombre_modulo.elemento`. Por ejemplo:
    
```python
mi_modulo.mi_funcion()
```
    
3. **Alias para un módulo:** Puedes utilizar un alias para un módulo importado utilizando la palabra clave `as`. Esto es útil cuando el nombre del módulo es largo o puede causar conflictos de nombres. Por ejemplo:
    
```python
import mi_modulo as mm mm.mi_funcion()
```
    

# ¿Dónde se encuentran los módulos?

Los módulos en Python pueden estar ubicados en diferentes lugares:

- **Módulos estándar de Python:** Estos son módulos incorporados en la instalación estándar de Python y se pueden utilizar directamente en cualquier programa Python.
    
- **Módulos de terceros:** Son módulos creados por la comunidad de Python y están disponibles a través del Python Package Index (PyPI). Puedes instalar estos módulos utilizando la herramienta `pip` y luego importarlos en tu programa.
    
- **Módulos propios:** Son módulos creados por ti mismo para reutilizar código en diferentes partes de tu aplicación o entre diferentes aplicaciones.
    

# ¿Qué es `__init__.py`?

El archivo `__init__.py` es un archivo especial que se utiliza para indicar que un directorio es un paquete de Python. Este archivo puede estar vacío o puede contener código de inicialización para el paquete. La presencia de este archivo permite que Python trate el directorio como un paquete y permite la importación de módulos desde ese directorio.

# ¿Qué son los paquetes en Python?

Los paquetes en Python son colecciones de módulos relacionados que están organizados en un directorio. Un paquete puede contener subpaquetes y módulos, y puede tener una estructura de directorios jerárquica. Los paquetes se utilizan para organizar y estructurar código Python de manera modular y reutilizable.

## Ejemplo:

Supongamos que tienes un paquete llamado `mi_paquete` que contiene los módulos `modulo1.py` y `modulo2.py`. La estructura del directorio sería la siguiente:

  
```python
mi_paquete/ |-- __init__.py |-- modulo1.py |-- modulo2.py
```

Para importar y utilizar los módulos en tu programa Python, puedes hacer lo siguiente:

 ```python
import mi_paquete.modulo1 mi_paquete.modulo1.mi_funcion()  from mi_paquete import modulo2 modulo2.mi_otra_funcion()
```

---

```python
# Importando un módulo y asigándole el nombre "m_saludar"
import modulo_saludar as m_saludar

# Desde ese módulo importamos dos funciones y les cambiamos el nombre
from modulo_saludar import saludar as saludar_normal, saludar_raro as saludar_como_un_tonto

# Creamos las variables con los saludos
saludo = saludar_normal("Alvaro")
saludo_raro = saludar_como_un_tonto("Silvia")

# Mostramos los resultados
print(saludo)
print(saludo_raro)

# Para ver las propiedades y metodos del namespace
# print(dir(m_saludar))

# Acceder al nombre de este módulo
print(__name__)

# Acceder al nombre del modulo al que llamamos
print(m_saludar.__name__)
```









