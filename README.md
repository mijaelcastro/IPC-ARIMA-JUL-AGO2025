# 📊 Predicción del IPC Lima Metropolitana con modelo ARIMA

Este repositorio documenta el análisis econométrico realizado sobre la serie temporal del **Índice de Precios al Consumidor (IPC)** en Lima Metropolitana, utilizando modelos ARIMA y preparando el terreno para un enfoque multivariante SARIMAX. Todo el análisis se basa en datos oficiales obtenidos desde la [API del BCRP](https://estadisticas.bcrp.gob.pe/estadisticas/series/).

---

## 🎯 Objetivos del proyecto

- Verificar la **estacionariedad** de la serie IPC con el test Augmented Dickey-Fuller.
- Modelar dinámicas inflacionarias mediante distintos modelos **ARIMA univariantes**.
- Comparar especificaciones mediante métricas AIC/BIC y diagnóstico de residuos.
- Realizar **forecast** del IPC para **julio,agosto y septiembre del 2025**.
- Incorporar variables exógenas en un modelo SARIMAX para capturar efectos estructurales.

---

## 🔍 Variables utilizadas

| Variable                         | Fuente BCRP          |
|----------------------------------|-----------------------|
| Índice de Precios al Consumidor (IPC) | Portal de estadísticas |
| Tasa de referencia               | API REST del BCRP     |
| Tipo de cambio interbancario     | API REST del BCRP     |
| Expectativas de inflación (12m)  | Encuesta de expectativas |

Todas las series fueron extraídas, procesadas y tratadas para análisis temporal y modelado econométrico.

---

## ⚙️ Modelos estimados

Se compararon tres modelos ARIMA:

| Modelo        | AIC     | Predicción Julio | Predicción Agosto |
|---------------|---------|------------------|-------------------|
| ARIMA(1,2,0)  | 160.35  | -0.04            | No aplicado       |
| ARIMA(1,2,1)  | 109.21  | 0.05             | No aplicado       |
| ARIMA(2,2,1)  | **103.33** | **0.14**         | **0.07**           |

**ARIMA(2,2,1)** demostró mejor ajuste según AIC/BIC y residuos no autocorrelados. Las proyecciones para julio, agosto y septiembre  fueron realizadas con este modelo.

---

## 📈 Visualización

La imagen principal del proyecto muestra:
- Serie observada del IPC (Dic. 2021 = 100)
- Predicción del IPC para julio,agosto y septiembre 2025

📌 *Elaboración propia | Modelado con ARIMA(2,2,1) sobre datos del BCRP*

---

## 🧠 Aplicación y relevancia

Este proyecto muestra cómo la **econometría aplicada** permite no solo modelar precios, sino también entender las correlaciones entre variables macroeconómicas. El enfoque multivariante con **SARIMAX** busca captar relaciones estructurales entre el IPC y variables clave como tasa de interés o expectativas inflacionarias.

📎 Estos modelos tienen alto valor en:
- Proyecciones en contexto privado (planes de precios, financiamiento)
- Simulación de escenarios económicos
- Análisis consultivo y soporte a decisiones basadas en evidencia

---

## 📦 Herramientas utilizadas

- `Python` (Pandas, NumPy)
- `Statsmodels` (ARIMA/SARIMAX)
- `Matplotlib`, `Seaborn`
- API BCRP (consultas automáticas)
- Test ADF, ACF/PACF, Ljung-Box, Jarque-Bera

---

## 👤 Autor

**Mijael Castro Lozano**  
Economista | 
📧 [mijael.castro@gmail.com]  
🔗 [https://www.linkedin.com/in/mijaelcastro/]

---

# Próximos pasos

- Estimación de SARIMAX con variables exógenas
- Análisis de impacto estructural por shocks macroeconómicos
- Publicación de resultados en LinkedIn y presentación técnica

---
