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

### Objetivos
Con nuestro programa pretendemos mostrar cuáles son los tipos de proyectos que más triunfan y los que menos triunfan,y poder servir de guía a las personas que están interesados en proponer un proyecto.
... más cosas ...

### Funcionamiento del código
Nuestro proyecto se compone de tres scripts, dos de ellos programados en Python y uno en Scala. En todos utilizamos el algoritmo de map-reduce sobre Spark. Para el correcto funcionamiento de ellos **necesitaremos tener descargado el fichero csv** que contiene los datos de los proyectos, descargables en este enlace (también se encuentran en el repositorio).

#### Script 1
El primer script tiene el objetivo de encontrar **cuáles son los tipos de proyectos que más funcionan**. Para ello, limpia el csv, obtiene todos los proyectos que han llegado a completarse al 100%, calcula sus beneficios, y los agrupa por categoría. Finalmente, el script genera dos ficheros de salida. El primero, PromedioExito, muestra las categorías con más porcentaje de éxito, mientras que el segundo, Media_Ganancias, muestra cuáles son las categorías que generan más ganancias. Para ejecutar el script basta con ejecutar en nuestra máquina virtual
```
spark-submit kickstarter1.py
```

#### Script 2
El segundo script se encuentra desarrollado en Scala. Este script muestra cuáles son los países que más donaciones reciben y en qué tipo de categoría. Para ello, filtramos los proyectos los proyectos que han recaudado más de 1 millón de dólares y mostramos en un fichero de salida el país, el tipo de proyecto, la cantidad pedida y la cantidad obtenida de cada proyecto. Para ejecutar el script hay que escribir en la terminal de nuestra máquina virtual el comando:
```
spark-submit kickstarter2.scala
```

#### Script 3
El tercer y último script de nuestro proyecto está desarrollado en Python, y utiliza la librería de Spark SQL. Este Script nos muestra la media de donantes que tiene cada categoría. 

### Autores del proyecto
El proyecto ha sido realizado por los estudiantes: 
- Joaquín Barrio Lottmann
- Alejandro Mendoza Silva
- Pablo Miranda Torres
- Pablo de Torre Barrio, 
pertenecientes a la facultad de informática de la Universidad Complutense de Madrid.

