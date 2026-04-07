---
name: creador-de-skills
description: Crea nuevas Skills para AI Edge Gallery. Genera un archivo ZIP con la estructura correcta y lo descarga.
---

# Creador de Skills

## Instrucciones para el LLM

Cuando el usuario pida crear una nueva skill, **debes llamar a la herramienta `run_js`** con los siguientes parámetros exactos:

- **script_name**: `index.html`
- **data**: Un objeto JSON con los siguientes campos:
  - `nombre`: string (nombre de la skill en kebab-case)
  - `descripcion`: string (breve descripción)
  - `contenidoMd`: string (contenido completo del archivo SKILL.md)
  - `tipo`: string, puede ser `"text-only"` o `"javascript"`
  - `contenidoHtml`: string (opcional, solo si `tipo` es `"javascript"`, contiene el HTML del script)

### Flujo de trabajo

1. Pregunta al usuario qué tipo de skill necesita.
2. Pregunta qué funcionalidad y personalidad debe tener.
3. Genera el contenido de `SKILL.md` (siguiendo el formato estándar) y, si aplica, el `index.html`.
4. **Llama a `run_js`** con los datos generados.
5. Informa al usuario que el archivo ZIP se descargará automáticamente.

### Ejemplo de llamada

```json
{
  "script_name": "index.html",
  "data": {
    "nombre": "mi-asistente",
    "descripcion": "Un asistente experto en Android",
    "contenidoMd": "---\nname: mi-asistente\ndescription: ...\n---\n\n# Instrucciones...",
    "tipo": "text-only",
    "contenidoHtml": ""
  }
}
