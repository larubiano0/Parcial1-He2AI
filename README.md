# Parcial1-He2AI
# Predicción del S&P 500 con Machine Learning 🚀

¡Bienvenido al repositorio de nuestro proyecto de IA para predecir el precio del S&P 500! Este trabajo fue desarrollado como parte de un curso universitario de inteligencia artificial, con el objetivo de explorar cómo los modelos de aprendizaje automático pueden ayudar en la toma de decisiones financieras.

---

## Tabla de Contenidos
- [Descripción del Proyecto](#descripción-del-proyecto)
- [Dataset Utilizado](#dataset-utilizado)
- [Modelos Implementados](#modelos-implementados)
- [Preprocesamiento de Datos](#preprocesamiento-de-datos)
- [Resultados](#resultados)
- [Ejecución del Código](#ejecución-del-código)
- [Limitaciones y Futuras Mejoras](#limitaciones-y-futuras-mejoras)
- [Contribuidores](#contribuidores)

---

## Descripción del Proyecto 📈
**Problema:** ¿Es posible predecir con precisión el precio del S&P 500 usando IA?  
**Objetivo:** Desarrollar modelos de machine learning para predecir los precios de cierre del índice S&P 500, analizando variables financieras históricas y ratios clave.  

**Aplicaciones prácticas:**
- Ayudar a inversores a optimizar estrategias de trading.
- Reducir riesgos en decisiones financieras.
- Explorar el potencial de la IA en mercados volátiles.

---

## Dataset Utilizado 📂
**Fuente:** [SP 500 Stocks Data - Ratios, News, Price (10 yrs)](https://huggingface.co/datasets/pmoe7/SP_500_Stocks_Data-ratios_news_price_10_yrs)  
**Características:**
- **Período:** 20 años de datos diarios.
- **Variables:** 23 columnas incluyendo precios (Open, Close), volumen, ratios financieros (ROE, ROA), y métricas temporales (año, trimestre).
- **Tickers:** 321 empresas del S&P 500.

---

## Modelos Implementados 🤖
Se compararon tres modelos para la predicción:
1. **Ridge Regression**  
   - Regularización L2 para evitar sobreajuste.
2. **Lasso Regression**  
   - Regularización L1 con selección automática de características.
3. **XGBoost**  
   - Modelo basado en árboles de decisión con boosting.

---

## Preprocesamiento de Datos 🔧
Los pasos clave incluyeron:
1. **Limpieza:**  
   - Interpolación lineal para valores faltantes.
   - Eliminación de outliers usando media móvil y desviación estándar.
2. **Feature Engineering:**  
   - Creación de ventanas temporales (40 días históricos de precios).
   - Suavizado de precios con media móvil de 5 días.
3. **Transformaciones:**  
   - Codificación one-hot del trimestre.
   - Normalización de datos numéricos.

---

## Resultados 📊


**Conclusión:** 

---

## Ejecución del Código 💻
1. **Requisitos:**  
   ```bash
   pip install pandas numpy scikit-learn xgboost
   Pasos:

2. **Ejecutar el Jupyter Notebook script_stock_market_variation.ipynb.**

El script carga los datos, realiza el preprocesamiento, entrena los modelos y muestra los resultados.

## Limitaciones y Futuras Mejoras 🔮
**Desafíos identificados:**

-Dificultad para predecir eventos inesperados (ej. crisis económicas).

-Dependencia de datos históricos de calidad.

**Propuestas de mejora:**

-Incorporar datos de redes sociales y noticias.

-Probar modelos de deep learning (LSTM, Transformers).

-Optimizar ventanas temporales y parámetros.
