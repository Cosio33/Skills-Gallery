# 🧠 AI Edge Skills – Personalidad y Memoria para Agentes en Español

Este repositorio contiene una colección de **Skills** para la plataforma [AI Edge Gallery](https://github.com/google-ai-edge/gallery), diseñadas para dotar a los agentes de inteligencia artificial de personalidad, memoria persistente y capacidades de análisis técnico, todo en español.

## 🚀 ¿Qué es una Skill?

Una Skill es un conjunto de instrucciones (y opcionalmente código JavaScript) que define el comportamiento, la personalidad y las capacidades de un agente dentro de la app **AI Edge Gallery**. Las skills se ejecutan en un entorno seguro (sandbox) y pueden ser:

- **Text‑only skills**: Solo un archivo `SKILL.md` con metadatos y un prompt de sistema. Son ideales para personalidades, guías o flujos conversacionales.
- **JavaScript skills**: Incluyen un `index.html` con lógica personalizada. Permiten almacenamiento local (`localStorage`), llamadas a APIs, cálculos dinámicos y, como mostramos aquí, **memoria persistente** entre conversaciones.


Cada skill vive en su propia subcarpeta dentro de `skills/`. El nombre de la carpeta debe ir en **kebab-case** (ej. `analizador-android`).

## ✨ Skills incluidas (ejemplos)

| Skill | Tipo | Descripción |
|-------|------|-------------|
| `asistente-con-memoria` | JavaScript | Agente que recuerda su personalidad y preferencias entre chats usando `localStorage`. |
| `mi-asistente-espanol` | Text‑only | Asistente tecnológico con personalidad cálida y respuestas obligatorias en español. |

> 🔜 Próximamente: skill para analizar logs de Android, otra para generar informes de rendimiento de apps, etc.

## 🛠️ Cómo crear tu propia Skill

### 1. Skill de solo texto (personalidad fija)

1. Crea una carpeta con el nombre deseado dentro de `skills/`.
2. Dentro, crea un archivo `SKILL.md` con este formato:

```markdown
---
name: nombre-de-la-carpeta
description: Breve descripción de lo que hace (el LLM la usa para activar la skill)
---

# Título opcional

## Personalidad
Eres un experto en...

## Reglas
- Siempre habla en español.
- …


