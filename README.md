# Supply Chain Fraud Detection & Financial Risk Audit

## 📋 Descripción del Proyecto
Este proyecto implementa un motor de auditoría dinámica y detección de anomalías transaccionales sobre una arquitectura de datos masiva (+180,000 registros) en el sector logístico y de cadena de suministro. El objetivo principal es aislar e identificar vulnerabilidades financieras críticas, fugas de capital y conductas de fraude mediante técnicas avanzadas de procesamiento ETL con Python, análisis predictivo y modelado estructurado para toma de decisiones gerenciales.

A través de este análisis, se identificó un patrón de vulnerabilidad crítico: **el 100% de los incidentes confirmados bajo sospecha de fraude se concentran exclusivamente en la modalidad de pago por transferencia**.

---

## 📁 Estructura del Repositorio
```text
supply-chain-fraud-detection/
│
├── Notebook/          # Cuadernos de Jupyter para análisis exploratorio (EDA) En Visual Studio Code
│   └── supply-chain-fraud-detection.ipynb
└── README.md           # Documentación técnica del repositorio

```

## 🛠️ Tecnologías y Herramientas Utilizadas
*   **Entorno de Desarrollo Principal:** Visual Studio Code (VS Code)
*   **Lenguaje Base:** Python 3.x
*   **Procesamiento y ETL de Datos:** Pandas, NumPy
*   **Visualización Estadística:** Seaborn, Matplotlib
*   **Extensiones e Integraciones:** Jupyter Notebooks para VS Code

---

## ⚙️ Arquitectura del Pipeline ETL & Hallazgos Técnicos

### 1. Control de Calidad y Saneamiento Integrado (Data Quality)
El pipeline implementa políticas estrictas para garantizar la salud de la base de datos estructural:
*   **Aislamiento Dimensional:** Validación de dimensiones (`df.shape`) identificando un universo inicial de 180,508 transacciones.
*   **Tratamiento de Nulos Críticos:** Diagnóstico predictivo mediante `df.isna().sum()`, aplicando depuración dirigida por filas en variables de identidad del cliente e imputación controlada con valores neutros en códigos postales marginales para evitar inconsistencias de tipos mixtos.
*   **Normalización Estándar:** Estandarización de variables categóricas mediante transformaciones de texto (`.str.lower()`) para neutralizar duplicados tipográficos indirectos.

### 2. Ingeniería de Características (Feature Engineering)
Se crearon nuevas métricas operativas directas para medir la fricción en la cadena de distribución:
*   **Varianza Logística:** Cálculo matemático exacto de la brecha entre los tiempos de entrega proyectados y reales para evaluar la efectividad por tipo de transporte:
    $$\text{Varianza de Envío} = \text{Días de Envío Programados} - \text{Días de Envío Reales}$$

### 3. Inteligencia de Riesgo y Hallazgos de Negocio
*   **Concentración del Fraude:** Filtrado predictivo sobre órdenes con la bandera `SOSPECHA_DE_FRAUDE`. El motor de agregación reveló un volumen crítico de **4,062 transacciones fraudulentas**.
*   **Vulnerabilidad Operativa:** El análisis probabilístico cruzado demostró que el fraude no se distribuye al azar, sino que explota canales débiles; el total de los casos sospechosos recae sobre el método de **transferencia electrónica**, permitiendo levantar alertas inmediatas para rediseñar las pasarelas de pago corporativas.

---

## 📊 Visualización Ejecutiva (Storytelling con Datos)
El componente analítico incluye gráficos avanzados de distribución cruzada que contrastan órdenes exitosas (`COMPLETADA`) frente a las pérdidas financieras potenciales (`SOSPECHA_DE_FRAUDE`). 

Las visualizaciones geográficas mapean la tasa de entregas tardías (`Riesgo_Entrega_Tardia`) segregadas por estado del cliente, facilitando a la gerencia la toma de decisiones para rescindir contratos con proveedores de transporte ineficientes en zonas de alta fricción.

---
`
