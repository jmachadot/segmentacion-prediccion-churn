# Segmentación y Predicción de Churn de Distribuidores de equipos celulares de la empresa de telecomunicaciones Claro en la Región Sur del Perú

Combina técnicas de **Aprendizaje No Supervisado** para segmentar la cartera de clientes y **Aprendizaje Supervisado** para predecir la probabilidad de abandono (Churn), integrando variables exógenas macroeconómicas y sociales.

## Características Principales

* **Ingeniería de Variables (RFM + Exógenas):** Construcción de métricas de Recencia, Frecuencia y Valor Monetario, enriquecidas con indicadores macroeconómicos (Tipo de Cambio) y sociales (Conflictividad en el corredor minero del sur).
* **Segmentación Avanzada (Clustering):** Comparativa de algoritmos (**K-Means, Clustering Jerárquico y Gaussian Mixture Models**) evaluados mediante *Silhouette Score*.
* **Predicción de Churn:** Entrenamiento y evaluación de 6 modelos de clasificación, incluyendo **XGBoost, Gradient Boosting y Random Forest**.
* **Evaluación Rigurosa:** Métricas detalladas (Precision, Recall, F1-Score, AUROC) y visualización de curvas ROC y Matrices de Confusión.

## Tecnologías Utilizadas

* **Lenguaje:** Python
* **Manipulación de Datos:** Pandas, NumPy, OpenPyXL
* **Visualización:** Matplotlib, Seaborn
* **Modelado:** Scikit-learn, XGBoost

## Estructura del Proyecto

1. **Limpieza y Preprocesamiento:**
* Filtrado geográfico (Departamentos del Sur: Cusco, Arequipa, Puno, etc.).
* Eliminación de ruido (SIMs, Chips).
* Creación de variables de entorno (Dólar, Conflictos sociales).


2. **Fase 1: No Supervisada (Perfilamiento):**
* Cálculo de scores RFM.
* Escalado de datos (StandardScaler).
* Determinación de perfiles: *Riesgo*, *Desarrollo*, *VIP*.


3. **Fase 2: Supervisada (Predicción):**
* Definición del Target (Churn = inactividad > 30 días).
* Entrenamiento de modelos de línea base y ensambles.
* Optimización y selección del modelo ganador.



## Resultados del Análisis

### 1. Segmentación de Clientes

Se identificaron 3 clústeres principales basados en el comportamiento de compra:

| Perfil | Características | Estrategia Sugerida |
| --- | --- | --- |
| **Riesgo / Bajo** | Baja frecuencia, ticket bajo, alta recencia. | Campañas de reactivación agresivas. |
| **Medio / Desarrollo** | Compras regulares, ticket promedio. | Upselling y Cross-selling. |
| **VIP** | Alto volumen y valor monetario. | Programas de fidelización exclusivos. |

### 2. Predicción de Fuga

Comparativa de rendimiento de los modelos:

| Modelo | Precision | Recall | F1-Score | AUROC |
| --- | --- | --- | --- | --- |
KNN (5 Vecinos) |	0.8571 |	1.0000 |	0.9231 |	1.0000
Random Forest |	1.0000 |	0.8333 |	0.9091 |	1.0000
XGBoost |	1.0000 |	0.8333 |	0.9091 |	0.9931
Gradient Boosting |	1.0000 |	0.6667 |	0.8000 |	1.0000
SVM (RBF Kernel) |	0.7143 |	0.8333 |	0.7692 |	0.9861
Naive Bayes |	0.7143 |	0.8333 |	0.7692 |	0.8819

## Instalación y Uso

1. Abrir el código en Colab.

2. Copiar el dataset a la ruta de colab "/content/sample_data/Data.xlsx".

3. Clic en Ejecutar Todo.
