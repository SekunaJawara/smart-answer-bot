# 🤖 Smart Answer Bot

Agente de investigación basado en LangChain y Claude que responde consultas utilizando búsqueda web, Wikipedia y almacenamiento de resultados.

## ¿Qué hace?

El agente recibe una pregunta del usuario y de forma autónoma decide qué herramientas usar para responder. La respuesta final se devuelve en un formato estructurado con el tema, resumen, fuentes y herramientas utilizadas.

## Estructura del proyecto

```
smart-answer-bot/
├── main.py          # Agente principal y lógica de ejecución
├── tools.py         # Definición de herramientas del agente
├── .env             # Variables de entorno (no subir a git)
├── requirements.txt
└── README.md
```

## Herramientas disponibles

- **DuckDuckGo Search** — búsqueda web en tiempo real
- **Wikipedia** — consulta de artículos de Wikipedia
- **Save to file** — guarda los resultados en `research_output.txt`

## Requisitos

- Python 3.12+
- Cuenta en [Anthropic](https://console.anthropic.com) con API key

## Instalación

```bash
# Clonar el repositorio
git clone <url-del-repo>
cd smart-answer-bot

# Crear y activar el entorno virtual
python -m venv venv
source venv/bin/activate  # Mac/Linux
venv\Scripts\activate     # Windows

# Instalar dependencias
pip install -r requirements.txt
```

## Configuración

Crea un archivo `.env` en la raíz del proyecto:

```
ANTHROPIC_API_KEY=sk-ant-...
```

## Uso

```bash
python main.py
```

El bot te pedirá una consulta y devolverá una respuesta estructurada como esta:

```
topic: "Capital de España"
summary: "Madrid es la capital de España..."
sources: ["https://...", "https://..."]
tools_used: ["search", "wikipedia"]
```

## Dependencias principales

- `langchain` — framework de agentes
- `langchain-anthropic` — integración con Claude
- `langchain-community` — herramientas de búsqueda y Wikipedia
- `python-dotenv` — gestión de variables de entorno
- `pydantic` — validación de la respuesta estructurada