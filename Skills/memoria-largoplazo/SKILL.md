---
name: memoria-largoplazo
description: Guarda y recupera información importante de forma persistente entre conversaciones. Permite almacenar datos relevantes, notas, preferencias del usuario y contexto para futuros chats.
metadata:
  homepage: https://github.com/Cosio33/Skills-Gallery/tree/main/Skills/memoria-largoplazo
---

# Memoria de Largo Plazo

## Instructions

Esta skill permite gestionar la memoria persistente del agente. Hay cuatro operaciones principales:

### 1. GUARDAR información
Cuando el usuario diga "guarda esto", "recuerda que", "esto es importante":

Llama `run_js` con:
- **script name**: `index.html`
- **data**: JSON string con:
  - `action`: "save"
  - `content`: El texto exacto a guardar
  - `category`: (opcional) "general", "preferencias", "proyectos", "recordatorios", "personales", "trabajo"
  - `tags`: (opcional) Array de etiquetas

### 2. BUSCAR/RECUPERAR información
Cuando el usuario pregunte "qué recuerdas", "qué guardaste sobre...", "busca en tu memoria":

Llama `run_js` con:
- **script name**: `index.html`
- **data**: JSON string con:
  - `action`: "search"
  - `query`: Términos de búsqueda (vacío para ver todo)

### 3. VER memoria completa
Cuando el usuario quiera "ver toda tu memoria", "gestionar recuerdos":

Llama `run_js` con:
- **script name**: `index.html`
- **data**: JSON string con:
  - `action`: "view"

### 4. BORRAR información
Cuando el usuario diga "olvida esto", "borra de tu memoria":

Llama `run_js` con:
- **script name**: `index.html`
- **data**: JSON string con:
  - `action`: "delete"
  - `id`: ID del recuerdo a borrar (o "all" para borrar todo)

---

IMPORTANTE: El sistema mostrará automáticamente el webview interactivo desde `assets/webview.html` después de cada operación.
