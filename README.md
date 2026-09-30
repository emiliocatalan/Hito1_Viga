# Evaluación 1 - Hito 1: Análisis carga-deflexión de una viga

## Objetivo

Este proyecto analiza la relación carga-deflexión de una viga simplemente apoyada de sección rectangular sometida a una carga puntual centrada. El objetivo es comparar los datos de deflexión entregados con la predicción lineal elástica obtenida mediante la teoría de Euler-Bernoulli y documentar el procedimiento de manera reproducible.

## Estructura del proyecto

El repositorio se organiza de la siguiente manera:

- `Data/`: contiene los archivos originales de entrada.
  - `datos_viga.csv`
  - `parametros_viga.xlsx`
  - `README_datos.md`

- `Analysis/`: contiene la planilla de análisis.
  - `analisis_viga.xlsx`

- `Figures/`: contiene las figuras utilizadas.
  - `esquema_viga.png`: esquema original proporcionado para la actividad, conservado sin modificaciones.
  - `carga_deflexion.png`: gráfico generado durante el análisis para comparar la deflexión medida y la teórica.

- `Report/`: contiene los archivos fuente de la nota técnica en LaTeX, el PDF final y una copia de las figuras necesarias para recompilar el informe de manera independiente.
  - `borrador_informe.tex`
  - `main_sections.tex`
  - `bibfile.bib`
  - `nota_tecnica.pdf`
  - `figures/`
    - `esquema_viga.png`
    - `carga_deflexion.png`

La carpeta `Report/figures/` repite las imágenes que también se encuentran en `Figures/` de manera intencional. La carpeta principal `Figures/` almacena las salidas gráficas del análisis, mientras que `Report/figures/` contiene una copia de las imágenes utilizadas por los archivos LaTeX. Esto permite que la nota técnica pueda recompilarse directamente desde la carpeta `Report/` sin depender de rutas externas.

- `USO_IA.md`: contiene la declaración y verificación del uso de inteligencia artificial.

## Datos de entrada

Los datos principales corresponden a:

- carga aplicada;
- deflexión medida en el centro de la viga;
- longitud de la viga;
- ancho y altura de la sección rectangular;
- módulo de elasticidad.

Los archivos originales se mantienen sin modificaciones.

## Procedimiento de análisis

El análisis se realizó en la planilla `Analysis/analisis_viga.xlsx`.

El procedimiento considera:

1. Conversión del módulo de elasticidad de GPa a Pa.
2. Conversión de la carga de kN a N.
3. Cálculo del segundo momento de área de la sección rectangular:

   I = b h^3 / 12

4. Cálculo de la deflexión teórica mediante:

   delta = P L^3 / (48 E I)

5. Conversión de la deflexión de metros a milímetros.
6. Comparación entre la deflexión medida y la teórica.
7. Cálculo de la diferencia relativa.
8. Verificación adicional mediante la comparación entre la pendiente teórica y la pendiente obtenida a partir de los datos medidos.

## Resultados principales

La respuesta carga-deflexión mostró un comportamiento prácticamente lineal.

Para una carga de 40 kN:

- Deflexión teórica: 2,00 mm.
- Deflexión medida: 2,05 mm.

La pendiente teórica fue aproximadamente:

0,05000 mm/kN

La pendiente obtenida a partir de los datos medidos fue aproximadamente:

0,05117 mm/kN

La diferencia relativa entre ambas pendientes fue aproximadamente:

2,33 %.

## Cómo reproducir el análisis

1. Abrir `Data/datos_viga.csv` y `Data/parametros_viga.xlsx` para revisar los datos originales.
2. Abrir `Analysis/analisis_viga.xlsx`.
3. Revisar los parámetros geométricos y las conversiones de unidades.
4. Verificar el cálculo del segundo momento de área.
5. Revisar el cálculo de la deflexión teórica para cada nivel de carga.
6. Comparar los valores medidos y teóricos.
7. Revisar el gráfico `Figures/carga_deflexion.png`.
8. Consultar la nota técnica en la carpeta `Report/`.

## Limitaciones

El análisis utiliza datos sintéticos con fines docentes y considera un comportamiento lineal elástico idealizado. Por lo tanto, no representa necesariamente todos los efectos que podrían presentarse en una estructura real.

## Uso de inteligencia artificial

El uso de inteligencia artificial se encuentra documentado en el archivo `USO_IA.md`.
