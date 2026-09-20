# 🚨 Supply Chain Fraud Detection

> Motor de auditoría y análisis de anomalías transaccionales aplicado al sector logístico y de cadena de suministro, desarrollado con **Python**, técnicas de procesamiento ETL y análisis exploratorio de datos.

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.x-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python 3.x" />
  <img src="https://img.shields.io/badge/Pandas-ETL-150458?style=for-the-badge&logo=pandas&logoColor=white" alt="Pandas" />
  <img src="https://img.shields.io/badge/NumPy-Data_Processing-013243?style=for-the-badge&logo=numpy&logoColor=white" alt="NumPy" />
  <img src="https://img.shields.io/badge/Matplotlib-Visualization-11557C?style=for-the-badge&logo=matplotlib&logoColor=white" alt="Matplotlib" />
  <img src="https://img.shields.io/badge/Seaborn-Analytics-4C72B0?style=for-the-badge&logo=python&logoColor=white" alt="Seaborn" />
  <img src="https://img.shields.io/badge/Jupyter-Notebook-F37626?style=for-the-badge&logo=jupyter&logoColor=white" alt="Jupyter Notebook" />
  <img src="https://img.shields.io/badge/VS_Code-Development-007ACC?style=for-the-badge&logo=visualstudiocode&logoColor=white" alt="Visual Studio Code" />
</p>

---

## 📋 Descripción del Proyecto

Este proyecto implementa un flujo de auditoría dinámica y detección de anomalías transaccionales sobre una base de datos del sector logístico y de cadena de suministro.

El objetivo principal es identificar posibles vulnerabilidades financieras, fugas de capital y patrones asociados a sospechas de fraude mediante:

- Procesamiento y transformación de datos con Python.
- Técnicas de limpieza y control de calidad.
- Ingeniería de características (*Feature Engineering*).
- Análisis exploratorio y visualización estadística.
- Segmentación de riesgos para apoyar la toma de decisiones gerenciales.

### 🔎 Hallazgo principal

De acuerdo con los resultados obtenidos en el análisis, el **100 % de los incidentes identificados como sospecha de fraude se concentran en la modalidad de pago por transferencia**.

> Este resultado corresponde al análisis realizado sobre la base de datos del proyecto y debe interpretarse considerando el periodo, la muestra y las reglas utilizadas para identificar las transacciones sospechosas.

---

## 📁 Estructura del Repositorio

```text
supply-chain-fraud-detection/
│
├── Notebook/
│   └── supply-chain-fraud-detection.ipynb
│
└── README.md
```

### Descripción de los componentes

| Componente | Descripción |
| --- | --- |
| `Notebook/` | Carpeta que contiene los cuadernos de análisis exploratorio y procesamiento de datos. |
| `supply-chain-fraud-detection.ipynb` | Notebook principal desarrollado en Visual Studio Code con soporte para Jupyter. |
| `README.md` | Documentación técnica y descripción general del proyecto. |

---

## 🛠️ Tecnologías y Herramientas Utilizadas

| Tecnología | Aplicación |
| --- | --- |
| **Python 3.x** | Lenguaje principal del proyecto. |
| **Pandas** | Manipulación, limpieza y transformación de datos. |
| **NumPy** | Operaciones numéricas y procesamiento de variables. |
| **Matplotlib** | Construcción de visualizaciones estadísticas. |
| **Seaborn** | Visualización y análisis exploratorio de datos. |
| **Jupyter Notebook** | Desarrollo y documentación del análisis. |
| **Visual Studio Code** | Entorno de desarrollo principal. |

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.x-3776AB?style=flat-square&logo=python&logoColor=white" alt="Python" />
  <img src="https://img.shields.io/badge/Pandas-150458?style=flat-square&logo=pandas&logoColor=white" alt="Pandas" />
  <img src="https://img.shields.io/badge/NumPy-013243?style=flat-square&logo=numpy&logoColor=white" alt="NumPy" />
  <img src="https://img.shields.io/badge/Matplotlib-11557C?style=flat-square&logo=matplotlib&logoColor=white" alt="Matplotlib" />
  <img src="https://img.shields.io/badge/Seaborn-4C72B0?style=flat-square&logo=python&logoColor=white" alt="Seaborn" />
  <img src="https://img.shields.io/badge/Jupyter-F37626?style=flat-square&logo=jupyter&logoColor=white" alt="Jupyter" />
</p>

---

## ⚙️ Arquitectura del Pipeline ETL y Hallazgos Técnicos

### 1. Control de Calidad y Saneamiento de Datos

El pipeline incorpora actividades de validación y preparación de la información para mejorar la consistencia de la base de datos.

#### Procesos aplicados

