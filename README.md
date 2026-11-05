# Clustering: K-Means, DBSCAN y Clustering Jerárquico

Trabajo **Semana 11** 

*Introducción a Machine Learning* (CAD2092023103) · Universidad de Cundinamarca · Especialización en Analítica y Ciencia de Datos.

**Autor:** Brayan Yesid Vega Niño · **Fecha:** 5 de noviembre de 2026

## Objetivo

Aplicar y comparar tres algoritmos de clustering sobre datasets de Scikit-learn, justificando el preprocesamiento, los hiperparámetros y el número de clusters, evaluando con métricas internas (Silhouette, Davies-Bouldin y Calinski-Harabasz) e interpretando los grupos. **Las etiquetas conocidas no se usan para construir los clusters**; solo se emplean después, como referencia opcional (Adjusted Rand Index).

## Algoritmos y datasets

| Ejercicio | Algoritmo | Dataset | Resultado principal |
|---|---|---|---|
| 1 | K-Means | Wine (178 × 13) | K = 3 · Silhouette 0,285 · Davies-Bouldin 1,389 · Calinski-Harabasz 70,94 |
| 2 | DBSCAN | Make Moons (500 × 2, `noise=0.07`, `random_state=42`) | eps = 0,30 · min_samples = 5 · 2 clusters · 0 % ruido · Silhouette 0,386 |
| 3 | Clustering jerárquico (Ward) | Iris (150 × 4) | K = 2 (corte ≈ 20) · Silhouette 0,577 · Davies-Bouldin 0,592 · Calinski-Harabasz 240,2 |

Las métricas de cada fila corresponden a su propio dataset y **no son comparables entre filas**. El notebook incluye la tabla comparativa completa (sección 4) y contrastes sobre el mismo dato (DBSCAN vs. K-Means en Moons; jerárquico vs. K-Means en Iris).

## Estructura del repositorio

```
/notebooks   Semana11_Clustering_Brayan_Vega.ipynb   
/data        wine.csv · moons.csv · iris.csv         
/figures     figuras PNG generadas por el notebook
/informe     Informe_Clustering_Brayan_Vega.pdf      
README.md
requirements.txt
```

## Librerías principales

`numpy`, `pandas`, `matplotlib`, `scikit-learn`, `scipy` (versiones mínimas en `requirements.txt`). Probado con Python 3.12, scikit-learn 1.9, SciPy 1.18, pandas 3.0 y matplotlib 3.11.

## Cómo ejecutar

1. Clonar el repositorio y entrar a la carpeta.
2. Instalar dependencias: `pip install -r requirements.txt`
3. Abrir `notebooks/Semana11_Clustering_Brayan_Vega.ipynb` con Jupyter (`jupyter notebook`) o subirlo a Google Colab.
4. Ejecutar todas las celdas en orden (*Run all*). Las figuras se guardan en `/figures` y los datos de ejemplo en `/data`.

**Reproducibilidad:** la semilla está fijada (`SEED = 42`) y los clusters se renumeran con un criterio fijo (p. ej. de mayor a menor prolina media en Wine), de modo que el etiquetado no cambia entre ejecuciones.
