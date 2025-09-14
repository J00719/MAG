# Análisis de Distribución de Especies y Huella Humana en México

Este repositorio contiene un script en R para analizar la distribución espacial de una especie de mamífero en México, evaluando su presencia en Áreas Naturales Protegidas (ANPs), zonas deforestadas y diferentes categorías de huella humana. Además, calcula estadísticas de elevación para las áreas de presencia de la especie.

---

## Descripción detallada del script

Este script realiza un análisis espacial para evaluar la distribución de una especie en México, relacionando su presencia con variables ambientales y antropogénicas como Áreas Naturales Protegidas (ANPs), deforestación, huella humana y elevación. A continuación se explica cada sección del código:

### 1. Carga de librerías

Se cargan múltiples paquetes necesarios para el manejo y análisis de datos espaciales, modelado ecológico y manipulación de datos. Algunos paquetes clave son:

- `sf`, `sp`, `raster`, `terra`, `rgdal`, `rgeos`: para manejo y análisis de datos espaciales vectoriales y raster.
- `kuenm`, `ENMeval`: para modelado de nicho ecológico.
- `dplyr`, `reshape`: para manipulación de datos.
- `beepr`: para notificaciones sonoras al finalizar procesos.

### 2. Limpieza del ambiente

Se eliminan todos los objetos del entorno de trabajo con `rm(list=ls())` para evitar conflictos con datos previos.

### 3. Carga de capas espaciales

Se leen shapefiles y raster que contienen información geográfica relevante para el análisis:

- **Áreas Naturales Protegidas (ANPs)**: polígonos que representan zonas protegidas en México.
- **Zonas deforestadas**: polígonos que indican áreas con pérdida de cobertura forestal.
- **Categorías de huella humana**: cuatro capas que representan diferentes niveles de transformación humana en el territorio (no transformado, baja, media y alta huella).
- **Modelo Digital de Elevación (DEM)**: raster con valores de elevación para todo México.
- **Mapa de distribución de la especie**: raster binario donde 1 indica presencia y 0 ausencia de la especie en cada píxel.

Cada capa se carga desde un directorio local especificado.

### 4. Análisis de distribución general de la especie

Se calcula la cantidad total de píxeles con presencia (valor 1) en el mapa de distribución de la especie. Esto representa el área total ocupada por la especie en el mapa.

### 5. Análisis de distribución en zonas deforestadas

- Se recorta el mapa de la especie para que coincida con la extensión espacial de la capa de deforestación.
- Se enmascara para conservar solo los píxeles dentro de las zonas deforestadas.
- Se calcula el número de píxeles con presencia dentro de estas zonas, lo que indica cuánto del área ocupada por la especie está en zonas deforestadas.

### 6. Análisis de distribución según categorías de huella humana

Para cada categoría (no transformado, baja, media, alta):

- Se recorta y enmascara el mapa de la especie con la capa correspondiente.
- Se calcula el número de píxeles con presencia dentro de cada categoría.
- Estos valores permiten evaluar cómo la especie se distribuye en relación con diferentes niveles de impacto humano.

El valor para la categoría "Muy Alto" se calcula externamente en Excel y no en este script.

### 7. Análisis de distribución en Áreas Naturales Protegidas (ANPs)

- Se recorta y enmascara el mapa de la especie con la capa de ANPs.
- Se calcula el número de píxeles con presencia dentro de las ANPs.
- Esto permite evaluar qué proporción del área ocupada por la especie está protegida.

### 8. Análisis de elevación de la especie

- Se convierten los píxeles con presencia en puntos espaciales.
- Se extraen los valores de elevación del DEM para cada punto de presencia.
- Se calculan la media y desviación estándar de elevación para la especie.
- Estos valores resumen la altitud típica donde se encuentra la especie y pueden ser útiles para análisis ecológicos y conservación.

---

## Requisitos

El script utiliza las siguientes librerías de R:

```r
install.packages(c("rgbif", "TeachingDemos", "dismo", "sp", "sf", "raster", "rgeos", "maptools", "rgdal", "terra", "usdm", "ENMeval", "foreign", "spocc", "corrplot", "XML", "dplyr", "reshape", "beepr"))
install.packages("remotes")
remotes::install_github("marlonecobos/kuenm")
# Análisis de Distribución de Especies y Huella Humana en México