- **Validación dimensional:** revisión de las dimensiones del conjunto de datos mediante `df.shape`, con un universo inicial reportado de **180.508 transacciones**.
- **Diagnóstico de valores nulos:** identificación de valores ausentes mediante `df.isna().sum()`.
- **Depuración de registros:** tratamiento dirigido de filas en variables relacionadas con la identidad del cliente.
- **Imputación controlada:** aplicación de valores neutros en códigos postales marginales para evitar inconsistencias de tipos.
- **Normalización de categorías:** estandarización de variables de texto mediante transformaciones como `.str.lower()`.

> Los tratamientos aplicados deben documentarse junto con sus criterios de exclusión o imputación para garantizar la trazabilidad del proceso de limpieza.

---

### 2. Ingeniería de Características (*Feature Engineering*)

Se generaron variables derivadas para analizar la eficiencia logística y la diferencia entre los tiempos de entrega programados y reales.

#### 📦 Varianza de Envío

Esta variable permite examinar la diferencia entre la planificación y la ejecución del proceso de entrega.

---

### 3. Inteligencia de Riesgo y Hallazgos de Negocio

#### 💰 Concentración de transacciones sospechosas

El filtrado de registros mediante la bandera `SOSPECHA_DE_FRAUDE` reportó un volumen de:

- **4.062 transacciones identificadas como fraudulentas o sospechosas**, según el resultado documentado en el análisis.

#### 💳 Vulnerabilidad asociada al método de pago

El análisis cruzado identificó que los casos sospechosos se concentran en el método de **transferencia electrónica**.

Este hallazgo puede servir como punto de partida para:

- Revisar los controles de validación de pagos.
- Analizar los procesos de conciliación financiera.
- Evaluar alertas de transacciones inusuales.
- Investigar posibles debilidades en los canales de pago.
- Diseñar controles adicionales de auditoría.

> La concentración de casos en un método de pago no demuestra por sí sola causalidad ni confirma que todas las transferencias sean fraudulentas. Se requiere validación adicional mediante reglas de negocio, revisión de casos y métricas de desempeño del modelo, si corresponde.

---

## 📊 Visualización Ejecutiva y Storytelling con Datos

El componente analítico incorpora visualizaciones orientadas a facilitar la interpretación de los resultados y la identificación de posibles riesgos operativos.

### Visualizaciones incluidas

- **Análisis de órdenes:** comparación entre órdenes con estado `COMPLETADA` y registros asociados a `SOSPECHA_DE_FRAUDE`.
- **Análisis geográfico:** representación de la tasa de entregas tardías mediante la variable `Riesgo_Entrega_Tardia`.
- **Segmentación por estado del cliente:** análisis de los riesgos de entrega según las categorías disponibles en la base de datos.

Estas visualizaciones permiten identificar patrones de comportamiento, zonas con posibles niveles elevados de fricción logística y oportunidades de revisión de los procesos asociados a proveedores de transporte.

<img width="529" alt="Visualización del análisis de fraude y riesgo logístico" src="https://github.com/user-attachments/assets/9badffee-180d-4996-a97c-f9bb34793142" />

---

## 🎯 Aplicaciones de Negocio

Los resultados del proyecto pueden servir como insumo para fortalecer los procesos de control y auditoría en la cadena de suministro:

| Área | Posible aplicación |
| --- | --- |
| **Auditoría interna** | Identificación de transacciones que requieren revisión. |
| **Control financiero** | Detección de patrones asociados a posibles fugas de capital. |
| **Gestión logística** | Análisis de entregas tardías y desempeño operativo. |
| **Gestión de proveedores** | Priorización de revisiones sobre zonas o proveedores con mayor nivel de riesgo. |
| **Gestión de pagos** | Evaluación de controles y validaciones de las modalidades de pago. |

---

## 🚀 Líneas de Mejora

Como posibles extensiones del proyecto, se pueden incorporar:

- Reglas de detección de anomalías basadas en umbrales de negocio.
- Análisis de frecuencia y monto de las transacciones.
- Matrices de riesgo por método de pago, proveedor y ubicación.
- Evaluación de precisión, recall, F1-score y matriz de confusión si se implementa un modelo supervisado.
- Monitoreo periódico de indicadores de fraude y entregas tardías.
- Automatización de reportes ejecutivos para el seguimiento de alertas.

---

## 👤 Autor

**Milton Vivero**  
*Data Analytics | Business Intelligence | Process Improvement*

> Proyecto analítico orientado a la detección de anomalías, el control financiero y la identificación de riesgos operativos en la cadena de suministro mediante herramientas de análisis de datos.

---

## 📄 Licencia

Este proyecto es de uso académico y/o demostrativo, salvo que se indique lo contrario en el repositorio. Para uso comercial o distribución externa, contactar directamente al autor.

---

<p align="center">
  <i>“Los datos transforman las señales de riesgo en oportunidades de control y mejora.”</i>
</p>
