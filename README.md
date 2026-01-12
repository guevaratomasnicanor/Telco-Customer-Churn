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
- Los siguientes predictores de la huida son la falta servicios de protección: sin **Seguridad Online**, **Soporte Técnico**, **Respaldo en Línea** ni **Protección del dispositivo**. Estos servicios no son solo extras, son anclajes de lealtad que elevan el costo de salida. Mientras que un cliente sin respaldo se va sin pensarlo, aquel que confía sus archivos a la empresa siente que renunciar al contrato es un riesgo logístico y personal, convirtiendo a las protecciones en el escudo final contra la volatilidad del pago manual y el contrato mensual.

- La estabilidad de la empresa descansa sobre el "Cliente Blindado", un perfil cuya lealtad no es casual, sino el resultado de barreras de salida estratégicas que reducen el riesgo de fuga a niveles mínimos de entre el 2.8% y el 7%. El pilar fundamental de este ecosistema es el **Contrato de Dos Años**, un "muro de contención" que transforma el servicio en una relación de largo plazo, eliminando el ciclo de duda que asfixia a los contratos mensuales. Esta fidelidad se ve reforzada por un "efecto de invisibilidad": al utilizar métodos de pago automáticos como **Tarjeta de credito** no estan cuestionandose constantemente el valor del servicio en cada factura, lo que permite que la relación fluya sin fricciones financieras mensuales. Finalmente, este círculo de lealtad se completa con los usuarios que no poseen **servicio de internet**, quienes presentan una tasa de abandono de apenas el 7.4%; para ellos, la simplicidad del servicio básico y la ausencia de las altas expectativas tecnológicas  eliminan los motivos de migración, convirtiéndolos en uno de los pilares más estables y predecibles de la compañía.

<img width="644" height="361" alt="Captura de pantalla 2026-01-11 201313" src="https://github.com/user-attachments/assets/2263dca2-cc95-483b-b786-015d37d5a126" />


### 📈 Variables numéricas

La relación entre el tiempo y el costo define el destino del cliente: la antigüedad (tenure) es el ancla de lealtad definitiva, donde los clientes fieles alcanzan una mediana de 40 meses frente a los escasos 10 meses de quienes huyen. Esta permanencia se ve amenazada por la presión de los cargos mensuales (monthly charges), ya que el abandono se concentra en facturas elevadas de $\$80$, mientras que la estabilidad se halla en pagos más modestos de $\$65$. Finalmente, el valor acumulado (total charges) actúa como una barrera psicológica; cuanto mayor es la inversión histórica —con medianas de $\$1,800$ en clientes leales contra $\$700$ en desertores—, mayor es el compromiso del usuario, demostrando que el éxito de la retención reside en lograr que el historial y el capital invertido neutralicen la tentación de un precio mensual más bajo.


<img width="1360" height="687" alt="Captura de pantalla 2025-11-12 094504" src="https://github.com/user-attachments/assets/81e43b01-1390-430b-9fe9-05e7298720b7" />

---

## 🤖 Modelado Predictivo

Se entrenaron modelos de clasificación para predecir la variable `Churn`.

**Mejor modelo:** `Random Forest`: Tiene una eficacia del 77%, detectando un 83% de los clientes que abandonan. Esto es fundamental ya que nos da la oportunidad de intervenir y salvar 8 de cada 10 bajas potenciales.

| Modelo | Accuracy | Recall | 
|---------|-----------|-----------|
| Random Forest | **0.77** | 0.83 |

<img width="638" height="357" alt="Captura de pantalla 2026-01-11 220436" src="https://github.com/user-attachments/assets/2f2a6007-91d2-4381-a92a-5f8fe00c60f9" />



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



