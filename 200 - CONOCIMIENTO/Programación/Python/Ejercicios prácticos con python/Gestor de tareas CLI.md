
# **Proyecto 1: Gestor de Tareas CLI (Command Line Interface)**

   **🎯 Objetivo**
---
  
Crear una aplicación por terminal que te permita:

- Añadir tareas
    
- Listar tareas
    
- Marcar tareas como completadas
    
- Eliminar tareas
    
- Guardar y recuperar tareas desde un archivo JSON

# Estructura inicial

```
gestor_tareas/
├── main.py
├── tareas.json         ← Aquí se guardarán las tareas
```


# Paso 1: Preparar entorno

1. Crea una carpeta gestor_tareas/.
    
2. Dentro, un archivo main.py.
    
3. Otro archivo vacío llamado tareas.json, con esto dentro al principio:

# Paso 2: Pensar el modelo de datos

Cada tarea será un diccionario como este:

```
{
    "id": 1,
    "descripcion": "Comprar pan",
    "completada": False
}
```

# Estructura básica del script

El script irá por consola, con menú:

```
def mostrar_menu():
    print("\n=== GESTOR DE TAREAS ===")
    print("1. Ver tareas")
    print("2. Añadir tarea")
    print("3. Marcar tarea como completada")
    print("4. Eliminar tarea")
    print("5. Salir")
```