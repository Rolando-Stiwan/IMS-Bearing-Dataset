# Predicción de Fallas en Rodamientos con Machine Learning y Señales de Vibración 🚀

Este proyecto utiliza datos reales del **IMS Bearing Dataset** proporcionado por la NASA y el IMS Center para **predecir fallas mecánicas en rodamientos** a partir de señales de vibración, usando técnicas de procesamiento de datos y modelos de inteligencia artificial.

---

## 📁 Dataset

- **Fuente:** [NASA Prognostics Data Repository](https://www.nasa.gov/intelligent-systems-division/discovery-and-systems-health/pcoe/pcoe-data-set-repository/)
- **Frecuencia de muestreo:** 20 kHz  
- **Tamaño por archivo:** 20.480 registros (1 segundo de vibración)  
- **Total de archivos:** 9.464 archivos planos `.txt`  
- **Pruebas:** 3 test-to-failure con diferentes intervalos de muestreo

---

## 🧠 Objetivo

- Integrar y procesar señales de vibración de gran volumen
- Calcular métricas estadísticas clave para análisis de condiciones
- Aplicar modelos de IA para **detectar anomalías previas a fallos mecánicos**

---

## 🛠 Tecnologías utilizadas

- `Python`, `Jupyter Notebook`
- `Pandas`, `NumPy`, `Joblib`
- `Scikit-learn`, `Keras`
- `Matplotlib`, `Seaborn`
- `Parquet` para almacenamiento optimizado

---

## ⚙️ Proceso

### 1. Integración de datos
- Conversión de archivos `.txt` en `DataFrames` masivos
- Almacenamiento eficiente en formato `.parquet`
- Procesamiento paralelo con `joblib` por limitaciones de hardware

### 2. Extracción de características
- Cálculo de métricas por archivo:
  - Media
  - RMS
  - Crest Factor
  - Kurtosis

### 3. Análisis exploratorio
- Visualización de métricas a lo largo del tiempo
- Identificación de patrones cercanos al fallo

### 4. Modelado y detección de anomalías
#### Fase 1: Modelos base
- `Isolation Forest`
- `One-Class SVM`
- `Local Outlier Factor`

#### Fase 2: Modelos avanzados
- **Distancia de Mahalanobis** con umbral estadístico
- **Autoencoders (Keras)** entrenados en condiciones normales  
  - Umbral definido con base en distribución de error (MSE)

---

## 📊 Resultados

- Los modelos basados en **Autoencoders** y **Mahalanobis** lograron una detección consistente de anomalías **antes de la falla documentada**, y son mas robustos pues se establecen puntos de referencia

---

## 📚 Lecciones aprendidas

•	Trabajar con volúmenes masivos de datos en condiciones limitadas de hardware.
•	Optimizar el procesamiento paralelo y en bloques con joblib y pandas.
•	Evaluar la efectividad de métricas de vibración en modelos de IA.
•	Aplicar modelos de detección de anomalías con base estadística y redes neuronales.


---

## ⚠️ Licencia

Este proyecto es de uso educativo y experimental. No está diseñado para entornos de producción sin una validación adicional.
