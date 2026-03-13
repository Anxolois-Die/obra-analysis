# obra-analysis

Repositorio de análisis de datos para un proyecto de construcción, basado en los partes diarios de obra.

## Descripción

Este proyecto procesa y analiza los **partes diarios** ("daily work reports") de una obra, permitiendo evaluar la productividad por oficio, detectar incidencias y comparar horas trabajadas frente a las planificadas.

El análisis prioriza siempre el estudio de incidencias antes de cualquier otro indicador.

## Archivos

| Archivo | Descripción |
|---|---|
| `partes_diarios.csv` | Datos brutos: registros diarios por oficio con horas, rendimiento e incidencias |
| `informe_productividad.md` | Informe de productividad generado a partir del CSV (período 01/03/2024 – 09/03/2024) |
| `CLAUDE.md` | Instrucciones para el asistente de análisis (Claude Code) |

## Esquema de datos (`partes_diarios.csv`)

| Columna | Descripción |
|---|---|
| `fecha` | Fecha del parte |
| `oficio` | Oficio (Albañilería, Ferrallistas, Peones…) |
| `trabajadores` | Número de trabajadores |
| `horas_trabajadas` | Horas efectivamente trabajadas |
| `horas_previstas` | Horas planificadas |
| `unidad` | Unidad de trabajo / tarea |
| `rendimiento_m2` | Productividad en m² |
| `incidencias` | Número de incidencias registradas |

## Cómo usarlo

### Análisis con Claude Code

Abre el repositorio con Claude Code y pide análisis en lenguaje natural:

```bash
cd obra-analysis
claude
```

Ejemplos de consultas:
- "Analiza las incidencias del período"
- "¿Qué oficio tiene menor eficiencia?"
- "Genera un informe de productividad"

### Análisis manual

El archivo `partes_diarios.csv` es compatible con cualquier herramienta de análisis de datos (Excel, Python/pandas, R, etc.).

```python
import pandas as pd

df = pd.read_csv("partes_diarios.csv", parse_dates=["fecha"])
print(df.groupby("oficio")[["horas_trabajadas", "horas_previstas", "incidencias"]].sum())
```

## Período actual analizado

**01/03/2024 – 09/03/2024**

- Eficiencia global: 93.4% (844h trabajadas / 904h planificadas)
- Total incidencias: 9 (concentradas en 3 días)
- m² producidos: 411 m²
