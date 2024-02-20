# Introducción a la Ciencia de Datos con R

## Treball pràctic Grado Psicología

### Febrero, 2024

### David Leiva Ureña

#### Departmento Psicología Social y Psicología Cuantitativa, Universidad de Barcelona

---

<a rel="license" href="http://creativecommons.org/licenses/by/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by/4.0/88x31.png" /></a><br />Este trabajo se ha realizado bajo licencia <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 International License</a>.

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.8152802.svg)](https://doi.org/10.5281/zenodo.10683620)

## Sobre el trabajo práctico

Este curso se ha pensado como una suerte de taller de tipo práctico en el que se introducirá a los estudiantes en la Ciencia de Datos mediante el software estadístico de libre distribución R. Puesto que se trata de un lenguaje de programación y su aprendizaje puede resultar costoso, se utilizarán numerosos ejemplos que faciliten el dominio de la sintaxis básica. A lo largo de las sesiones se capacitará a los participantes a ser autónomos en aquellas técnicas básicas relacionadas con la visualización de datos, la modelización estadística así como en la elaboración de informes técnicos con herramientas de R en combinación con programas como $\LaTeX$ o *Markdown*. Dado el carácter eminentemente práctico del curso, éste debería realizarse en aula de ordenadores o bien que cada estudiante lleve un ordenador portátil.

### Programa del curso:

1. Primeros pasos con R (2h)
 - Instalación y ejecución de R
 - RStudio: una IDE para R
 - Introducción al *tidyverse*

2. Visualización de datos con R (2h)
 - Paquetes gŕaficos básicos 
 - *ggplot2* y otros paquetes

3. Modelización estadística con R (1.30h)
 - Ejemplos de modelos estadísticos
 - Modelización con tidymodels

4. Investigación reproducible con R (3h)
 - Generación de documentos con *knitr* y *RMarkdown*
 - Desarrollo de aplicaciones dinámicas con Shiny

## Sobre el instructor

Me llamo David Leiva y soy profesor Agregado (Contratado Doctor) en el Departamento de Psicología Social y Psicología Cuantitativa. Imparto cursos de grado, máster y doctorado en Estadística, Técnicas de Investigación, Modelización Estadística, Ciencia de Datos y Matemáticas Aplicadas. Mis principales intereses de investigación son el análisis de datos diádicos, la modelización y el software estadístico. También he participado en numerosos trabajos en campos como la Psicología de las Organizaciones, la Neuropsicología, la Psicogerontología o la Biología, entre otros. Puedes encontrar mi CV en el siguiente [enlace](https://github.com/DLEIVA/CV/blob/main/CV_DLU_2023.pdf).

## Preparación previa

Por favor, asegúrate que tienes al menos la versión 4.2 de R instalada &mdash; *y preferiblemente la versión 4.3* &mdash; (pues dependiendo de los paquetes que se utilicen requieren versiones actualizadas del software). Nótese que R y RStudio son dos programas distintos: no es suficiente tener actualizada la versión de RStudio pues R se va actualizando independientemente de forma periódica.

Para comprobar la versión de R instalada, puedes ejecutar

```r
version
```

en R y leer en el apartado `version.string` (o las secciones `major` y `minor`).

Si la versión instalada de R es < 4.2.0, necesitarás actualizar el programa previa descarga e instalación. Para descargar R ve a la página [CRAN Download](https://cran.r-project.org/) y selececciona el enlace apropiado según tu sistema operativo:

* [Windows](https://cran.r-project.org/bin/windows/)
* [MacOS X](https://cran.r-project.org/bin/macosx/)
* [Linux](https://cran.r-project.org/bin/linux/)

A lo largo de las sesiones vamos a utilizar diversos paquetes de R que necesitarás tener instalados. Antes del inicio del curso, ejecuta el siguiente código que actualizará los paquetes instalados e instalará los paquetes necesarios durante el curso:

```r
# Actualiza paquetes
update.packages(ask = FALSE, checkBuilt = TRUE)

# Algunos paquetes a instalar
pkgs <- c("tidyverse", "readxl", "haven", "usethis", "learnr", "kableExtra", "magick","gridExtra", "dslabs", "patchwork", "plotly", "gganimate", "car", "effects", "gapminder", "tidymodels", "modelr", "broom", "purrr", "tinytex", "knitr","xtable", "lorem"," flexdashboard")

# Instalar esos paquetes
install.packages(pkgs, Ncpus = 4) # especifica Ncpus según nº CPUs disponibles en tu ordenador
```

*Conviene trabajar previamente estos 2 recursos para un buen aprovechamiento de las sesiones.*

[Instalación de R y RStudio](https://learnr-examples.shinyapps.io/ex-setup-r/)

[Programación básica con R](https://posit.cloud/learn/primers/1.2)

# Materiales del curso

## Desde Github

Para descargar los materiales del curso puedes abrir RStudio y ejecutar `use_course()` tal y como se muestra a continuación:

```r
usethis::use_course("DLEIVA/TreballPracticCienciaDatosR")
```

Una vez ejecutada la instrucción se os preguntará si queréis descargar los materiales del curso en el directorio `~/Desktop` (en este caso, `~/` se refiere a vuestro directorio raíz). Presionad el número indicado y presionad la tecla <kbd>Enter</kbd> para mostrar vuestro acuerdo. Los materiales se descargarán como un archivo zip y se extraerán automáticamente.

Tras la extracción, se os preguntará si queréis eliminar el archivo `.zip` descargado. Seleccionad la opción que creáis oportuna.

Finalmente, tras responder a esta cuestión, Rstudio cargará el proyecto del taller en una nueva sesión de RStudio. Una vez abierto el proyecto, podéis cerrar la otra ventana de RStudio (en la que habéis ejecutado la instrucción `use_course()`).

### Descarga directa

Si no estáis utilizando RStudio o sabéis lo que hacéis, podeís descargar el archivo zip directamente desde <https://github.com/DLEIVA/TreballPracticCienciaDatosR.git>. La extracción de archivos y el inicio en el directorio correcto correrá entonces a vuestro cargo.

### OTROS RECURSOS

**Cursos R Básicos**

https://www.codecademy.com/learn/learn-r

https://www.codecademy.com/learn/learn-statistics-with-r

https://www.codecademy.com/learn/r-for-programmers


**Cursos de tidyverse**

https://www.coursera.org/specializations/tidyverse-data-science-r

https://www.coursera.org/learn/tidyverse

https://www.coursera.org/learn/tidyverse-data-wrangling

https://www.coursera.org/learn/tidyverse-visualize-data


**Bibliografía recomendada**

Gandrud, C. (2020). Reproducible research with R and RStudio (3rd. Ed.). Boca
Raton, FL: Chapman & Hall/CRC.

Murrell, P. (2019). R graphics. (3rd. Ed.). Boca Raton, FL: Chapman & Hall/CRC.

Wilke, C. O. (2019). Fundamentals of Data Visualization. (2nd. Ed.). Sebastopol,
CA: O’Reilly.

Whickam, H, Grolemund, G. (2023). R for Data Science. (2nd. Ed.). Sebastopol,
CA: O’Reilly.

Xie, Y. (2017). Dynamic documents with R and knitr (2nd. Ed.). Boca Raton, FL:
Chapman & Hall/CRC.

Xie, Y., Allaire, J. J., & Grolemund, G. (2018). RMarkdown: The definitive guide
(2nd. Ed.). Boca Raton, FL: Chapman & Hall/CRC.