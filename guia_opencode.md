# Guía Técnica de Referencia: OpenCode

Esta guía proporciona los comandos y conceptos esenciales para operar OpenCode de forma eficiente en un entorno de desarrollo profesional.

---

## 1. Instalación y Configuración Inicial
*   **Instalación rápida**: Se recomienda utilizar el script oficial `curl -sL https://opencode.ai/install | sh`. En **Windows**, se sugiere el uso de **WSL** para garantizar compatibilidad total.
*   **Terminales recomendadas**: Utilice emuladores modernos con soporte gráfico como **Warp, Alacritty, Ghostty o la que incluya el escritorio que se este utilizando** .
*   **Conexión**: Ejecute `/connect` en la interfaz para configurar proveedores. 
*   **OpenCode Zen**: Opción recomendada para principiantes que permite usar modelos gratuitos y verificados (como **MiniMax o Big Pickle**) sin necesidad de configurar facturación inmediata.
*   **Inicialización**: Ejecute `opencode init` en la raíz de su proyecto [11, 12]. Esto generará el archivo **`AGENTS.md`**, el cual debe ser versionado en Git para que el agente comprenda las reglas de arquitectura y el stack tecnológico del proyecto.

## 2. Conceptos Fundamentales
*   **Agente**: Entidad de IA con autonomía para analizar archivos, proponer planes de acción y ejecutar cambios directos en el código.
*   **Skill**: Estándar basado en archivos Markdown que inyecta conocimientos expertos o reglas específicas (ej. SEO, accesibilidad, React, C# etc.) al agente para mejorar su precisión.
*   **MCP (Model Context Protocol)**: Protocolo abierto para conectar al agente con herramientas, bases de datos y servicios externos de manera estandarizada.

## 3. Interfaz de Terminal (TUI) y Navegación
*   **Alternar Modos (Tecla `Tab`)**: 
    *   **Modo Plan**: El agente propone una solución sin realizar cambios en los archivos. Útil para validar lógica antes de empezar a codificar.
    *   **Modo Build**: El agente tiene permisos de escritura para implementar los cambios de código propuestos.
*   **Uso de Contexto (`@`)**: Permite buscar archivos específicos para que el agente se enfoque solo en ellos, optimizando el uso de memoria y tokens.
*   **Modo Shell (`!`)**: Permite ejecutar comandos de sistema (como `git status` o `ls`) directamente. Es fundamental para **ahorrar tokens**, ya que evita que la IA procese tareas que no requieren razonamiento.

## 4. Comandos de Control y Sesiones
*   **`/compact`**: Resume el historial de la conversación para liberar espacio de contexto y mantener la precisión en sesiones largas.
*   **`/timeline`**: Permite navegar por el historial de peticiones para recuperar ideas anteriores o bifurcar la sesión.
*   **`/undo` / `/redo`**: Deshace o rehace los cambios aplicados por el agente en los archivos físicos.
*   **`/sessions`**: Permite gestionar y saltar entre diferentes flujos de trabajo paralelos dentro del mismo proyecto.
*   **`/share`**: Genera una URL para compartir el historial completo de la sesión, incluyendo el razonamiento del agente.

## 5. Ecosistema de Skills
*   **Fuentes**: Se pueden obtener habilidades especializadas de bibliotecas como **skills.sh** o repositorios técnicos como **context7**.
*   **Auditoría y Automatización**: El comando `npx auto-skills latest` audita el proyecto para recomendar e instalar automáticamente las habilidades necesarias (SEO, diseño, etc.).
*   **Personalización**: Los usuarios pueden definir sus propios agentes y comandos personalizados en la carpeta `.open/agents` o `.open/commands` del proyecto.
