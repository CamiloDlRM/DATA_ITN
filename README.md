# DATA_ITN

Proyecto de análisis de datos abiertos de salud pública en Colombia, desarrollado para el concurso de datos abiertos del gobierno.

## Descripción

Este proyecto analiza la relación entre enfermedades de interés en salud pública y condiciones ambientales en tres regiones de Colombia: Bucaramanga (Santander), Bogotá y Medellín (Antioquia).

El objetivo principal fue recolectar y procesar datos epidemiológicos para alimentar un modelo de aprendizaje no supervisado (K-Means) que permita determinar la ubicación óptima para la instalación de hospitales verdes en las ciudades analizadas, priorizando las zonas con mayor concentración de casos.

Se trabajó con datos del sistema SIVIGILA y portales de datos abiertos municipales para estudiar:

- **Dengue**: Casos por comuna, distribución demográfica, sintomatología
- **Cáncer**: Incidencia por localidad, tendencias temporales
- **Tuberculosis**: Pulmonar y extrapulmonar, distribución geográfica
- **Residuos**: Generadores de residuos peligrosos y su posible correlación con zonas de alta incidencia

## Datasets

Archivos y Descripción 

- `Dengue__Dengue_grave_y_mortalidad_por_dengue_municipio_de_Bucaramanga_*.csv` | Casos de dengue en Bucaramang(2015-2022) 

- `sivigila_denguegrave.csv` | Dengue grave en Antioquia
- `sivigila_cancer18.csv` | Cáncer en menores de 18 años 
- `osb_enfercronicas-ticancermenores18anos.csv` | Enfermedades crónicas - cáncer infantil
- `sivigila_tbpulmonar.csv` | Tuberculosis pulmonar Antioquia 
- `sivigila_tbextra.csv` | Tuberculosis extrapulmonar Antioquia
- `Grandes_Generadores__de_Residuos_-_UAESP_*.csv` | Generadores de residuos Bogotá
- `Residuos_peligrosos_por_municipio_*.csv` | Residuos peligrosos por municipio

## Análisis realizados

### Visualizaciones
- Gráficos de distribución por sexo y grupo etario
- Mapas de calor por comunas/localidades
- Series temporales de incidencia
- Gráficos de barras por zonas vulnerables

### Mapas interactivos
Se generaron mapas con Folium mostrando la distribución geográfica de casos por barrio, usando geocodificación con Nominatim (OpenStreetMap).

### Análisis con IA
Integración con Google Gemini para generar análisis contextualizados de la situación epidemiológica por localidad, considerando factores geográficos, socioeconómicos y ambientales.

### Ubicación óptima de hospitales verdes
Implementación de K-Means para identificar ubicaciones estratégicas donde instalar hospitales verdes, basándose en la concentración geográfica de casos. El modelo agrupa los barrios por coordenadas y cantidad de casos, y retorna el centroide del cluster más afectado como ubicación sugerida.

## Tecnologías

- Python 3
- Pandas, NumPy
- Matplotlib, Seaborn
- Folium (mapas)
- Scikit-learn (K-Means)
- Google Generative AI (Gemini)
- Google Colab

## Uso

El notebook `DataITN.ipynb` puede ejecutarse directamente en Google Colab. Los datasets deben estar en el directorio `/content/` o ajustar las rutas según corresponda.

## Fuentes de datos

- [Datos Abiertos Colombia](https://www.datos.gov.co/)
- [SIVIGILA - Instituto Nacional de Salud](https://www.ins.gov.co/Direcciones/Vigilancia/Paginas/SIVIGILA.aspx)
- [Datos Abiertos Bucaramanga](https://www.datos.gov.co/browse?q=bucaramanga)
- [Datos Abiertos Bogotá](https://datosabiertos.bogota.gov.co/)
