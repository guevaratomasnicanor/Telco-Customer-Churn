# 📉 Telco Customer Churn Analysis

El objetivo del proyecto es **predecir si un cliente abandonará la compañía de telecomunicaciones**, utilizando información demográfica, contractual y de servicios.

---

## 📊 Dataset

📦 Fuente: [Kaggle – Telco Customer Churn Dataset](https://www.kaggle.com/datasets/blastchar/telco-customer-churn)

El dataset contiene información de más de **7000 clientes**, con variables sobre servicios contratados, antigüedad, métodos de pago y características personales.

**Variables principales:**
- `gender`
- `SeniorCitizen`
- `Partner`, `Dependents`
- `tenure`
- `PhoneService`, `MultipleLines`, `InternetService`
- `OnlineSecurity`, `OnlineBackup`, `DeviceProtection`, `TechSupport`
- `StreamingTV`, `StreamingMovies`
- `Contract`, `PaperlessBilling`, `PaymentMethod`
- `MonthlyCharges`, `TotalCharges`
- `Churn` *(variable objetivo)*

---

## 🧹 Limpieza de datos

- No se encontraron **valores faltantes (NAs)**.  
- Se detectaron **pocos outliers**, que no afectaron significativamente los modelos.  
- Se transformaron variables categóricas y se escalaron variables numéricas para modelado.

---

## 🔍 Insights Principales

- El 27% de los clientes están abandonando a la compañía.
- Las principales caracteristicas de consumidores que abandonan la empresa son el pago con  **Cheque Electrónico**, el contrato **Mes a Mes** y el servicio de **Fibra Óptica**. Al tener el servicio más costoso y tecnológicamente exigente (Fibra), el cliente desarrolla una expectativa de calidad altísima; sin embargo, al no estar atado por un contrato de permanencia, su lealtad es volátil y depende del humor del día. El detonante final es el Cheque Electrónico: a diferencia del pago automático, este método obliga al usuario a realizar un acto consciente de pago cada mes, enfrentándolo cara a cara con una factura elevada en un momento de fricción financiera.
- Los siguientes predictores de la huida son la falta servicios de protección: sin **SeguridadOnline**, **SoporteTécnico**, **Respaldo en Línea** ni **Protección del dispositivo**,      
Estos servicios no son solo extras, son anclajes de lealtad que elevan el costo de salida. Mientras que un cliente sin respaldo se va sin pensarlo, aquel que confía sus archivos a la empresa siente que renunciar al contrato es un riesgo logístico y personal, convirtiendo a las protecciones en el escudo final contra la volatilidad del pago manual y el contrato mensual.




### 📈 Variables numéricas
- **Mayor antiguedad** → menor churn.  
- **Cargos mensuales bajos** y **cargos totales altos** se asocian con clientes que permanecen.
<img width="1360" height="687" alt="Captura de pantalla 2025-11-12 094504" src="https://github.com/user-attachments/assets/81e43b01-1390-430b-9fe9-05e7298720b7" />

---

## 🤖 Modelado Predictivo

Se entrenaron modelos de clasificación para predecir la variable `Churn`.

**Mejor modelo:** `Random Forest`: Tiene una eficacia del 83%, detectando un 77% de los clientes que abandonan. Esto es fundamental ya que nos da la oportunidad de intervenir y salvar 8 de cada 10 bajas potenciales.

| Modelo | Accuracy | Precision | Recall | F1 Score |
|---------|-----------|-----------|---------|-----------|
| Random Forest | **0.83** | 0.79 | 0.77 | 0.78 |


Otros modelos evaluados: Logistic Regression, XGBoost, LightGBM.

---

## 🧰 Tecnologías utilizadas

- **Lenguaje:** Python  
- **Bibliotecas:** `pandas`, `numpy`, `matplotlib`, `seaborn`, `scikit-learn`, `xgboost`, `lightgbm`  
- **Técnicas:**  
  - Análisis exploratorio (EDA)  
  - Feature encoding y escalado  
  - Balanceo de clases (SMOTE)  
  - Validación cruzada  
  - Optimización de hiperparámetros  

---



