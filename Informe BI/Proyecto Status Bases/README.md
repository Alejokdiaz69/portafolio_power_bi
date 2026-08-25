# Dashboard de Comportamiento y Estrategia de Bases

Este repositorio contiene un modelo de inteligencia de negocios desarrollado en Power BI, enfocado en auditar el rendimiento y la gestión de las bases de datos (leads) en operaciones de ventas o contact center de salida (Outbound). El informe permite evaluar métricas clave como la contactabilidad, la efectividad bruta y neta, y la estrategia de barrido (vueltas) a lo largo de diferentes campañas y canales.

## Objetivo del Proyecto
Proporcionar a las gerencias de inteligencia comercial y operaciones una herramienta analítica estructurada para medir la calidad de las bases cargadas y la eficiencia de los canales de marcación. El modelo facilita la identificación de bases agotadas, la optimización de las vueltas de contacto y la evaluación del retorno de conversión histórico (2024-2026).

## Estructura y Vistas del Informe

El proyecto está segmentado en 3 módulos lógicos de análisis operativo y estratégico. A continuación se detallan las 6 vistas integradas:

### Módulo 1: Comportamiento General de Bases
Análisis del rendimiento global de los registros cargados, midiendo el embudo desde la carga hasta la conversión (Venta Neta).

*   **Comportamiento General:** Visión macroscópica de los KPIs principales (Total Cargado, Contactado, % Contactabilidad, Efectividad) agrupados por año y mes.
    ![Comportamiento General](Img/Comportamiento%20-%20General.png)
*   **Comportamiento Detallado:** Desglose granular a nivel de campaña, evaluando el volumen de registros recorridos, ventas brutas vs. netas y el porcentaje de gestión específico por origen.
    ![Comportamiento Detallado](Img/Comportamiento%20-%20Detallado.png)
*   **Comportamiento Comparativo:** Panel enfocado en contrastar la relación entre el porcentaje de contacto (%Contact) y la intensidad de barrido (Int/Record) mediante visualizaciones de KPIs dinámicos.
    ![Comportamiento Comparativo](Img/Comportamiento%20-%20Comparativo.png)

### Módulo 2: Análisis Histórico y Tendencias
Evaluación longitudinal para identificar la estacionalidad de la contactabilidad y la caída o mejora en las tasas de conversión a lo largo de los años.

*   **Comparativo por Año:** Gráficos de doble eje que cruzan el porcentaje de contacto con la efectividad por contacto (Efect/Conta) y efectividad por trámite (Efect/Tram) abarcando periodos continuos de 2024, 2025 y 2026.
    ![Comparativo Año](Img/Comparativo%20a%C3%B1o.png)

### Módulo 3: Detalle de Estrategia y Priorización
Auditoría cualitativa de cómo se están consumiendo las bases, priorizando canales y midiendo el esfuerzo (vueltas) necesario para lograr el contacto.

*   **Detalle de Estrategia General:** Matriz que evalúa el porcentaje de recorrido, alertas de prioridad (Baja, Media, Alta) y las "vueltas" promedio aplicadas a cada campaña y canal.
    ![Estrategia General](Img/Detalle%20estrategia%20-%20General.png)
*   **Detalle de Estrategia Comparativo:** Tablas matriciales de calor que contrastan la contactabilidad, efectividad bruta, efectividad neta y vueltas, segmentadas por canal a través de los diferentes meses de gestión.
    ![Estrategia Comparativo](Img/Detalle%20estrategia%20-%20Comparativo.png)

---

## Arquitectura de Datos y Métricas (DAX)
El modelo incluye cálculos avanzados estandarizados para operaciones de gestión de bases y marcación masiva:

*   **Porcentaje de Contactabilidad (%Contact):** Relación entre los registros efectivamente contactados frente al total recorrido.
*   **Intensidad y Vueltas (Int/Record / Vueltas Base):** Promedio de intentos de contacto (marcaciones) aplicados a cada registro (lead) dentro de una base.
*   **Efectividad Bruta y Neta:** Tasas de conversión evaluadas antes y después de auditorías de calidad o rechazos, cruzadas contra el volumen contactado.
*   **Modelado:** Tablas de hechos integradas (Cargas de Bases, Registros de Marcación, Conversiones) vinculadas a dimensiones jerárquicas (Campañas, Canales, Calendario).

---
*Desarrollado para la optimización táctica y estratégica de bases de datos en entornos corporativos.*