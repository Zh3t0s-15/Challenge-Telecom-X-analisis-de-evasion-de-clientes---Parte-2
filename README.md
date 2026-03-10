# Telecom X – Análisis y predicción de cancelación (Churn)

Proyecto completo de análisis de datos y **Machine Learning** para el **Challenge 2 - Data Science LATAM**. Incluye EDA, limpieza de datos y modelos predictivos para identificar clientes en riesgo de cancelar sus servicios en Telecom X.

---

## Resumen del proyecto

Este proyecto se divide en dos partes:

| Parte | Descripción |
|-------|-------------|
| **Parte 1** | Extracción, transformación, limpieza de datos y análisis exploratorio (EDA) |
| **Parte 2** | Preparación para modelado, entrenamiento de clasificadores y evaluación de resultados |

---

## Propósito

- **Contexto:** Telecom X enfrenta una alta tasa de cancelaciones (churn). El objetivo es entender los factores asociados a la evasión y predecir qué clientes tienen mayor probabilidad de cancelar.
- **Objetivos:**
  - Extraer y limpiar datos desde la API (JSON).
  - Realizar **análisis exploratorio (EDA)** con visualizaciones.
  - Entrenar **modelos de clasificación** para predecir la cancelación.
  - Evaluar el rendimiento con métricas (accuracy, precisión, recall, F1-score).
  - Interpretar la **importancia de variables** y proponer estrategias de retención.

---

## Estructura del proyecto

```
challenge2-telecom-churn/
├── README.md              # Este archivo
├── TelecomX_Churn.ipynb   # Notebook con EDA y modelado predictivo
└── .gitignore
```

---

## Contenido del notebook

### Parte 1 – Análisis exploratorio (EDA)

1. **Extracción:** Carga de datos desde la API (JSON → DataFrame).
2. **Estructura:** Exploración de columnas y tipos de datos.
3. **Calidad:** Verificación de ausentes, duplicados y formato.
4. **Limpieza:** Conversión de tipos, imputación de ausentes y eliminación de duplicados.
5. **Transformación:** Creación de variables derivadas (`cuenta_diaria`, binarios).
6. **Análisis descriptivo:** Media, mediana, desviación estándar.
7. **Distribución de cancelación:** Gráficos de barras y torta.
8. **Variables numéricas vs cancelación:** Boxplots.
9. **Correlación:** Matriz de correlación y gráficos de dispersión.
10. **Informe EDA:** Conclusiones y recomendaciones iniciales.

### Parte 2 – Modelado predictivo (Machine Learning)

11. **Preparación para modelado:**
    - Eliminación de columnas irrelevantes (ej. `id_cliente`).
    - Codificación categórica (one-hot encoding).
    - Análisis de balance de clases.
12. **Entrenamiento de modelos:**
    - **Regresión Logística** (con normalización `StandardScaler`).
    - **Random Forest** (sin normalización).
13. **Evaluación:**
    - Métricas: Accuracy, precisión, recall, F1-score.
    - Matrices de confusión.
    - Análisis de importancia de variables.
14. **Conclusiones estratégicas:** Factores de churn y estrategias de retención.

---

## Fuente de datos (API)

Los datos se obtienen de una API pública en formato JSON:

| Campo | Valor |
|-------|-------|
| **URL** | `https://raw.githubusercontent.com/ingridcristh/challenge2-data-science-LATAM/main/TelecomX_Data.json` |
| **Formato** | JSON (estructura anidada por cliente) |
| **Contenido** | Información de clientes, servicios contratados, cuentas y cancelación |

No requiere autenticación ni archivos locales; la carga se hace directamente desde el notebook.

---

## Modelos de Machine Learning

| Modelo | Normalización | Razón |
|--------|---------------|-------|
| **Regresión Logística** | Sí (`StandardScaler`) | Los modelos lineales son sensibles a la escala; la normalización evita que variables con magnitudes mayores dominen el modelo. |
| **Random Forest** | No | Los árboles de decisión dividen por umbrales de cada variable por separado; la escala no afecta el resultado. |

### Métricas de evaluación

- **Accuracy:** Porcentaje total de predicciones correctas.
- **Precisión:** De los que el modelo predijo como churn, cuántos realmente cancelaron.
- **Recall:** De los que realmente cancelaron, cuántos detectó el modelo.
- **F1-score:** Media armónica entre precisión y recall; útil cuando las clases están desbalanceadas.
- **Matriz de confusión:** Desglose de verdaderos positivos, falsos positivos, verdaderos negativos y falsos negativos.

---

## Variables principales (español)

| Variable | Descripción |
|----------|-------------|
| `cancelacion` | Indica si el cliente canceló (Yes/No) |
| `meses_tenencia` | Tiempo como cliente en meses |
| `cargos_mensuales` | Cargos mensuales |
| `cargos_totales` | Total facturado |
| `cuenta_diaria` | Cargos mensuales / 30 |
| `tipo_contrato` | Month-to-month, One year, Two year |
| `metodo_pago` | Forma de pago |
| `num_servicios` | Cantidad de servicios contratados |

---

## Requisitos e instalación

### Dependencias

- Python 3.8+
- `pandas`, `requests`, `matplotlib`, `seaborn`, `scikit-learn`

### Instalación

```bash
pip install pandas requests matplotlib seaborn scikit-learn
```

### Opción 1: Google Colab

1. Abre [Google Colab](https://colab.research.google.com).
2. Sube `TelecomX_Churn.ipynb` o ábrelo desde GitHub.
3. Ejecuta todas las celdas (**Runtime → Run all**).

Los datos se cargan automáticamente desde la API; no hace falta subir archivos.

### Opción 2: Ejecución local

```bash
git clone https://github.com/TU_USUARIO/challenge2-telecom-churn.git
cd challenge2-telecom-churn
pip install pandas requests matplotlib seaborn scikit-learn
jupyter notebook TelecomX_Churn.ipynb
```

Ejecuta las celdas en orden de arriba hacia abajo.

---

## Conclusiones principales

- Los clientes con **menor tiempo de tenencia** y **menor total gastado** tienen mayor riesgo de cancelación.
- El **tipo de contrato** (month-to-month) está fuertemente asociado al churn.
- Los modelos de Regresión Logística y Random Forest permiten identificar variables clave para diseñar campañas de retención.
- Recomendaciones: enfocar retención en clientes nuevos, incentivar contratos de largo plazo y usar alertas tempranas basadas en las variables más relevantes.

---

## Repositorio en GitHub

```bash
git add .
git commit -m "Telecom X - EDA y modelos predictivos de churn"
git push origin main
```

---

Desarrollado como parte del **Challenge 2 - Data Science LATAM** (Telecom X).
