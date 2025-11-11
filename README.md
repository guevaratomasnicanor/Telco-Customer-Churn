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

### 🧭 Análisis demográfico
- Clientes **con pareja o dependientes** presentan menor tasa de abandono.  
- Los **adultos mayores (Senior Citizens)** tienen mayor propensión al churn.

### 💳 Análisis contractual
- Clientes con **contratos mensuales (month-to-month)** tienden a abandonar más.  
- Aquellos que pagan con **cheque electrónico** o tienen **facturación sin papel** muestran tasas más altas de churn.

### 💡 Análisis de servicios
- Clientes con **fibra óptica**, sin **Online Security**, **Backup**, **Tech Support** o **Device Protection** presentan mayor churn.  
- Clientes **sin servicio de Internet** muestran menor tasa de abandono.

### 📈 Variables numéricas
- **Mayor antiguedad** → menor churn.  
- **Cargos mensuales bajos** y **cargos totales altos** se asocian con clientes que permanecen.

---

## 🤖 Modelado Predictivo

Se entrenaron modelos de clasificación para predecir la variable `Churn`.

**Mejor modelo:** `Random Forest`

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



