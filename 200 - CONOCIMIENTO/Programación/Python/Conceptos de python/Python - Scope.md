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
# Índice

<!--/INDICE--> 

- global: define/modifica una variable **fuera de cualquier función**.
    
- local: existe **solo dentro** de una función.
    
- nonlocal: accede/modifica una variable de una **función exterior cercana**, **no global**.

```python
x = "global"  # 🌍 Variable global

def outer():
    x = "en cierre"  # 🔒 Variable local en la función outer (no visible fuera)
    
    def inner():
        nonlocal x  # 🔁 Modifica la variable x del scope de outer()
        x = "nonlocal"
        print("inner:", x)
    
    inner()
    print("outer:", x)

outer()
print("global:", x)
```

	inner: nonlocal
	outer: nonlocal
	global: global

| **Línea**       | **Variable** | **Scope**                 | **Valor final**                      |
| --------------- | ------------ | ------------------------- | ------------------------------------ |
| x = "global"    | x            | Global                    | "global"                             |
| x = "en cierre" | x en outer() | Local a outer()           | Se cambia a "nonlocal" desde inner() |
| nonlocal x      | x en inner() | Se refiere a x de outer() | Modificada a "nonlocal"              |

**🧠 En resumen:**

| **Palabra clave** | **Afecta a…**                          |
| ----------------- | -------------------------------------- |
| local             | Solo a la función donde se define      |
| nonlocal          | A la función externa más cercana       |
| global            | A variables fuera de cualquier función |
