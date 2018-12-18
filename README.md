## Analíticas de Kickstarter 

### Introducción
[Nuestro proyecto](https://github.com/PabloDeTorre/StartupsAnatlytics) consiste en el tratamiento y análisis de datos de la plataforma Kickstarter. [Kickstarter](https://www.kickstarter.com/?lang=es) es una plataforma de financiamiento para proyectos creativos de todo tipo: desde películas, juegos y música hasta arte, diseño y tecnología. Kickstarter está lleno de proyectos ambiciosos, innovadores e imaginativos que se hacen realidad gracias al apoyo directo de otras personas. 

### Obtención de los datos
Los datos que vamos a tratar han sido extraídos de [Kaggle](https://www.kaggle.com/kemical/kickstarter-projects#ks-projects-201801.csv). El dataset es un archivo de formato csv que contiene 15 columnas y más de 300k filas, en la que cada una indica los datos de un proyecto, en cuyas columnas encontramos: 
- ID: código numérico que representa el ID del proyecto
- name: nombre del proyecto.
- **category**: categoría (o subcategoría) a la que pertenece el proyecto.
- main_category: categoría que pertenece de una manera más genérica
- currency: moneda
- deadline: fecha límite de financiación
- goal: objetivo (en la moneda seleccionada)
- launched: fecha de publicación
- pledged: cantidad contribuida
- **state**: estado del proyecto(calcelado, exitoso, etc.)
- **backers**: número de patrocinadores
- **country**: país de origen
- usd pledged: cantidad obtenida (en dólares)
- **usd_pledged_real**: cantidad real obtenida (en dólares).
- **usd_goal_real**: cantidad objetivo (en dólares). 

Las columnas marcadas en negrita son las que nos resultarán útiles para nuestro proyecto. Para la ejecución del script no serán necesarias todas las columnas, utilizaremos las que consideremos necesarias para cumplir nuestros objetivos.

### Objetivos
Con nuestro programa pretendemos mostrar ciertas estadísticas que resultarán útiles para las personas interesadas en crear un proyecto o para las que quieren saber qué proyectos son más existosos. Nuestros objetivos son:
- Mostrar qué tipos de proyectos tienen mayor porcentaje de éxito,
- Analizar qué países suelen recibir mayores donaciones, y sus respectivas cantidades.
- Calcular qué categorías son las que reciben mayor cantidad de donaciones por patrocinador.

### Funcionamiento del código
Nuestro proyecto se compone de tres scripts, dos de ellos programados en Python y uno en Scala. En todos utilizamos el algoritmo de map-reduce sobre Spark. Para el correcto funcionamiento de ellos **necesitaremos tener descargado el fichero csv** que contiene los datos de los proyectos, descargable en este [enlace](https://www.kaggle.com/kemical/kickstarter-projects#ks-projects-201801.csv) (también se encuentra en el repositorio).

#### Script 1 - Éxito de proyectos
El primer script tiene el objetivo de encontrar **cuáles son los tipos de proyectos que más funcionan**. Para ello, limpia el csv, obtiene todos los proyectos que han llegado a completarse al 100%, calcula sus beneficios, y los agrupa por categoría.Para ejecutar el script basta con ejecutar en nuestra máquina virtual:
```
spark-submit kickstarter1.py
```
El script generará dos ficheros de salida. El primero, PromedioExito, muestra las categorías ordenadas por porcentaje de éxito, 
mientras que el segundo, Media_Ganancias, muestra cuáles las categorías ordenadas por mayor número de ganancias. Ambos ficheros se muestran en el formato:
```
PorcentajeÉxito,MediaGanancias,Categoría,

```

![](https://github.com/pablo-mirtor/Kickstarter-Analytics/blob/master/resources/script11pic.PNG)

![](https://github.com/pablo-mirtor/Kickstarter-Analytics/blob/master/resources/script12pic.PNG)

#### Script 2 - Países más financiados
El segundo script se encuentra desarrollado en Scala. Este script muestra cuáles son los países que más donaciones reciben y en qué tipo de categoría. Para ello, filtramos los proyectos los proyectos que han recaudado más de 1 millón de dólares y mostramos en un fichero de salida el país, el tipo de proyecto, la cantidad pedida y la cantidad obtenida de cada proyecto. Para ejecutar el script es necesario disponer de la herramienta IntelliJ. El script generará una salida que muestre:
```
País,Categoría,CantidadObjetivo,CantidadObtenida
```

![](https://github.com/pablo-mirtor/Kickstarter-Analytics/blob/master/resources/script2pic.PNG)

#### Script 3 - Media de donaciones
El tercer y último script de nuestro proyecto está desarrollado en Python, y utiliza la librería de Spark SQL. Este Script nos muestra la media de donantes que tiene cada subcategoría, y la media de donación por donante (ordenado de mayor a menor). Para ejecutar el script hay que escribir en la terminal de nuestra máquina virtual el comando:
```
spark-submit kickstarter3.py
```
Generará una salida que muestre
```
Subcategoría,mediaDonado,mediaDonadores,mediaDonacionPorDonante
```

![](https://github.com/pablo-mirtor/Kickstarter-Analytics/blob/master/resources/script3pic.PNG)

### Conclusiones
Hemos sido capaces de tratar con estos datos del dataset, a pesar de habernos encontrado con problemas con el formato de ciertos caracteres en el fichero csv. Tras ejecutar los scripts, hemos podido concluir estos hechos sobre Kickstarter:
- Los videojuegos son los proyectos que más éxito tienen y cantidad recaudan.
- Estados Unidos, el país que más financiación obtiene.
- Las herramientas de fabricación, la subcategoría que recibe mayor cantidad por contribuyente.

También podríamos afirmar que nuestro proyecto puede ser útil para analizar futuros datasets de Kaggle, y se podrá ir estudiando cómo evoluciona el mundo de las donaciones.


### Autores del proyecto
El proyecto ha sido realizado como proyecto final para la asignatura Cloud y Big Data, por los siguientes estudiantes pertenecientes a la facultad de informática de la Universidad Complutense de Madrid: 
- Joaquín Barrio Lottmann
- Alejandro Mendoza Silva
- Pablo Miranda Torres
- Pablo de Torre Barrio

### Enlace al repositorio del proyecto
[Kickstarter-Analytics](https://github.com/PabloDeTorre/StartupsAnatlytics)
