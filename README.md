# Telecom X – Análisis de evasión de clientes (Churn)

Proyecto de análisis de datos para el **Challenge 2 - Data Science LATAM**. El objetivo es analizar los datos de clientes de Telecom X, identificar factores asociados a la evasión (churn) y generar insights para reducir la cancelación.

---

## Propósito del análisis

- **Contexto:** La empresa Telecom X enfrenta una alta tasa de cancelaciones. Este proyecto forma parte del programa "Churn de Clientes".
- **Objetivos:**
  - Importar y manipular datos desde la API (JSON).
  - Aplicar conceptos de **ETL** (Extracción, Transformación, Carga).
  - Realizar **análisis exploratorio (EDA)** y crear visualizaciones para identificar patrones.
  - Generar un **informe** con conclusiones e insights que apoyen estrategias de retención y futuros modelos predictivos.

---

## Estructura del proyecto

```
challenge2-telecom-churn/
├── README.md              # Este archivo
├── TelecomX_Churn.ipynb    # Notebook con todo el análisis
└── .gitignore
```

**Contenido del notebook:**

1. Extracción de datos desde la API (JSON → DataFrame).
2. Exploración de estructura y tipos de datos.
3. Verificación de calidad (ausentes, duplicados, formato).
4. Limpieza y tratamiento de datos.
5. Creación de la columna `Cuentas_Diarias`.
6. Estandarización opcional (Sí/No → 1/0).
7. Análisis descriptivo (media, mediana, desviación estándar).
8. Distribución de Churn (gráficos).
9. Variables numéricas vs. Churn (boxplots).
10. Análisis de correlación (opcional): matriz de correlación y dispersión.
11. Informe final: introducción, limpieza, EDA, conclusiones y recomendaciones.

---

## Gráficos e insights

- **Distribución de Churn:** proporción de clientes que permanecen vs. que se dan de baja (barras y pie).
- **Variables numéricas vs. Churn:** boxplots de TotalCharges, tenure, MonthlyCharges y Cuentas_Diarias por grupo de Churn; permiten ver que menor tiempo de relación y menor gasto total se asocian más a evasión.
- **Matriz de correlación:** relación entre variables numéricas y Churn (binario).
- **Dispersión Cuentas_Diarias vs TotalCharges** coloreada por Churn.
- **Cantidad de servicios contratados** y su relación con la probabilidad de churn (extra opcional).

**Conclusiones principales:** Los clientes con bajo tenure, contrato month-to-month y menor total gastado presentan mayor riesgo de churn. La cuenta diaria y el número de servicios contratados aportan información útil para retención y modelos predictivos.

---

## Instrucciones para ejecutar el notebook

### Requisitos

- **Python 3** (recomendado 3.8+).
- Dependencias: `pandas`, `requests`, `matplotlib`, `seaborn`.

### Opción 1: Google Colab (recomendada)

1. Abre [Google Colab](https://colab.research.google.com).
2. **Archivo** → **Subir cuaderno** y selecciona `TelecomX_Churn.ipynb`.
3. **Runtime** → **Run all** (o ejecuta celda por celda con Shift+Enter).

Los datos se cargan desde la URL de la API; no hace falta subir archivos.

### Opción 2: Ejecución local

1. Clona o descarga este repositorio.
2. Crea un entorno virtual (opcional) e instala dependencias:

   ```bash
   pip install pandas requests matplotlib seaborn
   ```

3. Abre el notebook con Jupyter Notebook o VS Code/Cursor:

   ```bash
   jupyter notebook TelecomX_Churn.ipynb
   ```

4. Ejecuta todas las celdas en orden.

### Posibles problemas

- **`requests` no encontrado:** instala con `pip install requests`.
- **`seaborn` no encontrado:** instala con `pip install seaborn` (opcional; si no está, comenta o elimina la celda del heatmap).
- **API no responde:** verifica conexión a internet; la URL usa el repositorio público de GitHub.

---

## Repositorio en GitHub

Este proyecto está pensado para versionarse en GitHub. Después de clonar o crear el repo:

```bash
git add .
git commit -m "Análisis Churn Telecom X - ETL, EDA e informe"
git remote add origin https://github.com/TU_USUARIO/challenge2-telecom-churn.git
git push -u origin main
```

(Ajusta `TU_USUARIO` y el nombre del repositorio.)

---

Desarrollado como parte del Challenge 2 - Data Science LATAM (Telecom X).
