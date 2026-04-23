# Automated Incident Report Generator

Automated Incident Report Generator es una herramienta en Python que genera informes profesionales de incidentes de seguridad en formato PDF a partir de archivos JSON estructurados.

El objetivo del proyecto es **estandarizar y automatizar** la documentación de incidentes, facilitando el análisis, la trazabilidad y la presentación de evidencias.

---

## Características

- Generación automática de informes PDF
- Entrada de datos mediante archivos JSON
- Timeline de eventos del incidente
- Listado de activos afectados
- Indicadores de compromiso (IOCs)
- Recomendaciones de mitigación
- Diseño claro y estructurado usando ReportLab

---

## Tecnologías utilizadas

- Python 3
- ReportLab
- JSON
- Virtualenv

---

## Estructura del proyecto

```
text
incident-report-generator/
│
├── app/
│   ├── main.py              # Lógica principal del generador
│   └── template.html.j2     # Plantilla HTML (referencia)
│
├── samples/
│   ├── alert.json           # Datos del incidente
│   └── events.json          # Timeline de eventos
│
├── output/
│   └── reporte.pdf          # PDF generado
│
├── requirements.txt
├── .gitignore
└── README.md
``
