Actividad

Checkpoint de Configuración e Interfaces Agénticas
Objetivos de Aprendizaje
Diferenciar visualmente en la interfaz de usuario los componentes de un proceso que requieren automatización lineal determinista de aquellos candidatos a la autonomía probabilística del ciclo ReAct.
Diseñar e implementar instrucciones de sistema profesionales (System Messages) estructuradas de forma modular, acotando el rol y mitigando alucinaciones.
Parametrizar puntos de control y guardrails de iteración máxima en el panel avanzado para blindar el presupuesto financiero de la organización.
Ficha de la Actividad
Actividad: Configuración del "Tools Agent" y el Motor de Razonamiento Base
Objetivo: Diseñar, configurar y validar visualmente el nodo de razonamiento central (AI Agent Node) en modo Tools Agent, estructurando su System Prompt operativo profesional y delimitando físicamente sus guardrails de iteración y sus herramientas asociadas.
Instrucciones Paso a Paso:
Ingresar al lienzo gráfico de n8n, arrastrar el nodo avanzado AI Agent y seleccionar en su configuración el modo Tools Agent.
Conectar de forma nativa el nodo del modelo de lenguaje de alta fidelidad estructural (Chat Model).
Acceder al menú de configuración avanzada del nodo de IA y ajustar la palanca visual de iteraciones máximas para fijar un límite estricto de entre 5 y 10 vueltas.
En el cuadro de texto de System Message, redactar de forma modular las instrucciones fijas del agente: definir el rol corporativo, los objetivos comerciales de la sesión y las restricciones explícitas de acción. Validar la exclusión total de giros de lenguaje inclusivo.
Arrastrar un conector nativo de Workspace o productividad y acoplarlo lateralmente en la sección de extensiones (Tools) del agente.
Redactar una descripción semántica de negocio extensa dentro de la herramienta acoplada, detallando los casos exactos en los que el modelo debe decidir activarla de manera autónoma para mitigar la "instrucción huérfana".
Comprobar que el nodo no esté enlazado de forma secuencial posterior a bloques rígidos de decisión lineal en el lienzo general.
Conectar un nodo final de notificación (Slack o Gmail) que capture el resultado del Execution Log para generar un reporte automático de observabilidad humana.
Realizar una prueba de funcionamiento manual haciendo clic en Execute Workflow, auditar el recorrido visual en verde e interpretar el panel de ejecución antes de exportar.
​

Formato de Entrega: Archivo de configuración visual exportado de la plataforma en formato de texto estructurado limpio con el nombre obligatorio checkpoint1_nombre_apellido.json.

En un Repositorio (GitHub), subí el  .json  exportado de n8n y compartí el link.
Entregable

Pre-entregable: Construcción del Agente Base y Motor de Razonamiento
Para completar con éxito este primer checkpoint obligatorio de tu trayecto, debes diseñar y exportar un flujo en n8n que actúe como el motor de razonamiento inicial de tu proyecto integrador. El entregable formal de esta instancia es el archivo JSON del flujo, el cual debe cumplir estrictamente con las siguientes especificaciones operativas desde la interfaz visual:

🧩 Esto es un proyecto que crece, no un ejercicio suelto. El agente que armás acá es la primera versión de tu proyecto integrador, el mismo que vas a ir ampliando módulo a módulo: le sumás memoria y contexto (M3), herramientas e integraciones reales (M4), RAG / base documental (M5), voz (M6) y así hasta el Proyecto Final Integrador (M11). No arranques de cero en cada módulo: partí siempre del flujo del módulo anterior y hacelo evolucionar. Guardá bien tu .json — lo vas a reutilizar todo el curso.

🗺️ Cómo crece tu workflow (hito por hito)
Vas a construir un solo proyecto que evoluciona. En cada módulo importás tu .json del hito anterior y sumás SOLO los nodos nuevos:



M1 · Agente base      [Trigger] → [AI Agent + System Prompt + 1 Tool] → [Log/Observabilidad]
M2 · + Multi-agente        └─ [Manager] → [Workers como sub-workflows]
M3 · + Memoria             └─ [Airtable: leer/escribir contexto por Session_ID]
M4 · + Integraciones       └─ [CRM / Calendario / Workspace vía OAuth2]
M5 · + RAG                 └─ [Base documental / Vector store — LlamaCloud]
M6 · + Voz                 └─ [STT / TTS]
→ ... y así hasta el Proyecto Final Integrador (M11)
Regla de oro: no rehagas el flujo desde cero en ningún checkpoint. Abrí tu .json anterior, importalo y extendelo con los nodos del módulo.

1. Componentes Obligatorios del Flujo
Disparador (Trigger): Utiliza un nodo Chat Trigger o Webhook para capturar la instrucción, el estímulo o el mensaje inicial desestructurado del usuario.
AI Agent Node (El Cerebro): * Debe estar configurado obligatoriamente en modo Tools Agent.
Debe estar conectado a un modelo de lenguaje estratégico mediante su nodo nativo específico (OpenAI Chat Model o Anthropic Chat Model, utilizando preferentemente GPT-4o o Claude 3.5 Sonnet).
Guardrail de Seguridad: En la configuración avanzada del nodo, debes limitar visualmente el número de iteraciones máximas (establecer un límite estricto de entre 5 y 10 vueltas) para blindar el sistema contra bucles lógicos infinitos en producción.
System Prompt (La Constitución del Agente): Configurado dentro del nodo central, debe definir con claridad un rol operativo específico (por ejemplo: "Asistente de Calificación de Leads", "Coordinador de Agenda" o "Triaje de Soporte"). Debe estructurarse de forma modular (Rol $\rightarrow$ Ámbito $\rightarrow$ Objetivo $\rightarrow$ Reglas y Escalamiento) y establecer los límites estrictos de su alcance (qué acciones NO tiene permitido hacer).
Herramienta (Tool): * Integra al menos una herramienta nativa activa y funcional conectada directamente de forma lateral como una extensión al nodo del agente (como Google Sheets, Gmail o Slack), y nunca como un nodo de acción regular secuencial del lienzo general.
¡Requisito Clave! La herramienta debe tener una descripción (Description) semántica y contextual extensa que le explique al modelo de IA exactamente en qué casos de negocio debe decidir activarla de manera autónoma.
Observabilidad (Log de Control): El flujo debe incluir un sistema de notificaciones (conectando un nodo final de Slack o Gmail) que capture la auditoría del pensamiento de la IA (Execution Log) o el resultado de la herramienta ejecutada, actuando como un reporte automático de supervisión humana.
2. Formato y Requisitos de Entrega
Nombre del archivo obligatorio: checkpoint1_nombre_apellido.json
Validación previa (Testing): Antes de descargar el archivo, realiza una prueba de ejecución manual haciendo clic en Test step o Execute Workflow y envíale un prompt de prueba al agente dentro de n8n. Abre el panel de ejecución, audita el flujo en verde y verifica visualmente que el agente abra de forma probabilística la ramificación de la herramienta, la ejecute con éxito y envíe el log de observabilidad sin errores de sintaxis en las expresiones.
Exportación: En un Repositorio (GitHub), subí el .json exportado de n8n y compartí el link.
