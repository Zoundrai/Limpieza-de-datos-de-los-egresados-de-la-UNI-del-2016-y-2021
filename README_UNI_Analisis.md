# 📊 Análisis de Admisión UNI — Acceso, Género y Nivel Socioeconómico (2016 – 2021)

**Herramientas:** Python · Pandas · Matplotlib · Seaborn · Power BI  
**Datos:** Datasets de postulantes e ingresantes a la Universidad Nacional de Ingeniería (UNI), años 2016 y 2021  
**Registros procesados:** 42,516

---

## 🎯 Objetivo

Este proyecto analiza los patrones de acceso a la Universidad Nacional de Ingeniería (UNI) con el fin de responder las siguientes preguntas:

- ¿Influye el lugar de procedencia (Lima vs. provincia) en la probabilidad de ingresar?
- ¿Existen diferencias en el ingreso según género?
- ¿Qué carreras concentran más ingresantes? ¿Varía esto por género?
- ¿El nivel socioeconómico tiene relación con la carrera elegida?

---

## 📁 Estructura del proyecto

```
├── notebooks/
│   ├── 01_limpieza.ipynb     # Limpieza y preparación de datos
│   └── 02_analisis.ipynb     # Análisis exploratorio y visualizaciones
└── README.md
```

---

## 🧹 Proceso de limpieza de datos

Los datasets originales (2016 y 2021) se obtuvieron en formato tabular con delimitadores mal configurados, lo que hacía que al abrirlos en Excel todos los campos aparecieran comprimidos en una sola columna. El primer paso fue identificar el separador correcto y cargar los archivos de forma legible con `pandas`.

Una vez cargados, se identificaron y corrigieron los siguientes problemas:

- **Valores nulos y celdas vacías:** varias filas presentaban campos vacíos en las columnas de procedencia (distrito/región) y nivel socioeconómico. Se evaluó cada caso: los registros con campos críticos vacíos fueron eliminados; los secundarios se imputaron o marcaron como "No especificado".
- **Nombres de carreras inconsistentes:** la misma carrera aparecía escrita de múltiples formas (mayúsculas, abreviaciones, con y sin tildes). Se estandarizaron todos los valores a un formato único para poder agruparlos correctamente en el análisis.
- **Registros duplicados:** se detectaron filas repetidas, probablemente por errores en la exportación original del sistema. Fueron eliminados con `drop_duplicates()`.
- **Tipos de dato incorrectos:** columnas de códigos numéricos estaban cargadas como `float` (con decimales innecesarios) y algunas fechas como texto. Se convirtieron al tipo correcto para permitir operaciones de filtrado y agrupación.

Tras la limpieza, los dos datasets fueron unificados en un solo DataFrame con una columna `año` para permitir comparaciones entre 2016 y 2021.

**Herramientas usadas:** `pandas`, `numpy`

---

## 📈 Hallazgos principales

### 1. Brecha geográfica
Los postulantes provenientes de provincia presentan una tasa de ingreso significativamente menor a la de postulantes de Lima, lo que evidencia una desigualdad en el acceso a la UNI según el lugar de origen.

### 2. Distribución por género
La mayoría de ingresantes en carreras de ingeniería son hombres. Las carreras con mayor presencia femenina son [completar con tu hallazgo específico].

### 3. Carreras más demandadas
Las carreras con mayor número de ingresantes en ambos años son [completar]. Se observa [aumento/disminución] en la demanda de [carrera] entre 2016 y 2021.

### 4. Nivel socioeconómico y carrera elegida
[Completar con tu hallazgo — por ejemplo: "Los postulantes de nivel socioeconómico bajo se concentran en carreras como X, mientras que los de nivel alto tienden a postular a Y."]

---
## ▶️ Cómo reproducir el análisis

1. Clona el repositorio:
```bash
git clone https://github.com/tu-usuario/uni-admision-analisis.git
```

2. Instala las dependencias:
```bash
pip install pandas matplotlib seaborn jupyter
```

3. Ejecuta los notebooks en orden:
   - `01_limpieza.ipynb` → limpia y exporta los datos procesados
   - `02_analisis.ipynb` → genera el análisis y las visualizaciones

---

## 👤 Autor

**Axel James Santibañez Obando**  
Estudiante de Ingeniería Informática — Universidad Ricardo Palma  
[linkedin.com/in/axelsantibañez](https://www.linkedin.com/in/axelsantibañez)
