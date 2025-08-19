# 📊 Predicción de Cancelación de Clientes - TelecomX (Challenge Alura)

## Contexto
Este proyecto forma parte del **Challenge de Alura - TelecomX (Parte 2)**.  
El objetivo es analizar un conjunto de datos de clientes de una empresa de telecomunicaciones para **predecir la cancelación (Churn)**.  

El flujo incluye:  
- Limpieza y preparación de datos (Parte 1).  
- Balanceo de clases para tratar el desbalance del churn.  
- Creación y evaluación de modelos predictivos.  
- Análisis de variables clave que influyen en la cancelación.  

---

## 📂 Datos
- Dataset original procesado en la **Parte 1 del challenge** → `datos_tratados.csv`.  
- Variables relevantes:  
  - **Demográficas**: SeniorCitizen, Partner, Dependents.  
  - **Contrato**: tipo, forma de pago, duración.  
  - **Servicios**: Internet, Streaming, Teléfono, Soporte técnico.  
  - **Económicas**: Cargos mensuales (`MonthlyCharges`), Cargos totales (`TotalCharges`).  
  - **Variable target**: **Churn** (Sí / No).  

---

## ⚙️ Flujo del proyecto
1. **Preprocesamiento**
   - Eliminación de columnas irrelevantes (`customerID`).  
   - Separación de variables categóricas y numéricas.  
   - Codificación de variables categóricas con **OneHotEncoder**.  
   - Normalización de variables numéricas con **StandardScaler**.  

2. **Balanceo de clases**
   - Se aplicó **SMOTE** para balancear la variable objetivo (Churn).  

3. **División del dataset**
   - Conjunto de entrenamiento (80%).  
   - Conjunto de prueba (20%).  

4. **Modelos utilizados**
   - **Regresión Logística** (con normalización).  
   - **Random Forest** (sin necesidad de normalización).  

---

## 📊 Resultados

### 📌 Regresión Logística
- Accuracy: **0.77**  
- Buen balance entre precisión y recall, aunque menor capacidad predictiva frente a modelos más complejos.  

### 📌 Random Forest
- Accuracy: **0.86**  
- Mejor desempeño en comparación con la Regresión Logística.  
- AUC = **0.94**, mostrando excelente discriminación entre clientes que cancelan y permanecen.  

---

## 🔑 Factores Clave en la Cancelación
1. **Tiempo de permanencia (tenure)**: clientes con poca antigüedad cancelan más.  
2. **Cargos mensuales**: valores altos aumentan la probabilidad de churn.  
3. **Método de pago (Electronic check)**: asociado con mayor cancelación.  
4. **Tipo de contrato**: contratos mensuales presentan mayor churn que los de 1 o 2 años.  

---

## 📈 Visualizaciones destacadas
- **Matriz de correlación** de variables numéricas.  
- **Curvas ROC** comparando Regresión Logística y Random Forest.  
- **Matriz de confusión** de cada modelo.  
- **Importancia de variables en Random Forest**.  
- **Distribución del churn por tipo de contrato**.  
- **Boxplot de cargos mensuales vs churn**.  

---

## 🚀 Tecnologías utilizadas
- Python  
- Pandas, NumPy  
- Scikit-learn  
- Imbalanced-learn (SMOTE)  
- Matplotlib, Seaborn  

---

## ✨ Conclusión
El proyecto demuestra que es posible predecir la cancelación de clientes en TelecomX con una **alta precisión** usando modelos de machine learning. Random Forest sobresale como el mejor modelo, y el análisis de variables proporciona insights claros para diseñar **estrategias de retención efectivas**.
