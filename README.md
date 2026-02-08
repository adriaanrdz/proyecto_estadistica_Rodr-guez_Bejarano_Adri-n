# 📊 Análisis de Depresión en Estudiantes Universitarios

Proyecto de análisis estadístico y modelado predictivo sobre factores asociados a la depresión en estudiantes universitarios.

## 📖 Descripción

Este proyecto analiza un dataset de **27,898 estudiantes universitarios** para identificar factores de riesgo asociados a la depresión mediante técnicas de estadística descriptiva, análisis de correlaciones y modelado predictivo.

### Objetivos:

1. **Análisis Descriptivo:** Exploración de variables numéricas y categóricas
2. **Inferencia y Modelado:** Predicción de depresión mediante regresión lineal y logística
3. **Series Temporales:** Análisis de tendencias y estacionalidad en datos simulados

---

## 📊 Dataset

**Fuente:** Student Depression Dataset  (Kaggle)
**Observaciones:** 27,898 registros  
**Variables:** 15 (8 numéricas, 7 categóricas)

### Variables principales:

- **Objetivo:** `depression` (0 = No, 1 = Sí)
- **Predictores clave:**
  - `suicidal_thoughts` (Pensamientos suicidas)
  - `academic_pressure` (Presión académica, escala 0-5)
  - `financial_stress` (Estrés financiero, escala 1-5)
  - `family_mental_illness` (Historial familiar)
  - `study_satisfaction` (Satisfacción con estudios)
  - `dietary_habits` (Hábitos alimenticios)
  - `work_study_hours` (Horas de estudio/trabajo)
  - `age` (Edad del estudiante)

---

## 🗂️ Estructura del Proyecto
```
proyecto-depresion/
│
├── data/
│   └── student_depression_dataset.csv
│
├── notebooks/
│   └── analisis_completo.ipynb
│
├── outputs/
│   ├── graficas/
│   │   ├── correlacion_matrix.png
│   │   ├── pairplot.png
│   │   ├── scatter_plots.png
│   │   ├── regresion_lineal.png
│   │   ├── regresion_logistica.png
│   │   └── series_temporales.png
│   │
│   └── modelos/
│       └── resultados_modelos.txt
│
└── README.md
```

---

## 📈 Resultados Principales

### 1️⃣ Análisis Descriptivo

- **Dataset limpio:** Solo 0.075% de outliers detectados
- **Distribuciones:** Todas las variables numéricas muestran curtosis platicúrtica (< 0)
- **Skewness:** Todas las variables con |skewness| < 0.5, indicando distribuciones balanceadas

### 2️⃣ Correlaciones

**Variables más correlacionadas con depresión:**

| Variable | Correlación | Interpretación |
|----------|-------------|----------------|
| `suicidal_thoughts` | **r = 0.55** | Correlación moderada-fuerte |
| `academic_pressure` | **r = 0.47** | Correlación moderada |
| `financial_stress` | **r = 0.36** | Correlación débil-moderada |

### 3️⃣ Modelado Predictivo

#### Regresión Lineal:
- **R² = 0.453** (45.3% de varianza explicada)
- **RMSE = 0.35**
- ⚠️ **Conclusión:** No apropiada para variables binarias (genera predicciones fuera de [0,1])

#### Regresión Logística:
- **Accuracy = 82.2%** ✅
- **Precision = 83.2%**
- **Recall = 87.3%**
- **F1-Score = 85.2%**
- ✅ **Conclusión:** Modelo apropiado y con alto desempeño

**Mejora:** Regresión Logística supera a Regresión Lineal en +37 puntos porcentuales

### 4️⃣ Series Temporales

**Serie simulada (730 días):**
- **Tendencia:** Crecimiento lineal de 10 a 50 unidades (+400%)
- **Estacionalidad:** Ciclos repetitivos cada ~91 días (3 meses)
- **Componentes identificados:** Tendencia (85%), Estacionalidad (10%), Ruido (5%)

---

## 🛠️ Tecnologías

- **Python 3.13.12**
- **Pandas** - Manipulación de datos
- **NumPy** - Operaciones numéricas
- **Matplotlib** - Visualización básica
- **Seaborn** - Visualización estadística
- **Scikit-learn** - Modelado predictivo
- **Statsmodels** - Análisis de series temporales
- **Jupyter Notebook** - Desarrollo interactivo

---

## 📚 Metodología

1. **Limpieza de datos:** Eliminación de duplicados y valores nulos
2. **Análisis exploratorio:** Estadísticos descriptivos, distribuciones, outliers
3. **Análisis de correlaciones:** Identificación de variables predictoras
4. **Modelado:**
   - Regresión Lineal (comparación)
   - Regresión Logística (modelo final)
5. **Evaluación:** Métricas de clasificación (Accuracy, Precision, Recall, F1)
6. **Series temporales:** Descomposición estacional y análisis de tendencias

---

## 💡 Conclusiones

1. La **depresión en estudiantes** está significativamente asociada a pensamientos suicidas, presión académica y estrés financiero.

2. El modelo de **Regresión Logística** alcanza un **82% de precisión** en la predicción de depresión, siendo apropiado para clasificación binaria.

3. El **Recall alto (87%)** indica que el modelo detecta la mayoría de casos de depresión, lo cual es crucial en contexto de salud mental.

4. Las distribuciones del dataset son robustas y balanceadas, con mínima presencia de outliers (<0.1%).
