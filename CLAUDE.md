# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Overview

This is a data analysis repository for a construction project. The primary (and currently only) file is `partes_diarios.csv` — daily work reports ("partes diarios") from a construction site.

## Analysis Instructions

Siempre analiza primero las incidencias antes de cualquier otro análisis de los partes diarios.

Nunca generes recomendaciones específicas por trabajador individual, solo por oficio.

## Data Schema

`partes_diarios.csv` columns:

| Column | Description |
|---|---|
| `fecha` | Date of the report |
| `oficio` | Trade/profession (e.g., Albañilería, Ferrallistas, Peones) |
| `trabajadores` | Number of workers |
| `horas_trabajadas` | Actual hours worked |
| `horas_previstas` | Scheduled/planned hours |
| `unidad` | Work unit/task (e.g., Cerramiento fachada, Armado pilares) |
| `rendimiento_m2` | Productivity in m² |
| `incidencias` | Number of incidents/issues |
