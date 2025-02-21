# Parcial1-He2AI
# Predicción del movimiento de la accion de Apple con Machine Learning 🚀

¡Bienvenido al repositorio de nuestro proyecto de IA para predecir el precio de la accion de Apple a 30 días! Este trabajo fue desarrollado como parte de un curso universitario de inteligencia artificial, con el objetivo de explorar cómo los modelos de aprendizaje automático pueden ayudar en la toma de decisiones financieras.

---

## Tabla de Contenidos
- [Descripción del Proyecto](#descripción-del-proyecto)
- [Dataset Utilizado](#dataset-utilizado)
- [Modelos Implementados](#modelos-implementados)
- [Preprocesamiento de Datos](#preprocesamiento-de-datos)
- [Resultados](#resultados)
- [Ejecución del Código](#ejecución-del-código)
- [Limitaciones y Futuras Mejoras](#limitaciones-y-futuras-mejoras)

---

## Descripción del Proyecto 📈
**Problema:** ¿Es posible predecir cómo será el stock de la acción de Apple en 30 dias?  
**Objetivo:** Desarrollar modelos de machine learning para predecirel valor de la accion de Apple (subida o bajada) como una variable binaria, analizando variables financieras históricas y ratios clave.  

**Aplicaciones prácticas:**
- Ayudar a inversores a tomar decisiones informadas sobre como estara el stock de las acciones a futuro.
- Reducir riesgos en decisiones financieras al anticipar movimientos del mercado.
- Explorar el potencial de la IA en mercados volátiles para estrategias de trading. 


---

## Dataset Utilizado 📂
**Fuente:** [SP 500 Stocks Data - Ratios, News, Price (10 yrs)](https://huggingface.co/datasets/pmoe7/SP_500_Stocks_Data-ratios_news_price_10_yrs)  
**Características:**
- **Período:** 16 años de datos diarios.
- **Variables:** 23 columnas incluyendo precios (Open, Close), volumen, ratios financieros (ROE, ROA), y métricas temporales (año, trimestre).
- **Tickers:** 321 empresas del S&P 500.

---

## Modelos Implementados 🤖
Se compararon tres modelos para la predicción:
1. **Ridge Regression**  
   - Regularización L2 para evitar sobreajuste.
   - Adecuado para modelos con muchas variables correlacionadas.
2. **Lasso Regression**  
   - Regularización L1 con selección automática de características.
   - Ideal para identificar y eliminar variables irrelevantes.
3. **XGBoost**  
   - Modelo basado en árboles de decisión con boosting.
   - Excelente para detectar patrones complejos y no lineales en los datos.


---

## Preprocesamiento de Datos 🔧
Los pasos clave incluyeron:
1. **Limpieza de datos:**  
   - Imputación de valores faltantes mediante interpolación lineal, aplicada por Ticker para conservar la coherencia temporal.
   - Detección de valores atípicos utilizando una ventana móvil de 20 días y eliminación de aquellos que exceden 3 desviaciones estándar.
2. **Feature Engineering:**  
   - Creación de ventanas temporales: se generaron Close_denoised_lag_1 hasta Close_denoised_lag_40 (40 días históricos de precios).
   - Suavizado de los precios (Open y Close) usando una media móvil de 5 días para reducir el ruido.

---

## Resultados 📊

Desempeño de cada modelo según el Error Cuadrático Medio (MSE) y el Coeficiente de Determinación (R²):

Ridge Regression:
MSE: 15.95
R2: 0.97
----------------
Lasso Regression:
MSE: 14.74
R2: 0.97
----------------
XGBoost Regression:
MSE: 1.33
R2: 1

**Conclusión:** 

XGBoost fue el modelo más preciso, con el menor error (MSE: 1.33) y la mayor capacidad explicativa (R²: 1). Sin embargo, consideramos que existe un sobreajuste.

Ridge y Lasso mostraron desempeños similares, aunque Lasso es útil para identificar variables importantes. 

## Ejecución del Código 💻
1. **Requisitos:**  
   ```bash
   pip install pandas numpy scikit-learn xgboost
   
2. **Pasos para ejecutar el código:**
   
  **1. Descargar el dataset si no está incluido:**
      
   Puedes utilizar el siguiente código para cargar los datos:

   ```python
   from datasets import load_dataset
   ds = load_dataset("pmoe7/SP_500_Stocks_Data-ratios_news_price_10_yrs", data_files="sp500_daily_ratios_20yrs.zip")
   df = ds['train'].to_pandas()
   ```

   **2. Ejecutar el script principal:**

   ```python
   script_stock_market_variation.ipynb
   ```
      
   El código realiza el preprocesamiento, entrena los tres modelos y muestra los resultados comparativos.


## Limitaciones y Futuras Mejoras 🔮
**Desafíos identificados:**

-Dificultad para predecir eventos inesperados (ej. crisis económicas).

-Dependencia de datos históricos de calidad.

**Propuestas de mejora:**

-Incorporar datos de redes sociales y noticias.

-Probar modelos de deep learning (LSTM, Transformers).

-Optimizar ventanas temporales y parámetros.
