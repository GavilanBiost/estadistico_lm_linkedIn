# Análisis de Modelo Lineal - Estadístico de Contraste Global

## 📋 Descripción

Este proyecto realiza un análisis estadístico completo de un **modelo lineal múltiple** que explora la relación entre diversas variables clínicas, demográficas y de estilo de vida con los niveles de **colesterol HDL** utilizando la base de datos `met_CQI_rl`.

## 🎯 Objetivo

Entender cómo la edad, sexo, consumo de tabaco, actividad física, presión sanguínea y otras 12 variables adicionales explican los niveles de HDL mediante una regresión lineal múltiple, con énfasis en el **estadístico F de contraste global**.

## 📊 Variables del Modelo

### Variable Dependiente
- **HDL**: Colesterol HDL (high-density lipoprotein)

### Variables Independientes (16 predictores)
- `edad0`: Edad
- `sexo`: Sexo (factor categórico)
- `tabaco0`: Consumo de tabaco (factor categórico)
- `ps1`, `ps2`: propensity scores
- `grup_int`: Grupo de intervención (factor categórico)
- `energiat`: Energía total
- `alcoholg`: Consumo de alcohol (gramos)
- `imc1`: Índice de Masa Corporal
- `idcluster`: Identificador de cluster
- `escolar1`: Nivel educativo
- `getota_1`: Grasa total
- `hipercol0`: Hipercolesterolemia (factor categórico)
- `hta0`: Hipertensión (factor categórico)
- `tra_col0`: Tratamiento de colesterol (factor categórico)
- `trathta0`: Tratamiento de hipertensión (factor categórico)

## 📁 Contenidos

- **`estadistico_contraste.Rmd`**: Documento R Markdown que contiene:
  - Carga de librerías (`dplyr`, `knitr`, `kableExtra`)
  - Especificación del modelo lineal con `lm()`
  - Resumen estadístico del modelo
  - Extracción y cálculo del **estadístico F**
  - Tabla formateada de métricas clave
  - Visualización gráfica de la distribución F bajo hipótesis nula
  - Interpretación de resultados

## 🔬 Concepto Clave: Estadístico F

El **estadístico F** es la prueba global del modelo que responde la pregunta: *¿Las variables independientes en conjunto explican significativamente la variabilidad del HDL?*

- **Fórmula conceptual**: $F = \frac{\text{Señal (Varianza explicada)}}{\text{Ruido (Varianza residual)}}$
- **Hipótesis nula (H₀)**: Todos los coeficientes son cero (modelo no significativo)
- **Hipótesis alternativa (H₁)**: Al menos un coeficiente es diferente de cero

## 🛠️ Requisitos

- **R** (versión 4.0+)
- **Paquetes R**:
  - `dplyr`: Manipulación de datos
  - `knitr`: Generación de reportes dinámicos
  - `kableExtra`: Tablas formateadas
  - `tidyr`: Transformación de datos

## 📈 Cómo Ejecutar

1. Abre el archivo `estadistico_contraste.Rmd` en RStudio
2. Asegúrate de tener la base de datos `met_CQI_rl` cargada en memoria
3. Ejecuta todas las celdas de código (Ctrl+A, Ctrl+Enter)
4. El documento genera:
   - Tabla resumen del estadístico F
   - Gráfico de la distribución F teórica
   - P-valor global e interpretación

## 📊 Salida Esperada

El análisis proporciona:
- **Estadístico F**: Valor de la razón señal/ruido
- **Grados de libertad del numerador**: Número de predictores
- **Grados de libertad del denominador**: n - p - 1
- **P-valor global**: Probabilidad de observar F si H₀ fuera cierta
- **Visualización**: Gráfico de densidad con línea del F observado

## 📝 Interpretación

- Si **p-valor < 0.05**: Rechazamos H₀ → El modelo es **significativo**
- Si **p-valor ≥ 0.05**: No rechazamos H₀ → El modelo **no es significativo**

El gráfico muestra cómo el valor F observado se aleja de la masa principal de la curva, demostrando visualmente que la probabilidad de que nuestros resultados sean casualidad es prácticamente inexistente.

