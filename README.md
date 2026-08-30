# 🥗 Clasificación de Alimentos Antiinflamatorios mediante Machine Learning

## 📌 Descripción del proyecto

Este proyecto aplica técnicas de **Machine Learning supervisado** para clasificar alimentos según su potencial antiinflamatorio, a partir de características nutricionales y composicionales.

El objetivo principal es desarrollar y evaluar diferentes modelos de clasificación, comparar su desempeño y seleccionar el modelo con mejor capacidad predictiva.

El proyecto fue desarrollado como parte de la formación en **Data Analytics con Python**, integrando diferentes etapas del flujo de trabajo de un proyecto de Machine Learning: exploración y preparación de datos, preprocesamiento, entrenamiento, validación, evaluación y selección del modelo final.

---

## 🎯 Objetivo

Construir un modelo de clasificación capaz de identificar la categoría de un alimento a partir de sus características nutricionales.

Para ello se plantearon los siguientes objetivos:

* Explorar y comprender el conjunto de datos.
* Analizar las variables disponibles y su relación con la variable objetivo.
* Realizar la limpieza y preparación de los datos.
* Aplicar técnicas de preprocesamiento.
* Entrenar diferentes algoritmos de clasificación.
* Comparar el rendimiento de los modelos mediante métricas de evaluación.
* Analizar la estabilidad de los resultados mediante validación cruzada.
* Seleccionar el modelo con mejor desempeño.
* Guardar el modelo final para su posible reutilización.

---

## 📊 Flujo del proyecto

El proyecto sigue las siguientes etapas:

```text
Datos
  ↓
Exploración y análisis
  ↓
Limpieza y preparación
  ↓
Preprocesamiento
  ↓
División de datos
  ↓
Entrenamiento de modelos
  ↓
Validación cruzada
  ↓
Evaluación y comparación
  ↓
Selección del mejor modelo
  ↓
Guardado del modelo final
```

---

## 🧹 Preparación de los datos

Antes del entrenamiento de los modelos se realizó un proceso de preparación de los datos que incluyó:

* Exploración inicial del dataset.
* Identificación de variables numéricas y categóricas.
* Revisión de valores faltantes.
* Análisis de la variable objetivo.
* Selección de las variables utilizadas para el modelado.
* Transformación de variables cuando fue necesario.
* Estandarización de las variables numéricas.
* Separación entre variables predictoras (`X`) y variable objetivo (`y`).

Para evitar problemas de fuga de información (*data leakage*) y mantener un flujo reproducible, el preprocesamiento se integró dentro de un **Pipeline de Scikit-learn**.

---

## 🤖 Modelos utilizados

Se entrenaron y compararon diferentes algoritmos de clasificación:

* **Regresión Logística**
* **Árbol de Decisión**
* **Random Forest**
* **Support Vector Machine (SVM)**

La comparación permitió analizar no solamente qué modelo obtuvo el mayor accuracy, sino también la estabilidad de su rendimiento entre diferentes particiones de los datos.

---

## 📈 Evaluación de los modelos

Para evaluar los modelos se utilizó **validación cruzada de 5 folds**.

Las principales métricas analizadas fueron:

* Accuracy promedio.
* Desvío estándar del Accuracy.
* Resultados individuales de cada fold.

El **Accuracy promedio** permite conocer el rendimiento general del modelo, mientras que el **desvío estándar** permite observar qué tan estable es ese rendimiento entre las distintas particiones utilizadas durante la validación.

### Comparación de modelos

| Modelo              | Accuracy promedio | Desvío estándar |
| ------------------- | ----------------: | --------------: |
| Regresión Logística |             0.969 |           0.004 |
| Árbol de Decisión   |            0.881* |               — |
| Random Forest       |                 — |               — |
| SVM                 |                 — |               — |

> *Los valores restantes se encuentran detallados en el notebook. La tabla puede actualizarse con los resultados finales obtenidos durante la ejecución.*

---

## 🏆 Selección del modelo

A partir de la comparación realizada mediante validación cruzada, se seleccionó el modelo que presentó el mejor equilibrio entre:

* rendimiento predictivo;
* estabilidad entre folds;
* capacidad de generalización;
* y adecuación al problema planteado.

La **Regresión Logística** obtuvo un Accuracy promedio de **0.969**, con un desvío estándar de **0.004**, mostrando un rendimiento elevado y estable en las particiones evaluadas.

Resultados por fold:

```text
[0.975, 0.971, 0.964, 0.966, 0.970]

Accuracy promedio: 0.969
Desvío estándar:   0.004
```

---

## 📊 Visualización de resultados

Se generaron visualizaciones para facilitar la comparación del rendimiento de los diferentes modelos.

Entre ellas se incluye un gráfico de barras con:

* Accuracy promedio por modelo.
* Desvío estándar como barra de error.

Esto permite visualizar simultáneamente el rendimiento y la variabilidad de cada algoritmo.

---

## 💾 Guardado del modelo

Una vez seleccionado el modelo final, se realizó su guardado para permitir su reutilización posteriormente sin necesidad de volver a entrenarlo desde cero.

Esto permite utilizar el modelo como punto de partida para futuras predicciones sobre nuevos datos.

---

## 🛠️ Tecnologías utilizadas

### Lenguaje

* Python

### Librerías principales

* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn
* Joblib

### Entorno

* Google Colab
* Jupyter Notebook

---

## 📁 Estructura del repositorio

```text
Clasificacion-de-Alimentos-Antiinflamatorios-mediante-Machine-Learning/
│
├── ENTREGA_FINAL_VELASQUEZ_VALERIA_pynb.ipynb
│
└── README.md
```

---

## ▶️ Cómo ejecutar el proyecto

1. Clonar o descargar este repositorio.

2. Abrir el archivo:

```text
ENTREGA_FINAL_VELASQUEZ_VALERIA_pynb.ipynb
```

3. Ejecutar el notebook en **Google Colab** o **Jupyter Notebook**.

4. Instalar las librerías necesarias en caso de no encontrarse disponibles:

```python
pip install pandas numpy matplotlib seaborn scikit-learn joblib
```

5. Ejecutar las celdas en orden para reproducir el análisis, entrenamiento y evaluación de los modelos.

---

## 🔎 Conclusiones

El proyecto permitió aplicar de manera integral un flujo de trabajo de Machine Learning para un problema de clasificación.

La comparación entre distintos algoritmos permitió observar diferencias en rendimiento y estabilidad. En particular, la **Regresión Logística alcanzó un Accuracy promedio de 96,9% y un desvío estándar de 0,4%**, mostrando un comportamiento consistente durante la validación cruzada.

Más allá de la métrica obtenida, el proyecto permitió trabajar con un flujo completo de Machine Learning, desde la preparación de los datos hasta la selección y guardado del modelo final.

---

## 🚀 Posibles mejoras futuras

Como líneas de trabajo futuras se podrían incorporar:

* Optimización de hiperparámetros.
* Evaluación mediante métricas adicionales como Precision, Recall y F1-Score.
* Matriz de confusión.
* Análisis de importancia de variables.
* Comparación con modelos adicionales.
* Incorporación de nuevos datos nutricionales.
* Desarrollo de una interfaz para realizar predicciones sobre nuevos alimentos.
* Implementación del modelo mediante una API o aplicación web.

---

## 👩‍💻 Autora

**Valeria Velasquez**

Proyecto desarrollado como parte de la formación en **Data Analytics con Python**.
