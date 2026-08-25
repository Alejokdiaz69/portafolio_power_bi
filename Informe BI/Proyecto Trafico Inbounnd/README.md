# Dashboard de Monitoreo de Tráfico Diario - Contact Center

Este repositorio contiene un modelo de inteligencia de negocios desarrollado en Power BI para el monitoreo y control operativo del tráfico de llamadas en un Contact Center. El informe está diseñado para auditar el volumen de interacciones frente a las proyecciones (Forecast) y evaluar el cumplimiento de los Acuerdos de Nivel de Servicio (SLA) a través de distintas ventanas de tiempo.

## Objetivo del Proyecto
Dotar a las áreas de Operaciones, *Workforce Management* (WFM) y supervisión con una herramienta dinámica para la toma de decisiones en tiempo real. El modelo permite identificar desviaciones en el volumen de llamadas, medir la tasa de abandono y controlar el Nivel de Servicio, facilitando la reasignación de personal o ajustes en la estrategia operativa.

## Estructura y Vistas del Informe

El proyecto utiliza un sistema de navegación por marcadores (bookmarks) y botones en la parte superior, permitiendo al usuario transicionar fluidamente entre diferentes niveles de granularidad temporal (Anual, Semanal, Diario e Intervalos) sin cambiar de página.

### Vistas Analíticas

*   **1. Análisis Anual:** Visión macroscópica del comportamiento del tráfico a nivel mensual. Permite contrastar el volumen histórico y evaluar la estacionalidad del servicio a lo largo del año.
    ![Vista Anual](Img/Trafico%20Diario%20-%20Anual.png)

*   **2. Análisis Semanal:** Desglose del rendimiento operativo por semanas dentro del mes seleccionado, facilitando la evaluación táctica a corto plazo.
    ![Vista Semanal](Img/Trafico%20Diario%20-%20Semanal.png)

*   **3. Análisis Diario:** Monitoreo táctico del volumen de llamadas (ofrecidas, atendidas, abandonadas) y la curva de Nivel de Servicio día a día.
    ![Vista Diaria](Img/Trafico%20Diario%20-%20%20Diario.png)

*   **4. Análisis por Intervalos (Intradía):** La vista más granular del modelo. Permite gestionar picos de tráfico midiendo las desviaciones cada 15 minutos e incorpora métricas operativas críticas como el TMO (Tiempo Medio de Operación).
    ![Vista Intervalos](Img/Trafico%20Diario%20-%20Intervalo.png)

---

## Arquitectura de Datos y KPIs (DAX)
El modelo se fundamenta en un esquema de modelado de datos robusto, aplicando lenguaje DAX para el cálculo de los indicadores estándar de la industria de *Contact Center*:

*   **Nivel de Servicio (SLA):** Porcentaje de llamadas atendidas dentro del umbral de tiempo aceptable, con comparativas (Diferencia vs. periodo anterior).
*   **Nivel de Atención (Tasa de Respuesta):** Relación porcentual entre las llamadas atendidas y las llamadas totales ofrecidas.
*   **Nivel de Abandono (Tasa de Abandono):** Porcentaje de clientes que colgaron antes de ser atendidos por un agente.
*   **Desviación vs. Proyección (Forecast):** Comparativa matricial entre las llamadas reales (ofrecidas) y las proyectadas (Forecast + 12%), utilizando formato condicional avanzado (alertas visuales) para denotar desviaciones críticas.
*   **Tiempos Operativos (TMO, TPC IN, TPC OUT):** Control de los tiempos medios de operación en llamadas entrantes y salientes (disponible en la vista de intervalos).

---
*Desarrollado para optimización de recursos y análisis táctico en operaciones de Contact Center.*