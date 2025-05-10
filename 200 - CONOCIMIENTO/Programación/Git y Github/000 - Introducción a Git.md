


--- start-multi-column: ID_drv7
```column-settings
Number of Columns: 2
Largest Column: standard
```

No debemos confundir **Git y GitHub**. 

Git es independiente de GitHub, pero GitHub depende de Git 

--- column-break ---

> [!NOTE]- Enlaces de interés
> - [Web](https://git-scm.com/) oficial Git (Documentación, descarga...)
> - [Libro](https://git-scm.com/book/es/v2) de Git en Español (Gratis)
> - ¿Con qué herramientas estoy trabajando?: [iTerm](https://iterm2.com/) con [Oh My Zsh](https://ohmyz.sh/), [VSCode](https://code.visualstudio.com/), [Miro](https://miro.com/)
> - [Guía](https://training.github.com/downloads/es_ES/github-git-cheat-sheet/) con comandos de Git más utilizados
> - [Web](https://github.com/) oficial GitHub
> - [Documentación](https://docs.github.com/es) de GitHub
> - [Configuración](https://docs.github.com/es/authentication/connecting-to-github-with-ssh/about-ssh) SSH para GitHub
> - [Markdown](https://docs.github.com/es/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)
> - Herramientas gráficas para Git y GitHub: [GitHub Desktop](https://desktop.github.com/), [GitKraken](https://gitkraken.com/), [Sourcetree](https://sourcetreeapp.com/), [Fork](https://git-fork.com/)
> - [Gitflow](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow)
> - [GitHub Pages](https://pages.github.com/)
> - [GitHub Actions](https://github.com/features/actions)
> - Practica con los [retos de programación](https://retosdeprogramacion.com/) de la comunidad
> - Y por último, aquí tienes un Gif que he creado con los 30 comandos más utilizados de Git


--- end-multi-column




# Git

## Comandos Git

Nos moveremos por la terminal con una **Bash**, por lo cual los comandos son los de Linux. Ver [[Comandos Shell de Linux]]

| Comando                | Descripción                                                                                                                                                                                             |
| ---------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| $ git config  --global | Todas las configuraciones que se hagan con el `$ git config  --global` afectarán a todas las personas que entren con su usuario en tu equipo. Afectará a todo lo que se haga desde git en esta máquina. |


<font color="#4f81bd">¿Cómo le decimos a Git que queremos inicializar un control de versiones en una carpeta?</font>

EScribimos en el directorio donde queremos iniciarlizar el siguiente comando: `git init`. En este momento, ese directorio tendrás las funciones de git. Se puede ver porque hay un archivo oculto de configuración.

![[Pasted image 20241123174003.png]] ![[Pasted image 20241123173907.png]]

## Rama

La rama Master es aquella que contendrá todo el código unido. No deja de ser una rama, pero que contiene todo.

Se le suele llamar rama **main**

Para cambiarle el nombre a nuestra rama principal usaremos el comando: `git branch -m [nombre]`

![[Pasted image 20241123175811.png]]

## Git add

Sirve para añadir una fotografía del proyecto, es 

# GitHub




Estoy estudiando Git y Github, y quiero que me ayudes a describir los conceptos para mis apuntes de forma sencilla y breve, teniendo en cuenta buenas prácticas y recomendaciones útiles. Te pasaré preguntas y conceptos en una lista. Comencemos.

1. ¿Qué es una rama y qué se diferencia la principal de las demás ramas? ¿Para que se usaría una rama?
2. ¿Qué es el área local y el área de stage?
4. ¿Qué hace el comando Git add y por que mi tutor habla de ese comando para hacer “fotografías”?
5. ¿Qué hace el comando commit?
6. ¿Qué hace git log y status? ¿Se pueden visualizar más bonito y con estilos esos logs?
7. Git checkout y reset