# desaf-o2-ciencia-de-datos-LATAM-parte-2
# 📞 Telecom X - Parte 2: Predicción de Cancelación (Churn)

![Status](https://img.shields.io/badge/Status-Completado-brightgreen)
![Python](https://img.shields.io/badge/Python-3.12-blue)
![Machine Learning](https://img.shields.io/badge/Machine_Learning-Scikit_Learn-orange)

## 📖 Descripción del Proyecto
Este proyecto representa la segunda fase del análisis de retención de clientes para la empresa de telecomunicaciones **Telecom X**. Tras un exhaustivo Análisis Exploratorio de Datos (EDA) en la Fase 1, esta fase se centra en el **desarrollo de modelos predictivos de Machine Learning** capaces de identificar anticipadamente a los clientes con alta probabilidad de cancelar sus servicios (Churn).

El objetivo principal es pasar de un análisis descriptivo a uno **prescriptivo**, brindando a la empresa herramientas automatizadas y hallazgos estratégicos para diseñar campañas de retención efectivas.

---

## 🎯 Objetivos
1. **Preprocesamiento Avanzado:** Preparar los datos limpios mediante codificación de variables categóricas (One-Hot Encoding), tratamiento de valores atípicos/nulos y estandarización de escalas.
2. **Balanceo de Clases:** Mitigar el desbalanceo natural del dataset (donde la mayoría de los clientes *no* cancelan) utilizando la técnica de sobremuestreo sintético **SMOTE**.
3. **Modelado Predictivo:** Entrenar y evaluar dos algoritmos de clasificación de distinta naturaleza:
   - *Regresión Logística* (Enfoque lineal e interpretable).
   - *Random Forest* (Enfoque de ensamble no lineal).
4. **Extracción de Insights:** Interpretar los coeficientes y la importancia de las variables para entregar recomendaciones accionables a la gerencia.

---

## 🛠️ Tecnologías y Librerías Utilizadas
* **Lenguaje:** Python
* **Manipulación de Datos:** Pandas, NumPy
* **Visualización:** Matplotlib, Seaborn
* **Machine Learning:** Scikit-Learn (LogisticRegression, RandomForestClassifier)
* **Preprocesamiento:** Imbalanced-Learn (SMOTE), StandardScaler

---

## 📊 Principales Hallazgos Estratégicos (Insights)

Tras evaluar los modelos, extrajimos los factores determinantes que impulsan la fuga o retención de clientes. 

### 1. Variables Críticas Globales (Según Random Forest)
El modelo de Random Forest destacó las siguientes características como las más decisivas al momento de predecir el Churn:
1. **Método de Pago:** `Electronic check` (Cheque electrónico).
2. **Fidelidad:** `Meses_Contrato` (Permanencia del cliente).
3. **Facturación:** `Cobro_Total` y `Cobro_Mensual`.
4. **Tipo de Servicio:** `Servicio_Internet_Fiber optic` (Fibra óptica).

### 2. Factores de Riesgo (Según Regresión Logística)
Los siguientes servicios, evaluados de forma aislada, mostraron una fuerte tendencia a **aumentar la probabilidad de cancelación**:
* 📺 Streaming de TV (Coef: 3.69)
* 🎬 Streaming de Películas (Coef: 3.63)
* 🛡️ Protección de Dispositivo (Coef: 3.40)
* ☁️ Respaldo Online y Seguridad Online

*Nota analítica:* Aunque estos servicios individuales elevan el riesgo (posiblemente por el aumento del ticket promedio que percibe el cliente), el ecosistema completo genera retención (ver punto 3).

### 3. Factores de Retención (Según Regresión Logística)
Las variables que **más ayudan a evitar que el cliente se vaya** son:
* 📦 **Cantidad de Servicios Adquiridos:** (Coef: -5.83). A mayor integración del cliente en el ecosistema de Telecom X, menor es la fuga.
* 📅 **Antigüedad (Meses_Contrato):** (Coef: -2.06). La lealtad a largo plazo es un fuerte blindaje.
* 📜 **Contratos a Largo Plazo:** Los contratos de 1 año (Coef: -0.46) y 2 años (Coef: -0.85) reducen drásticamente el Churn frente a los contratos mensuales.

---

## 💡 Recomendaciones de Negocio
Basados en los datos empíricos de nuestros modelos, se sugiere al equipo directivo:

1. **Incentivar Contratos a Largo Plazo:** Diseñar campañas agresivas de *upselling* para migrar a clientes de contratos "Mes a Mes" hacia contratos de "1 o 2 años", ofreciendo beneficios en la facturación.
2. **Revisión de Métodos de Pago:** Investigar la fricción que genera el método de pago `Electronic check`, ya que es la principal señal de alerta en el modelo de Random Forest.
3. **Estrategia de Ecosistema (Bundles):** Dado que la `Cant_Servicios` es el mayor retenedor, se deben crear "Paquetes (Bundles)" atractivos. Si el cliente percibe que tiene su vida digital resuelta con Telecom X (Internet + Teléfono + TV), es mucho menos probable que cancele.
4. **Monitoreo de Costos:** Revisar la estructura de precios de los servicios de Streaming y Seguridad, ya que están impactando negativamente la percepción de valor de algunos usuarios.

---
*Proyecto desarrollado como parte del equipo de Machine Learning de Telecom X.*
