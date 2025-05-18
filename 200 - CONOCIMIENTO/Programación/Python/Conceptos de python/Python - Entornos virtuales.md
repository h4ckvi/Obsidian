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

Después de la activación, su indicador cambiará para mostrar que ahora está trabajando en el entorno activo:

La línea de comandos tendrá este aspecto cuando el entorno virtual esté activo:

```
(myfirstproject) C:\Users\_Your Name_>
```

# Instalar paquetes

Una vez activado su entorno virtual, puede instalar paquetes en él, utilizando pip.

# Desactivar un entorno virtual

Se usa este comando:

```
(myfirstproject) C:\Users\_Your Name_> deactivate
```

Como resultado, ahora está de vuelta en la interfaz de línea de comandos normal:

```
C:\Users\_Your Name_>
```

Si intentas ejecutar un archivo .py fuera del entorno virtual, nos dará un error porque el módulo/módulos no los encuentra, solo están instalados en el entorno virtual


> [!caution]+  El entorno virtual \<nombreproyecto> sigue existiendo, sólo que **no está activado**. 
> Si vuelve a activar el entorno virtual, puede ejecutar el archivo .py y se mostrará el contenido.

