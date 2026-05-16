GUÍA TÉCNICA DE REFERENCIA: OPENCODE
Esta hoja de instrucciones está diseñada para proporcionar los comandos y conceptos esenciales para operar OpenCode de forma eficiente en un entorno de desarrollo.

--------------------------------------------------------------------------------
1. Instalación y Configuración Inicial

    Instalación: Se recomienda utilizar el script oficial para una configuración automática. En sistemas Windows, se sugiere el uso de WSL para garantizar la compatibilidad total de funciones.
    Terminales: Para una integración visual óptima, se recomienda el uso de emuladores modernos como Warp, Alacritty, Ghostty o la que tenga instalada el sistema.
    Conexión: Ejecute /connect para configurar los proveedores de inteligencia artificial.
    OpenCode Zen: Opción recomendada para principiantes que permite usar modelos verificados y gratuitos (como MiniMax o Big Pickle) sin necesidad de configurar facturación inmediata.
    Inicialización: Ejecute opencode init en la raíz de su proyecto. Esto generará el archivo AGENTS.md, el cual debe ser versionado en Git para que el agente comprenda las reglas de arquitectura, el stack tecnológico y los patrones de código del proyecto.

2. Conceptos Fundamentales

    Agente: Entidad de IA con autonomía para analizar el sistema de archivos, proponer planes de acción y ejecutar cambios directos en el código fuente.
    Skill: Estándar basado en archivos Markdown que inyecta conocimientos expertos o reglas específicas (ej. SEO, accesibilidad o React) al agente para mejorar su precisión.
    MCP (Model Context Protocol): Protocolo abierto que permite conectar al agente con herramientas, bases de datos y servicios externos de manera estandarizada.

3. Interfaz de Terminal (TUI) y Navegación

    Alternar Modos (Tecla Tab):
        Modo Plan: El agente analiza y propone una solución sin realizar cambios en los archivos. Útil para validar la lógica antes de construir.
        Modo Build: El agente tiene permisos de escritura para implementar los cambios de código propuestos.
    Uso de Contexto (@): Permite buscar archivos específicos para que el agente se enfoque solo en ellos, optimizando el uso de memoria y tokens.
    Modo Shell (!): Permite ejecutar comandos de sistema (como ls o git status) directamente. Es fundamental para ahorrar tokens, ya que evita que la IA procese tareas que no requieren razonamiento.

4. Comandos de Control y Sesiones

    /compact: Resume el historial de la conversación para liberar espacio en la ventana de contexto, manteniendo la precisión del modelo en sesiones largas.
    /timeline: Permite navegar por el historial de peticiones para recuperar ideas anteriores o bifurcar la sesión de trabajo.
    /undo / /redo: Deshace o rehace los cambios aplicados por el agente en los archivos físicos.
    /sessions: Permite gestionar y saltar entre diferentes flujos de trabajo paralelos dentro del mismo proyecto.
    /share: Genera una URL para compartir el historial completo de la sesión, incluyendo el razonamiento del agente y los cambios realizados.

5. Ecosistema de Skills

    Fuentes: Se pueden obtener habilidades especializadas de bibliotecas como skills.sh o repositorios técnicos como context7.
    Auditoría y Automatización: El uso de npx auto-skills latest permite auditar el proyecto para recomendar e instalar automáticamente las habilidades de seguridad, diseño o SEO necesarias.
    Personalización: Los usuarios pueden definir sus propios agentes con permisos específicos (solo lectura o ejecución de comandos restringidos) creando archivos en la carpeta de configuración del proyecto.
