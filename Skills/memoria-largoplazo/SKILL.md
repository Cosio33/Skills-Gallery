---
name: memoria-largoplazo
description: Guarda y recupera información importante de forma persistente entre conversaciones. Permite almacenar datos relevantes, notas, preferencias del usuario y contexto para futuros chats.
metadata:
  homepage: https://github.com/Cosio33/Skills-Gallery/tree/main/Skills/memoria-largoplazo
  require-secret: false
---

# Memoria de Largo Plazo

## Instructions

Esta skill permite gestionar la memoria persistente del agente. Hay tres operaciones principales:

### 1. GUARDAR información
Cuando el usuario diga algo como "guarda esto", "recuerda que", "esto es importante", "agrega a tu memoria":

Llama `run_js` con:
- **script name**: `index.html`
- **data**: JSON string con:
  - `action`: "save"
  - `content`: El texto exacto que el usuario quiere guardar
  - `category`: (opcional) Categoría sugerida: "general", "preferencias", "proyectos", "recordatorios", "personales"
  - `tags`: (opcional) Array de etiquetas para facilitar búsqueda

### 2. BUSCAR/RECUPERAR información
Cuando el usuario pregunte "qué recuerdas", "qué guardaste sobre...", "busca en tu memoria", "recuerdas cuando hablamos de...":

Llama `run_js` con:
- **script name**: `index.html`
- **data**: JSON string con:
  - `action`: "search"
  - `query`: Términos de búsqueda (puede ser vacío para ver todo)

### 3. VER/MANAGE memoria
Cuando el usuario quiera "ver toda tu memoria", "gestionar recuerdos", "borrar algo que guardaste":

Llama `run_js` con:
- **script name**: `index.html`
- **data**: JSON string con:
  - `action`: "view"

### 4. BORRAR información
Cuando el usuario diga "olvida esto", "borra de tu memoria", "elimina el recuerdo":

Llama `run_js` con:
- **script name**: `index.html`
- **data**: JSON string con:
  - `action`: "delete"
  - `id`: El ID del recuerdo a borrar (o "all" para borrar todo)

---

## Ejemplos de uso:

**Usuario**: "Guarda que mi color favorito es el azul marino"
→ action: "save", content: "Color favorito del usuario: azul marino", category: "preferencias", tags: ["color", "favorito"]

**Usuario**: "¿Qué recuerdas sobre mis proyectos?"
→ action: "search", query: "proyectos"

**Usuario**: "Muéstrame todo lo que has guardado"
→ action: "view"

---

IMPORTANTE: Después de cada operación, el sistema mostrará un webview interactivo donde el usuario puede ver, editar o gestionar sus recuerdos almacenados.
