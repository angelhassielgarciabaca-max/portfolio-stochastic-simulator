# 📈 Multi-Asset Monte Carlo Risk Engine

Este proyecto implementa un motor de simulación estocástica para evaluar el riesgo y la dirección de mercado de un portafolio de activos financieros (AAPL, MSFT, NVDA, AMZN, GOOGL). Utiliza modelos avanzados de probabilidad para proyectar 5,000 escenarios posibles en un horizonte de un año.

## 🎯 El Problema
En la gestión de portafolios, basarse únicamente en el rendimiento promedio histórico es peligroso porque ignora la **volatilidad** y la **correlación** entre activos. Un portafolio puede parecer rentable, pero ser extremadamente vulnerable a eventos de "cola" (cisnes negros). 

El desafío técnico aquí es: ¿Cómo predecir la distribución de precios futuros respetando que si Apple baja, es muy probable que Microsoft también lo haga?



## 🧠 Metodología Técnica
A diferencia de las simulaciones básicas, este motor utiliza:

1. **Movimiento Browniano Geométrico (GBM):** Para modelar el componente aleatorio y el 'drift' (tendencia) del mercado.
2. **Correlación de Cholesky:** Se calculó la matriz de covarianza de los activos y se aplicó una descomposición de Cholesky. Esto asegura que los números aleatorios generados mantengan la estructura de correlación real del mercado.
3. **Optimización con NumPy:** El código está vectorizado para procesar simulaciones masivas en milisegundos, permitiendo escalabilidad para algoritmos de Trading de Alta Frecuencia (HFT).

## 🛠️ Tecnologías Utilizadas
* **Python 3.x**
* **NumPy:** Álgebra lineal y generación de números aleatorios.
* **Pandas:** Manipulación de series de tiempo financieras.
* **Matplotlib:** Visualización de nubes de trayectoria.
* **YFinance:** Ingesta de datos de mercado en tiempo real.

## 📊 Análisis de Resultados (Value at Risk)
Tras ejecutar 5,000 iteraciones sobre los activos seleccionados, el modelo arroja:

* **Escenario Optimista (95%):** El techo proyectado para el portafolio.
* **Valor en Riesgo (VaR 5%):** La pérdida máxima esperada en condiciones normales de mercado con un 95% de confianza.



## 💡 Conclusiones y Aprendizaje
1. **La correlación importa:** Ignorar la covarianza subestima el riesgo real. Al usar Cholesky, el modelo refleja cómo el sector tecnológico tiende a moverse en bloque.
2. **Distribución no Normal:** Aunque el modelo base asume normalidad en los retornos logarítmicos, la simulación ayuda a visualizar la asimetría en los precios finales.
3. **Aplicabilidad HFT:** Este motor de cálculo es el primer paso para un bot de trading que necesite ajustar sus parámetros de riesgo según la volatilidad del momento.

---
**Contacto:** 
-  [Linkdin](www.linkedin.com/in/hassiel-garcía-719756260)
-  [Correo](angelhassielgarciabaca@gmail.com)
