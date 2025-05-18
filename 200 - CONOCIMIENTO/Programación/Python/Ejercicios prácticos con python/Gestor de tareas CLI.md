<!--INDICE-->
# Índice

- [[#1. **Proyecto 1: Gestor de Tareas CLI (Command Line Interface)**]]
- [[#2. Estructura inicial]]
- [[#3. Paso 1: Preparar entorno]]
- [[#4. Paso 2: Pensar el modelo de datos]]
- [[#5. Estructura básica del script]]
- [[#6. Siguientes pasos]]
<!--/INDICE-->


# 1. **Proyecto 1: Gestor de Tareas CLI (Command Line Interface)**

   **🎯 Objetivo**
---
  
Crear una aplicación por terminal que te permita:

- Añadir tareas
    
- Listar tareas
    
- Marcar tareas como completadas
    
- Eliminar tareas
    
- Guardar y recuperar tareas desde un archivo JSON

# 2. Estructura inicial

```
gestor_tareas/
├── main.py
├── tareas.json         ← Aquí se guardarán las tareas
```


# 3. Paso 1: Preparar entorno

1. Crea una carpeta gestor_tareas/.
    
2. Dentro, un archivo main.py.
    
3. Otro archivo vacío llamado tareas.json, con esto dentro al principio:
   
	```
	[]
	```

# 4. Paso 2: Pensar el modelo de datos

Cada tarea será un diccionario como este:

```python
{
    "id": 1,
    "descripcion": "Comprar pan",
    "completada": False
}
```

# 5. Estructura básica del script

El script irá por consola, con menú:

```python
def mostrar_menu():
    print("\n=== GESTOR DE TAREAS ===")
    print("1. Ver tareas")
    print("2. Añadir tarea")
    print("3. Marcar tarea como completada")
    print("4. Eliminar tarea")
    print("5. Salir")
```

Y luego algo así:

```python
while True:
    mostrar_menu()
    opcion = input("Selecciona una opción: ")

    if opcion == "1":
        ver_tareas()
    elif opcion == "2":
        añadir_tarea()
    elif opcion == "3":
        completar_tarea()
    elif opcion == "4":
        eliminar_tarea()
    elif opcion == "5":
        break
    else:
        print("Opción no válida")
```

# 6. Siguientes pasos

Función para cargar y guardar tareas con JSON

```python
import json

def cargar_tareas():
    with open("tareas.json", "r") as archivo:
        return json.load(archivo)

def guardar_tareas(tareas):
    with open("tareas.json", "w") as archivo:
        json.dump(tareas, archivo, indent=4)
```

---

<font color="#f79646"><u><font color="#f79646">¿Qué hacer ahora?</font></u></font>
---

1. Crear la estructura base del script con el menú
2. Añadir las funciones cargar_tareas() y guardar_tareas()
3. Implementar la opción 1: ver tareas 
4. Implementar la opciñon 2: añadir tareas
