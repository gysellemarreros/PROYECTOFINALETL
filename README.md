
# ETL CANTIDAD de PRODUCTOS MAS VENDIDOS EN UNA MARCA DE ROPA

Arquitectura Medallion en Azure Databricks

Pipeline automatizado de datos para mostrar los productos mas vendidos  en una marca de ropa de dama  con arquitectura de tres capas y despliegue continuo.
## 🎯 Descripción

Pipeline ETL que transforma datos crudos de ventas, detalle de ventas y productos de una marca, implementando la Arquitectura Medallion (Bronze-Silver-Gold) en Azure Databricks con CI/CD completo y Delta Lake para garantizar consistencia ACID.

## ✨ Características Principales

* 🔄 ETL Automatizado - Pipeline completo con despliegue automático via GitHub Actions
* 🏗️ Arquitectura Medallion - Separación clara de capas Bronze → Silver → Gold
* 📊 Modelo Dimensional - Star Schema optimizado para análisis de negocio
* 🚀 CI/CD Integrado - Deploy automático en cada push a master
* 📈 Databricks Dashboards - Visualización
* ⚡ Delta Lake - ACID transactions y time travel capabilities
* 🔔 Monitoreo - Notificaciones automáticas y logs detallados

## 🏛️ Arquitectura


![Texto descriptivo](Arquitectura.png)


## Capas del Pipeline

![pipeline](pipeline.png)

## 🚀 Instalación y Configuración

### 1️⃣ Clonar el Repositorio

```bash
git clone https://https://github.com/gysellemarreros/PROYECTOFINALETL
cd databricks_project
```

### 4️⃣ Verificar Storage Configuration

```python
storage_path = "abfss://raw@storageproject99.dfs.core.windows.net"
```


✅ **¡Configuración completa!**


---

## 💻 Uso

### 🔄 Despliegue Automático (Recomendado)

```bash
git add .
git commit -m "✨ feat: mejoras en pipeline"
git push origin master
```

**GitHub Actions ejecutará**:
- 📤 Deploy de notebooks a `/Workspace/databricks_project/proceso`
- 🔧 Creación del workflow `WF_ToPVentasProductos`
- ▶️ Ejecución completa:  Bronze → Silver → Gold
- 📧 Notificaciones de resultados

### 🖱️ Despliegue Manual desde GitHub

1. Ir al tab **Actions** en GitHub
2. Seleccionar **Deploy ETL Apple Sales And Warranty**
3. Click en **Run workflow**
4. Seleccionar rama `main`
5. Click en **Run workflow**

### 🔧 Ejecución Local en Databricks

Navegar a `/Workspace/databricks_project/proceso` y ejecutar en orden:

```
- 0_preparacion_ambiente.py         → Crear esquema
- 1_ingest_ciclo.py                 → Bronze Layer
- 1_ingest_matricula.py             → Bronze Layer
- 1_ingest_programa.py              → Bronze Layer
- 2_transform_mat_escuela.py        → Silver Layer
- 2_transform_prog_estatus.py       → Silver Layer
- 3_load.py                         → Gold Layer
```

---


### 🔄  Workflow Databricks
![Texto descriptivo](evidencias/WF_ToPVentasProductos.png)


## 📈 Dashboards
https://github.com/Enrykiel/databricks_project/tree/main/dashboard

## 🔍 Monitoreo

### En Databricks

**Workflows**:
- Ir a **Workflows** en el menú lateral
- Buscar `WF_PROD_ETF_INSTITUTO`
- Ver historial de ejecuciones

**Logs por Tarea**:
- Click en una ejecución específica
- Click en cada tarea para ver logs detallados
- Revisar stdout/stderr en caso de errores

### En GitHub Actions

- Tab **Actions** del repositorio
- Ver historial de workflows
- Click en ejecución específica para detalles
- Revisar logs de cada step

---

## 👤 Autor


### Gyselle Marreros

[![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/gysellemarreros)

---


**Proyecto**: Data Engineering - Arquitectura Medallion  
**Tecnología**: Azure Databricks + Delta Lake