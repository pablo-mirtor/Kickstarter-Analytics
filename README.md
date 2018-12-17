## Analíticas de Kickstarter 

### Introducción
Nuestro proyecto consiste en el tratamiento de datos de la plataforma Kickstarter. [Kickstarter](https://www.kickstarter.com/?lang=es) es una plataforma de financiamiento para proyectos creativos de todo tipo: desde películas, juegos y música hasta arte, diseño y tecnología. Kickstarter está lleno de proyectos ambiciosos, innovadores e imaginativos que se hacen realidad gracias al apoyo directo de otras personas. 

### Obtención de los datos
Los datos que vamos a tratar han sido extraídos de Kaggle. El dataset es un archivo de formato csv que contiene 15 columnas y más de 300k filas, en la que cada una indica los datos de un proyecto, en cuyas columnas encontramos: 
- ID: código numérico que representa el ID del proyecto
- name: nombre del proyecto.
- category: categoría (o subcategoría) a la que pertenece el proyecto.
- main_category: categoría que pertenece de una manera más genérica
- currency: moneda
- deadline: fecha límite de financiación
- goal: objetivo (en la moneda seleccionada)
- launched: fecha de publicación
- pledged: cantidad contribuida
- state: estado del proyecto(calcelado, exitoso, etc.)
- backers: número de patrocinadores
- country: país de origen
- usd pledged: cantidad obtenida (en dólares)
- usd_pledged_real: cantidad real obtenida (en dólares).
- usd_goal_real: cantidad objetivo (en dólares). 

Para la ejecución del script no serán necesarias todas las columnas, utilizaremos las que consideremos necesarias para buscar nuestros objetivos.

### Integrantes del grupo
El proyecto ha sido realizado por los estudiantes Pablo de Torre Barrio, Pablo Miranda Torres, Alejandro, y Joaquín, pertenecientes a la facultad de informática de la Universidad Complutense de Madrid.

### Objetivos
Con nuestro programa pretendemos mostrar cuáles son los tipos de proyectos que más triunfan y los que menos triunfan,y poder servir de guía a las personas que están interesados en proponer un proyecto.
... más cosas ...

### Funcionamiento del código
Nuestro proyecto se compone de tres scripts, dos de ellos programados en Python y uno en Scala. En todos utilizamos el algoritmo de map-reduce sobre Spark. Para el correcto funcionamiento de ellos **necesitaremos tener descargado el fichero csv** que contiene los datos de los proyectos, descargables en este enlace (también se encuentran en el repositorio).

#### Script 1
El primer script tiene el objetivo de encontrar **cuáles son los tipos de proyectos que más funcionan**. Para ello, limpia el csv, obtiene todos los proyectos que han llegado a completarse al 100%, calcula sus beneficios, y los agrupa por categoría. Finalmente, el script genera dos ficheros de salida. El primero, PromedioExito, muestra las categorías con más porcentaje de éxito, mientras que el segundo, Media_Ganancias, muestra cuáles son las categorías que generan más ganancias. Para ejecutar el script basta con ejecutar en nuestra máquina virtual
```
`spark-submit kickstarter1.py`
```

#### Script 2
El segundo script
#### Script 3

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

### Ejecución
El script está programado en Python, en el cual usamos la librería de Spark. El objetivo es ejecutarlo sobre una máquina virtual de Amazon.
... explicar cómo ha ido la ejecución...


### Conclusiones
Como se puede ver los proyectos del tipo A suelen ser bastante exitosos, mientras que los del tipo B no...


### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for




