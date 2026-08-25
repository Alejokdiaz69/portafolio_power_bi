# Dashboard de Seguimiento de Ventas Backoffice (Conversión y Logística)

Este repositorio contiene un modelo de inteligencia de negocios desarrollado en Power BI, enfocado en auditar y analizar el embudo de conversión de ventas (Ventas Cantadas vs. Ventas Activas) y la eficiencia logística posterior al cierre. El informe permite evaluar la calidad de la venta comercial, el impacto del backlog (arrastre), las tasas de cancelación y los tiempos de tránsito logístico, ofreciendo una visión end-to-end (de principio a fin) de la operación.

## Objetivo del Proyecto
Proporcionar a las gerencias de calidad, operaciones y logística una herramienta analítica detallada para monitorear la efectividad de las ventas y su entrega. El modelo desglosa los estados de pago (Activo, Cancelado, Pendiente, Rechazo) y mide el desempeño a nivel jerárquico (supervisor/agente), temporal, geográfico y logístico (cumplimiento de promesas de entrega).

## Estructura y Vistas del Informe

El proyecto está segmentado en 4 módulos lógicos de análisis operativo y logístico. A continuación se detallan las 16 vistas integradas:

### Módulo 1: Rendimiento del Equipo de Conversión
Análisis de la efectividad de cierre y validación por jerarquía operativa, evaluando el porcentaje de ventas activas frente al backlog y arrastre.

*   **Conversión por Supervisor:** Análisis de la tasa de conversión y arrastre agrupado por líderes de equipo, incluyendo tendencias históricas.
    ![Conversión Supervisor](Img/%25%20Conversion%20Ops%20-%20Supervisor.png)
*   **Conversión por Agente:** Matriz de efectividad a nivel individual detallando Ventas N, N+1 y porcentajes de Backlog.
    ![Conversión Agente](Img/%25%20Conversion%20Ops%20-%20Agente.png)
*   **Detalle Operativo por Agente:** Vista secundaria del rendimiento operativo individual.
    ![Conversión OPS Agente](Img/Conversion%20OPS%20-%20Agente.png)
*   **Detalle Operativo por Supervisor:** Vista secundaria del rendimiento operativo por liderazgo.
    ![Conversión OPS Supervisor](Img/Conversion%20OPS%20-%20Supervisor.png)

### Módulo 2: Análisis Temporal del Embudo de Ventas
Evaluación de la tendencia de los estados de venta a lo largo del tiempo, permitiendo identificar patrones estacionales, valles de rendimiento o picos de rechazo.

*   **Conversión Mensual:** Evolución macro de los estados (Completion, Cancelado, Trans With OIC) mes a mes mediante gráficos de área.
    ![Conversión Mensual](Img/Conversion%20-%20Mensual.png)
*   **Detalle Interactivo (Tooltip) Mensual:** Tarjeta emergente con el desglose exacto de Ventas MM y Backlog del mes seleccionado.
    ![Tooltip Mensual](Img/%25%20Conversion%20-%20Mensual.png)
*   **Conversión Diaria:** Seguimiento táctico del volumen de ventas y su estado de liquidación día a día.
    ![Conversión Diaria](Img/Conversion%20-%20Diario.png)
*   **Detalle Interactivo (Tooltip) Diario:** Tarjeta emergente para auditar la conversión exacta de un día específico.
    ![Tooltip Diario](Img/%25%20Conversion%20-%20Diario.png)
*   **Análisis en Cascada (Waterfall):** Desglose matricial de la conversión segmentado por días, semanas y meses consolidados para auditorías rápidas.
    ![Conversión Cascada](Img/Conversion%20-%20Cascada.png)

### Módulo 3: Segmentación de Mercado y Tipificación de Rechazos
Auditoría de la calidad de la venta dependiendo del origen geográfico, el operador de procedencia y los motivos exactos de caída o rechazo de la venta.

*   **Conversión por Ciudad y Departamento:** Distribución geográfica del volumen de ventas y su porcentaje de activación.
    ![Conversión Ciudad](Img/Conversion%20-%20Ciudad.png)
*   **Conversión por Operador Donante:** Análisis del comportamiento de portabilidad y activación según el operador de origen (Claro, Tigo, Movistar, etc.).
    ![Conversión Operador](Img/Conversion%20-%20Operador.png)
*   **Análisis de Rechazo General:** Identificación de los motivos principales de rechazo (NIP, Titularidad, etc.) y su distribución por tipo de transporte y operador donante.
    ![Rechazo General](Img/Rechazo%20-%20General.png)
*   **Análisis de Rechazo Detallado:** Matriz granular que audita el estado de cada orden, su clasificación y tipo de rechazo asociado.
    ![Rechazo Detallado](Img/Rechazo%20-%20Detallado.png)

### Módulo 4: Logística, Transporte y Cumplimiento de Promesa
Evaluación del proceso post-venta, midiendo el estado físico de la entrega al cliente y el cumplimiento de los acuerdos de nivel de servicio (SLA/ANS) de los transportistas.

*   **Logística de Transporte General:** Visión global del estado de las órdenes (Entregado, En Tránsito, Devolución) y cumplimiento del tiempo de promesa de entrega (ANS).
    ![Transporte General](Img/Transporte%20-%20General.png)
*   **Desempeño por Transportador:** Análisis detallado de la efectividad de las empresas logísticas (Logexpress, TXX, Envía) evaluando si cumplen o exceden el tiempo promesa.
    ![Transporte Logística](Img/Transporte%20-%20Transporte.png)
*   **Resumen Logístico (Tracking):** Tabla detallada de seguimiento individualizado por *Order ID*, con días transcurridos y estado logístico (Bodega, Rechazo, Cancelado).
    ![Transporte Resumido](Img/Transporte%20-%20Resumido.png)

---

## Arquitectura de Datos y Métricas (DAX)
El modelo incluye procesos de extracción, transformación y carga (ETL), limpieza y cálculos avanzados para determinar la eficiencia operativa a través de medidas estandarizadas en análisis corporativo:

*   **Backlog y Arrastre:** Medición de ventas pendientes o arrastradas de periodos anteriores (N+1).
*   **Porcentaje de Conversión (% Venta MM / % Ventas Activas):** Relación entre las ventas gestionadas comercialmente y las que efectivamente se liquidan y activan.
*   **Cumplimiento ANS Logístico:** Evaluación binaria y porcentual entre el tiempo real de entrega y la promesa comercial acordada.
*   **Modelado:** Tablas de hechos integradas (CRM Comercial + Sistema de Logística/Despachos) unificadas mediante dimensiones comunes como Calendario, Empleados y Geografía.

---
*Desarrollado en Power BI para control gerencial de procesos Backoffice.*