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

## 🧩 Componentes principales

### `main.py`

Es el núcleo de la aplicación. Se encarga de orquestar todo el flujo de generación del informe:

- Carga los archivos JSON de entrada (`alert.json` y `events.json`)
- Procesa los datos del incidente
- Construye el documento PDF usando ReportLab
- Genera tablas, encabezados y secciones estructuradas
- Guarda el informe final en la carpeta `output`

Funciones principales:

- `load_json(path)`: carga archivos JSON de entrada
- `generate_pdf(alert, events)`: genera el informe PDF completo
- Bloque `if __name__ == "__main__"`: punto de entrada de la aplicación

---

### `template.html.j2`

Plantilla HTML de referencia utilizada para definir la estructura visual del informe.

Aunque la versión actual genera el PDF directamente desde Python (ReportLab),
esta plantilla se conserva para:

- Documentar la estructura lógica del informe
- Facilitar una futura implementación HTML → PDF
- Separar diseño y lógica de negocio

---

### `alert.json`

Archivo JSON que define los **metadatos principales del incidente**, incluyendo:

- Identificador del incidente
- Título, severidad y estado
- Lista de activos afectados
- Indicadores de compromiso (IOCs)
- Recomendaciones de mitigación

---

### `events.json`

Archivo JSON que contiene la **línea temporal del incidente**.

Cada evento incluye:
- Marca temporal
- Regla o tipo de evento
- Mensaje descriptivo

Estos datos se utilizan para generar la sección de timeline del informe PDF.

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
