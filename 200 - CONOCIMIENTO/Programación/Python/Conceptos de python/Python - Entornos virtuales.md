---
aliases: 
tags:
  - Programación
categoria:
  - Fundamentos de Python
subcategoria: 
nivel:
---

Ir a [[000 - Conceptos de python]] <br>
Ir a [[000 - Ejercicios prácticos con python]] <br>
Ir a [[000 - Bibliotecas de python]]

---

<!--INDICE-->
<!--/INDICE--> 

# Crear un entrono virtuak

Python tiene incorporado el módulo venv para crear entornos virtuales.

Para crear un entorno virtual en su ordenador, abra el símbolo del sistema y vaya a la carpeta donde desea crear su proyecto, a continuación, escriba este comando:

```
python -m venv myfirstproject
```

Esto configurará un entorno virtual, y creará una carpeta llamada "myfirstproject" con subcarpetas y archivos, así:

La estructura de archivos/carpetas tendrá el siguiente aspecto:

```
myfirstproject  
  Include  
  Lib  
  Scripts  
  .gitignore  
  pyvenv.cfg
```


# Activar entornos virrtuales

Para utilizar el entorno virtual, tienes que activarlo con este comando:

```
myfirstproject\Scripts\activate
```


