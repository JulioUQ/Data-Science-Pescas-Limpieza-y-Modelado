<div align="center">

![Machine Learning](https://img.shields.io/badge/MACHINE_LEARNING-C62828?style=for-the-badge)

# Machine learning sobre la flota pesquera española

Limpieza, análisis exploratorio, clasificación y clustering del registro de la flota pesquera española entre 1987 y 2025.

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white) ![pandas](https://img.shields.io/badge/pandas-150458?style=flat-square&logo=pandas&logoColor=white) ![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat-square&logo=scikitlearn&logoColor=white) ![XGBoost](https://img.shields.io/badge/XGBoost-189FDD?style=flat-square) ![TensorFlow · Keras](https://img.shields.io/badge/TensorFlow_%C2%B7_Keras-FF6F00?style=flat-square&logo=tensorflow&logoColor=white) ![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=flat-square&logo=jupyter&logoColor=white)

<img src="figures/pca_clusters.png" alt="Proyección PCA de los grupos de buques obtenidos con K-means" width="100%" />

<sub>Grupos de buques según sus características técnicas (proyección PCA).</sub>

</div>

---

## Descripción general

Analiza los datos técnico-administrativos de la flota pesquera española, identificados por buque, para estudiar su evolución, estructura y reparto geográfico. Parte del conjunto obtenido en [datos-web-scraping-flota](https://github.com/JulioUQ/datos-web-scraping-flota) y sus resultados alimentan el [dashboard de la flota](https://github.com/JulioUQ/app-dashboard-flota-pesquera).

## Funcionalidades

- **Limpieza:** duplicados, valores vacíos, tipos de dato, separación de columnas compuestas (estado, puerto base) y estandarización de categorías.
- **Calidad de datos:** imputación de ceros y valores ilógicos y detección de valores extremos.
- **Exploración:** edad de los buques, evolución de eslora, arqueo, potencia y material del casco, distribuciones y correlaciones.
- **Clasificación** del arte de pesca con modelos de ensemble (Random Forest, XGBoost, CatBoost) y una red neuronal densa.
- **Clustering** de la flota con K-means.
- **Contrastes de hipótesis:** comunidad autónoma frente a arte de pesca, y eslora frente a arte de pesca.

## Tecnologías y herramientas

| Ámbito | Herramientas |
| --- | --- |
| Datos | pandas, NumPy |
| Modelos | scikit-learn, XGBoost, CatBoost, TensorFlow/Keras |
| Visualización | matplotlib, seaborn |

## Estructura del proyecto

```text
.
├── data/       # Datos extraídos y datos limpios
├── src/        # limpieza-datos_V2.ipynb y Modelado.ipynb
├── figures/    # Gráficos generados
├── output/     # Modelos (.pkl), estadísticas y clusters asignados
├── memoria/    # Memoria del proyecto (PDF)
└── requirements.txt
```

## Instalación y uso

```bash
pip install -r requirements.txt
jupyter lab src/
```

Ejecuta primero `limpieza-datos_V2.ipynb` y después `Modelado.ipynb`.

## Resultados

- Modernización de la flota en los últimos 10–15 años, con buques nuevos más grandes y potentes, junto a una parte importante de buques con más de 30 años.
- Eslora, arqueo y potencia con distribuciones sesgadas a la derecha y relacionadas entre sí, lo que valida los datos y la imputación.
- El arte de pesca depende de la comunidad autónoma y del tamaño del buque.
- Según la memoria, el clasificador alcanza una sensibilidad media del 71 % y un F1 de 0,86; el clustering separa 11 grupos con un coeficiente de silueta de 0,4.
- [Caso de estudio en el portfolio](https://juliouq.github.io/Portfolio-Web---JulioUQ/es/casos/flota-pesquera/).

## Aspectos técnicos destacados

- Pipeline completo, desde los datos extraídos hasta los modelos serializados.
- Proyecto en equipo con Lucas Zamora Vera.

## Autor

**Julio Úbeda Quesada** · Data Scientist

[![Portfolio](https://img.shields.io/badge/Portfolio-0B2545?style=flat-square&logo=astro&logoColor=white)](https://juliouq.github.io/Portfolio-Web---JulioUQ/es/) [![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat-square)](https://www.linkedin.com/in/juliouq/) [![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/JulioUQ)

<sub>Proyecto realizado en el Máster Universitario en Ciencia de Datos. Licencia: GPL-3.0 (ver LICENSE).</sub>
