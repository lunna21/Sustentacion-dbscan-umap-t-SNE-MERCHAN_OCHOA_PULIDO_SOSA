# Sustentación – DBSCAN con Reducción Dimensional (t-SNE y UMAP)
**MERCHAN • OCHOA • PULIDO • SOSA**

---
<p align="center"> <img src="https://img.shields.io/badge/Proyecto-Académico-blue?style=flat-square"> <img src="https://img.shields.io/badge/Estado-En%20Desarrollo-yellow?style=flat-square"> <img src="https://img.shields.io/badge/Algoritmos-DBSCAN%20%7C%20UMAP%20%7C%20tSNE-red?style=flat-square"> <img src="https://img.shields.io/badge/Python-3.10+-green?style=flat-square&logo=python"> <img src="https://img.shields.io/badge/Licencia-Académica-lightgrey?style=flat-square"> </p>
---
## Objetivo del Proyecto

Implementar y comparar técnicas de reducción dimensional (t-SNE y UMAP) aplicadas a clustering basado en densidad (DBSCAN), mediante experimentación sistemática de hiperparámetros y evaluación cuantitativa de resultados.

---

## Descripción del Trabajo

### Fase 1: Configuración Inicial y Exploración de Datos
Carga del dataset Iris y análisis exploratorio inicial. Se realizan visualizaciones de distribuciones, correlaciones y detección de outliers para comprender la estructura de los datos.

**Objetivo**: Familiarización con el dataset y preparación para el preprocesamiento.

### Fase 2: Preprocesamiento de Datos
Estandarización de características mediante StandardScaler para transformar los datos con media cero y desviación estándar uno. Se verifica la correcta aplicación de la transformación y se comparan distribuciones antes y después.

**Objetivo**: Preparar los datos para técnicas sensibles a escala como t-SNE, UMAP y DBSCAN.

### Fase 3: Reducción Dimensional con t-SNE + Clustering con DBSCAN
Experimentación con diferentes valores de perplexity (5, 15, 30, 50) para t-SNE, evaluando KL Divergence, Silhouette Score y tiempo de ejecución. Se compara t-SNE con PCA en términos de preservación de estructura local versus global mediante correlación de Spearman. Selección manual del perplexity óptimo seguida de aplicación de DBSCAN con determinación de eps mediante k-distance graph.

**Objetivo**: Evaluar el impacto de hiperparámetros en la calidad de reducción dimensional y justificar la selección de parámetros para DBSCAN.

### Fase 4: Reducción Dimensional con UMAP + Clustering con DBSCAN
Experimentación variando n_neighbors (5, 15, 30, 50) y min_dist (0.0, 0.1, 0.25, 0.5). Evaluación de preservación de vecindarios mediante k-NN accuracy, que mide qué tan bien se mantienen los vecinos cercanos antes y después de la reducción. Selección manual de hiperparámetros y aplicación de DBSCAN con cálculo de métricas internas y externas, incluyendo accuracy mediante asignación por mayoría.

**Objetivo**: Evaluar preservación de estructura local y global en UMAP, comparando su desempeño con t-SNE para clustering.

### Fase 5: Comparación Final - t-SNE vs UMAP
Comparación cuantitativa mediante 13 métricas: tiempo de ejecución, k-NN accuracy, número de clusters, porcentaje de ruido, accuracy, silhouette score, Calinski-Harabasz, Davies-Bouldin, Adjusted Rand Index, Normalized Mutual Information, homogeneity, completeness y V-measure. Visualización lado a lado de resultados.

**Objetivo**: Determinar cuál método de reducción dimensional es más apropiado para clustering con DBSCAN según diferentes criterios de evaluación.

---

## Estructura del Proyecto

```
Sustentacion-dbscan-umap-t-SNE/
│
├── notebooks/
│   └── sustentacion.ipynb       # Notebook principal con todas las fases
│
├── requirements.txt              # Dependencias del proyecto
└── README.md                     # Este archivo
```

---

## Tecnologías Utilizadas

**Librerías principales**:
- scikit-learn: TSNE, PCA, DBSCAN, NearestNeighbors, métricas
- umap-learn: Reducción dimensional UMAP
- numpy, pandas: Manipulación de datos
- scipy: Cálculos estadísticos (Spearman, distancias)
- matplotlib, seaborn: Visualización

**Entorno de ejecución**: Google Colab, Jupyter Notebook, JupyterLab o VS Code

---

## Guía de Ejecución

### Opción 1: Google Colab (Recomendado)

1. Acceder a Google Colab: https://colab.research.google.com/
2. Subir el archivo `notebooks/sustentacion.ipynb`
3. Ejecutar la primera celda para instalar dependencias:
   ```python
   !pip install umap-learn
   ```
4. Ejecutar las celdas secuencialmente

**Nota**: Colab ya incluye numpy, pandas, scikit-learn, matplotlib y seaborn preinstalados.

### Opción 2: Entorno Local

#### Crear entorno virtual:
```bash
python -m venv venv

# Activar entorno
venv\Scripts\activate      # Windows
source venv/bin/activate   # Linux/Mac
```

#### Instalar dependencias:
```bash
pip install -r requirements.txt
```

#### Ejecutar notebook:
```bash
jupyter notebook notebooks/sustentacion.ipynb
# o
jupyter lab notebooks/sustentacion.ipynb
```

### Consideraciones Importantes

**Selección manual de parámetros**:
- En Fase 3, ajustar `PERPLEXITY_SELECCIONADO` según tabla comparativa
- En Fase 4, ajustar `N_NEIGHBORS_SELECCIONADO` y `MIN_DIST_SELECCIONADO` según experimentación

Las tablas comparativas en cada fase proporcionan métricas cuantitativas para tomar decisiones informadas sobre los hiperparámetros.

---

## Autores

- Merchan Mesa, Danna Xiomara
- Ochoa Pinilla, Juan David
- Pulido Arias, Ibeth Stefanny
- Sosa Espitia, Lunna Karina

---
