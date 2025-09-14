# Análisis de Distribución de Especies y Huella Humana en México

Este repositorio contiene un script en R para analizar la distribución espacial de especies de mamíferos en México, evaluando su presencia en Áreas Naturales Protegidas (ANPs), zonas deforestadas y diferentes categorías de huella humana. Además, calcula estadísticas de elevación para las áreas de presencia de la especie.

---

## Contenido

- `analisis_distribucion.R` (o el nombre que le des al script): Código en R para realizar el análisis espacial.
- Capas espaciales (shapefiles y raster) necesarias para el análisis (no incluidas en el repositorio, deben descargarse y ubicarse en las rutas indicadas).

---

## Requisitos

El script utiliza las siguientes librerías de R:

- `rgbif`
- `TeachingDemos`
- `dismo`
- `sp`
- `sf`
- `raster`
- `rgeos`
- `maptools`
- `rgdal`
- `terra`
- `usdm`
- `ENMeval`
- `foreign`
- `spocc`
- `corrplot`
- `XML`
- `dplyr`
- `reshape`
- `beepr`
- `kuenm`
- `remotes` (para instalar `kuenm` desde GitHub)

Puedes instalar las librerías necesarias con:

```r
install.packages(c("rgbif", "TeachingDemos", "dismo", "sp", "sf", "raster", "rgeos", "maptools", "rgdal", "terra", "usdm", "ENMeval", "foreign", "spocc", "corrplot", "XML", "dplyr", "reshape", "beepr"))
install.packages("remotes")
remotes::install_github("marlonecobos/kuenm")
