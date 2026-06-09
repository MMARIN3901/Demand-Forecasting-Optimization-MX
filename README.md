# Demand-Forecasting-Optimization-MX

Este repositorio contiene el desarrollo lógico y técnico de un modelo de **Forecasting (Pronóstico de Demanda y Costos)** diseñado para optimizar la cadena de suministro, mitigar riesgos de desabasto y mejorar la planeación presupuestal anual mediante analítica avanzada.

El proyecto está estructurado desde la perspectiva de un **Analytics Translator / Business Analyst**, conectando variables críticas de negocio con modelos predictivos de suavizamiento exponencial en Python para transformar datos históricos en decisiones estratégicas de alta dirección.

---

## 📊 Arquitectura del Proyecto y Enfoque Estratégico

En la gestión de abastecimiento tradicional, las proyecciones suelen basarse en promedios móviles simples o intuición operativa, lo que genera variaciones costosas (efecto látigo/bullwhip effect) o desviaciones en el presupuesto asignado (CAPEX/OPEX).

Este proyecto implementa un flujo automatizado de analítica predictiva utilizando algoritmos de series de temporales para:

* **Optimizar el Capital de Trabajo:** Reducir costos de almacenamiento mediante el cálculo de un *baseline* estadístico robusto, disminuyendo el costo de mantener inventario parado (*holding cost*).
* **Mitigar Riesgo Operativo (Out-of-Stock):** Programar las órdenes de compra (PO) con proveedores críticos basándose en la tasa de consumo real proyectada, blindando el nivel de servicio al cliente.
* **Transparencia Presupuestal:** Anticipar negociaciones contractuales de volumen y asegurar la capacidad logística antes de los choques estacionales del mercado.

---

## 🛠️ Stack Tecnológico Utilizado

* **Lenguaje:** Python 3.x
* **Manipulación y Modelación Matemática:** `pandas`, `numpy`
* **Modelado Predictivo (Series Temporales):** `statsmodels` (Simple Exponential Smoothing / Holt-Winters)
* **Visualización de Datos e Insights:** `matplotlib`

---

## 📂 Estructura del Repositorio

* `demanda_cadena_suministro.csv`: Dataset histórico generado (3 años de transacciones analizadas).
* `Supply_Chain_Forecasting.ipynb`: Jupyter Notebook que documenta el Análisis Exploratorio de Datos (EDA), el ajuste algorítmico y la interpretación de negocio.
* `README.md`: Documentación ejecutiva del proyecto.

---

## 📈 Pipeline de Implementación Lógica

### 1. Modelado de Series Temporales y Análisis Exploratorio (EDA)
Construcción de un histórico transaccional de 3 años (2023-2025) aislando matemáticamente las fuerzas que mueven el mercado para mitigar el riesgo de subcompras basadas en históricos obsoletos:
* **Tendencia Ascendente:** Simulación del crecimiento orgánico sostenido del negocio (pasando de ~10 a >50 unidades base).
* **Estacionalidad Semanal (Corto Plazo):** Identificación de picos recurrentes de consumo (+20 unidades) concentrados en viernes y sábados, exigiendo operativamente programar entregas críticas los días jueves.
* **Estacionalidad Anual (Temporada Alta):** Captura de incrementos sistemáticos de +40 unidades durante el mes de diciembre.

### 2. Entrenamiento del Modelo Predictivo (Baseline)
Implementación del algoritmo de **Suavizamiento Exponencial Simple (Simple Exponential Smoothing)** configurado con optimización automática de parámetros (*initialization method: estimated*). 

### 3. Evaluación y Métricas de Control de Negocio
* **Optimización de Alpha ($\alpha \approx 19.6\%$):** Al determinar automáticamente un factor de suavizamiento bajo, el algoritmo otorga mayor peso a la historia acumulada y no sobre-reacciona a picos aislados, garantizando un pronóstico robusto frente al ruido estocástico del mercado.
* **Estabilización Post-Estacional:** Capacidad de asimilar el descenso natural de la demanda a inicios de año tras el pico crítico de diciembre (máximos de 120 unidades) sin sesgarse negativamente.
* **Establecimiento del Running Rate:** Proyección de una línea base constante de **94.72 unidades diarias** para los próximos 30 días, sirviendo como métrica de control financiero y operativo.

---

## 👤 Autor

* **Moisés Antonio Marín Bernal**
* *Strategic Sourcing & Business Intelligence Leader*
