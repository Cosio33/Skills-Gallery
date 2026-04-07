# 🧠 AI Edge Skills – Personalidad y Memoria para Agentes en Español

Este repositorio contiene una colección de **Skills** para la plataforma [AI Edge Gallery](https://github.com/google-ai-edge/gallery), diseñadas para dotar a los agentes de inteligencia artificial de personalidad, memoria persistente y capacidades de análisis técnico, todo en español.

## 🚀 ¿Qué es una Skill?

Una Skill es un conjunto de instrucciones (y opcionalmente código JavaScript) que define el comportamiento, la personalidad y las capacidades de un agente dentro de la app **AI Edge Gallery**. Las skills se ejecutan en un entorno seguro (sandbox) y pueden ser:

- **Text‑only skills**: Solo un archivo `SKILL.md` con metadatos y un prompt de sistema. Son ideales para personalidades, guías o flujos conversacionales.
- **JavaScript skills**: Incluyen un `index.html` con lógica personalizada. Permiten almacenamiento local (`localStorage`), llamadas a APIs, cálculos dinámicos y, como mostramos aquí, **memoria persistente** entre conversaciones.

## 📂 Estructura del repositorio