## 👤 Autor

**Jesús F García Gavilán**  
31 de enero de 2026

## 📄 Licencia

Especificar si aplica una licencia (p.ej., MIT, Creative Commons, etc.)

---

*Este análisis forma parte de un estudio sobre factores que explican los niveles de colesterol HDL utilizando metodología de regresión lineal múltiple.*

---

# Linear Model Analysis - Global Test Statistic

## 📋 Description

This project performs a complete statistical analysis of a **multiple linear model** that explores the relationship between various clinical, demographic, and lifestyle variables with **HDL cholesterol levels** using the `met_CQI_rl` database.

## 🎯 Objective

To understand how age, sex, tobacco consumption, physical activity, blood pressure, and 12 other variables explain HDL levels through multiple linear regression, with emphasis on the **global F-test statistic**.

## 📊 Model Variables

### Dependent Variable
- **HDL**: HDL cholesterol (high-density lipoprotein)

### Independent Variables (16 predictors)
- `edad0`: Age
- `sexo`: Sex (categorical factor)
- `tabaco0`: Tobacco consumption (categorical factor)
- `ps1`, `ps2`: propensity scores
- `grup_int`: Intervention group (categorical factor)
- `energiat`: Total energy
- `alcoholg`: Alcohol consumption (grams)
- `imc1`: Body Mass Index
- `idcluster`: Cluster identifier
- `escolar1`: Educational level
- `getota_1`: Total fat
- `hipercol0`: Hypercholesterolemia (categorical factor)
- `hta0`: Hypertension (categorical factor)
- `tra_col0`: Cholesterol treatment (categorical factor)
- `trathta0`: Hypertension treatment (categorical factor)

## 📁 Contents

- **`estadistico_contraste.Rmd`**: R Markdown document containing:
  - Loading of libraries (`dplyr`, `knitr`, `kableExtra`)
  - Specification of the linear model with `lm()`
  - Statistical summary of the model
  - Extraction and calculation of the **F-statistic**
  - Formatted table of key metrics
  - Graphical visualization of the F distribution under null hypothesis
  - Interpretation of results

## 🔬 Key Concept: F-Statistic

The **F-statistic** is the global test of the model that answers the question: *Do the independent variables together significantly explain the variability in HDL?*

- **Conceptual formula**: $F = \frac{\text{Signal (Explained variance)}}{\text{Noise (Residual variance)}}$
- **Null hypothesis (H₀)**: All coefficients are zero (model not significant)
- **Alternative hypothesis (H₁)**: At least one coefficient is different from zero

## 🛠️ Requirements

- **R** (version 4.0+)
- **R Packages**:
  - `dplyr`: Data manipulation
  - `knitr`: Dynamic report generation
  - `kableExtra`: Formatted tables
  - `tidyr`: Data transformation

## 📈 How to Run

1. Open the `estadistico_contraste.Rmd` file in RStudio
2. Ensure the `met_CQI_rl` database is loaded in memory
3. Execute all code cells (Ctrl+A, Ctrl+Enter)
4. The document generates:
   - Summary table of the F-statistic
   - Graph of the theoretical F distribution
   - Global p-value and interpretation

## 📊 Expected Output

The analysis provides:
- **F-Statistic**: Value of the signal-to-noise ratio
- **Numerator degrees of freedom**: Number of predictors
- **Denominator degrees of freedom**: n - p - 1
- **Global p-value**: Probability of observing F if H₀ were true
- **Visualization**: Density plot with observed F line

## 📝 Interpretation

- If **p-value < 0.05**: We reject H₀ → The model is **significant**
- If **p-value ≥ 0.05**: We fail to reject H₀ → The model is **not significant**

The graph shows how the observed F value departs from the main mass of the curve, visually demonstrating that the probability of our results being due to chance is virtually nonexistent.

## 👤 Author

**Jesús F García Gavilán**  
January 31, 2026

## 📄 License

Specify if a license applies (e.g., MIT, Creative Commons, etc.)

---

*This analysis is part of a study on factors that explain HDL cholesterol levels using multiple linear regression methodology.*