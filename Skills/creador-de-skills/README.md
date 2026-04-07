
### 🚀 Cómo Usar la Skill Creadora

Sigue estos pasos para ponerla en marcha:

1.  **Crea la skill creadora**: Carga los dos archivos en la app Gallery como una skill normal.
2.  **Inicia una conversación**: Pídele que cree una nueva skill. Por ejemplo: *"Crea una skill para analizar código Kotlin y que tenga una personalidad amigable"*.
3.  **Observa el proceso**: El asistente te hará preguntas para definir la nueva skill y generará el contenido de `SKILL.md`.
4.  **Guarda en el teléfono**: El asistente invocará `window.crearSkill` y te pedirá que selecciones la carpeta raíz. Elige una ubicación como "Documentos" o "Descargas".
5.  **Carga la nueva skill en Gallery**: Abre la app, ve a "Agent Skills", selecciona "Import from Folder" y elige la carpeta raíz que contiene la carpeta 'skills'. Gallery encontrará automáticamente todas las subcarpetas con su `SKILL.md`.

### 💡 Tips y Consideraciones Clave

*   **Estructura correcta**: Es fundamental que el JSON devuelto por el asistente tenga **exactamente** los tres campos: `nombre`, `descripcion` y `contenidoMd`. Así se garantiza que el `index.html` reciba los datos correctos.
*   **API de directorios**: El código usa la API `window.showDirectoryPicker`, que funciona de maravilla en el contexto de la app Gallery.
*   **Múltiples skills**: La skill creadora siempre genera las nuevas skills dentro de la carpeta `skills/` que elijas. Esto te permite tener todas tus creaciones organizadas y listas para que Gallery las detecte.

### ⚠️ Solución de Problemas Comunes

*   **El selector de carpeta no se abre**: Asegúrate de haber invocado `crearSkill` desde el chat y de que el agente haya generado el JSON correctamente.
*   **Gallery no ve la nueva skill**: Confirma que el archivo se haya guardado en `skills/[nombre-de-la-skill]/SKILL.md` y que el `name` en el YAML coincida con el nombre de la carpeta.
  
