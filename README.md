# De EDUKA a PDF: automatización de certificados académicos oficiales asistida por IA

Proyecto Final — *IA: Entretejiendo Imaginación y Algoritmos*

## Qué hace este proyecto

Automatiza la generación de documentos académicos oficiales (constancias de
escolaridad, certificados de estudios, certificados de egreso) que un liceo
uruguayo debía generar manualmente, de a uno, desde un sistema de gestión
legado. Combina:

- Un motor determinístico (`src/`) que extrae datos crudos y reconstruye la
  lógica de negocio del sistema original.
- Tres prompts de *fast prompting* (few-shot, chain-of-thought, formato de
  salida restringido) sobre la API de Claude (Anthropic).
- Dos piezas de material visual generadas con un modelo texto-imagen.

**Todos los datos de este repositorio son ficticios** — nombres, cédulas y
trayectorias académicas inventadas. Ver el notebook (sección Metodología)
para más detalle.

## Cómo correrlo

1. Instalar dependencias:
   ```bash
   pip install anthropic nbformat reportlab python-dotenv
   ```
2. Conseguir una API key gratuita en [console.anthropic.com](https://console.anthropic.com).
3. Abrir `proyecto.ipynb` (Jupyter, VS Code, o Google Colab) y correr las
   celdas en orden. La primera celda de código te pide pegar la key
   (o la toma de un archivo `.env` local — ver `.env.example`).

**Importante**: nunca escribas tu API key directamente en el código del
notebook si vas a subirlo a GitHub — usá `.env` (ya está en `.gitignore`,
no se sube) o el `getpass()` que ya trae la celda de setup.

## Estructura

```
proyecto.ipynb          # El notebook completo (informe + código)
src/                     # Motor de extracción y generación de documentos
data/ficticio/Normales/  # Dataset sintético (20 alumnos inventados)
images/                  # Material generado con texto-imagen
salida/                  # Los PDF se generan acá al correr el notebook
```
