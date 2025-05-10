---
tags:
  - etiquetas
frontt: Texto frontmatter
date: 2023-05-12
boolean: true
paginas: 123
estado:
  - "1"
  - "2"
---


# TITULO 1
## TITULO 2
### TITULO 3
#### TITULO 4
##### TITULO 5

# Metadatos inline

	clave:: valor
 

# ESCRITURA:

Normal
**Negrita**
*cursiva*
***negrita y cursiva***
==subrayado== ==**subrayado y negrita**==
~~cloze style~~
$ESPRESIÓN MATEMÁTICA: x=0$
#etiquetas

para representar atajos de teclado: 
- `<kbd> Ctrl + k </kbd>` → <kbd> Ctrl + k </kbd>  
- `Ctrl + K` como si fuera un [[#CÓDIGO INLINE]]
Para representar salida monespaciada: `<samp> hola mundo </samp>` → <samp> hola mundo </samp>

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Curabitur hendrerit neque at massa luctus, nec volutpat dolor efficitur. **Proin convallis eros massa, at pharetra ex commodo commodo**. In eget dolor ut purus congue ornare vitae sed orci. *Nam nec dignissim ligula. Curabitur faucibus tempus sem, in bibendum turpis convallis sed.* Sed convallis metus nec congue **convallis**. Cras libero enim, rhoncus sed fringilla dignissim, dapibus in risus. Phasellus tortor #sapien, tincidunt in felis porttitor, auctor tempor massa. Aenean tristique, purus ut efficitur viverra, lacus est faucibus dolor, commodo malesuada libero metus in libero. **Duis faucibus vestibulum tempus. Vestibulum interdum neque in enim finibus ultricies. In dignissim est eget turpis lacinia, et rutrum enim viverra**. Mauris ut odio vulputate, lacinia leo mollis, placerat sapien.

# LINKS:


Link externo: [link](https://www.markdownguide.org/basic-syntax/#code)
Wikilink: [[Instagram]]
Wikilink no creado: [[Nota sin crear]]

# LISTAS ORDENADAS Y NUMERADAS:

 

1. First item
	1. subitem
		1. Subsubitem
2. Second item
3. Third item
4. Fourth item

 

- First item
- Second item
- Third item
    - Indented item
    - Indented item
- Fourth item

 

- [x] Tarea 1  [completion:: 2024-01-24]
- [ ] Tarea 2


 

# CALLOUTS

> [!script] script

>[!abstract] Abstract. Summary, tldr

>[!info] Info
>>[!info] Info

> [!todo] 

>[!tip] tip

>[!success] check

>[!faq] faq

>[!warning] warning

>[!fail]  fail

>[!danger] danger

>[!bug] 

>[!example] 

>[!quote] cite



# CITAS:

 


> Dorothy followed her through many of the beautiful rooms in her castle.
>
> The Witch bade her clean the pots and kettles and sweep the floor and keep the fire fed with wood.
[^cita1] 

 Se pueden incrustar [[#TITULO 1|títulos]] en las citas:

> ## The quarterly results look great!
>
> - Revenue was off the chart.
> - Profits were higher than ever.
>
>  *Everything* is going according to **plan**.

 

# TABLAS

|        Título        |          Descripción           |            Enlace Interno            |
|:--------------------:|:------------------------------:|:------------------------------------:|
|     **Tarea 1**      | _Esta es una tarea importante_ |             [[Tarea 1]]              |
|     **Tarea 2**      |  _Esta es otra tarea crucial_  |             [[Tarea 2]]              |
|    **Proyecto A**    |   _Detalles del proyecto A_    |            [[Proyecto A]]            |
|    **Proyecto B**    |   _Detalles del proyecto B_    |            [[Proyecto B]]            |
|    **Enlace Web**    |     _Sitio web importante_     |    [OpenAI](https://openai.com/)     |
| **Documento creado** |     _Un documento creado_      |        [[MOC - Toma de notas con Zettlekasten]]         |
|      **Imagen**      |          _Una imagen_          | ![[Pasted image 20240515162455.png]] |


# BLOQUE TABULADO

 


    Este bloque está tabulado:
    <html>
      <head>
      </head>
    </html>

 

# BLOQUE DE CÓDIGO

```python
#!/usr/bin/env python3

first_number = 8 
second_number = 6

result = first_number ** second_number  

print("{:,}".format(result).replace(",",".")) #  resultado con puntos
print("{:,}".format(result)) #  resultado con comas
```


# CÓDIGO INLINE

 

Poner un código en una frase usamos los backticks:   `nano`.
Para poner una frase como código: ``Use code in your Markdown file.``

 

| COLUMNA 1              | COLUMNA 2 |
|:---------------------- | --------- |
| ESTO ES UNA PRUEBA 123 |           |
| ESTO ES UNA PRUEBA     |           |
| ESPACIO DE PRUEBAS     | HOLA      |

 

	###### Basic
	- [ ] to-do
	- [x] incomplete
	- [x] done
	- [-] canceled
	- [>] forwarded
	- [<] scheduling
	
	###### Extras
	- [?] question
	- [!] important



 # IMÁGENES

![[Pasted image 20250104111222.png]]

![[Pasted image 20250104111234.png]] ![[Pasted image 20250104111245.png]]

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Curabitur hendrerit neque at massa luctus, nec volutpat dolor efficitur. **Proin convallis eros massa, at pharetra ex commodo commodo**.  ![[Pasted image 20250104111257.png]]

![[Pasted image 20250104111259.png]] Lorem ipsum dolor sit amet, consectetur adipiscing elit. Curabitur hendrerit neque at massa luctus, nec volutpat dolor efficitur. **Proin convallis eros massa, at pharetra ex commodo commodo**. 

# FOOTNOTES

> [!INFO]+ Podemos hacer referencia a bloques enteros con *footnotes* de esta forma ^bloque
> 
> > Que se trataría como un wikilink normal

> [!INFO]+ Podemos hacer referencias a palabras[^refpalabra] y desde ellas. En esta ocasión usamos el lenguaje natural de obsidian para hacer **referencias** 
> 
> > Se trata como una función integrada de obsidian para enlaces. Aparecen al final del documento
> 
> [^refpalabra]: Referencia a una palabra %% Está no aparece aquí, aparece al final del documento como referencia oficial de obsidian%%



 

# TRANSCLUSIONES

**El siguiente texto es una transclusión de una nota (modo embebido):**

![[000 - Análisis FODA#¿Qué es el análisis FODA?]]

