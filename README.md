# Trimi: Asistente Virtual n8n (Grupo Empresarial Tres Marías)

[cite_start]Este repositorio contiene la configuración y los flujos de trabajo de **n8n** para **Trimi**, el asistente inteligente encargado de la gestión de información y automatización del Club Empresarial Tres Marías en Morelia, Michoacán[cite: 3].

## 🤖 Sobre el Bot
[cite_start]Trimi es un agente de IA diseñado para actuar como el punto de contacto principal para la gestión de eventos, usuarios y soporte técnico[cite: 3]. [cite_start]Su comportamiento está programado para ser profesional, cercano y eficiente, garantizando que nunca invente información y siempre confirme las acciones realizadas[cite: 6, 9].

### Funcionalidades Principales
* [cite_start]**Gestión de Eventos**: Crea eventos en Firebase solicitando descripción, título y fechas de inicio/fin[cite: 6, 7].
* [cite_start]**Consultas a Base de Datos**: Acceso mediante MCP a colecciones de Firestore como `eventos`, `organizaciones`, `usuarios` y `retos`[cite: 6].
* [cite_start]**Networking y Filtrado**: Capacidad para listar usuarios según sector, categoría o profesión, ignorando mayúsculas o acentos[cite: 7].
* [cite_start]**Soporte Humano**: Proceso automatizado que solicita nombre y correo para enviar alertas a Telegram y correos de seguimiento vía Gmail[cite: 7, 8, 9].

---

## 🛠️ Estructura de Archivos
El proyecto se compone de tres piezas clave para su despliegue en n8n:

1.  **`Trimi2.json`**: Flujo principal que contiene el Agente de IA, la memoria de sesión y la conexión con OpenRouter.
2.  **`MCP_Trimi2.json`**: Servidor de herramientas (Model Context Protocol) que expone las funciones de Firestore, Gmail y Telegram como herramientas consumibles por el agente.
3.  [cite_start]**`Trimi2_MCP.txt`**: Documentación de respaldo del código JavaScript utilizado para el formateo de datos y validación antes de la inserción en base de datos[cite: 17, 18, 19, 20].

---

## ⚙️ Configuración Requerida
Para que el bot funcione correctamente, es necesario configurar las siguientes credenciales en n8n:

* [cite_start]**OpenRouter API**: Para el procesamiento de lenguaje natural del agente[cite: 11, 12].
* [cite_start]**Google Firebase Cloud Firestore**: Para la persistencia de datos y consultas de eventos/usuarios[cite: 15, 16].
* **Telegram API**: Para el envío de notificaciones de soporte al equipo humano.
* **Gmail OAuth2**: Para el envío automático de correos de asistencia.

## 🚀 Instalación
1. Importa los archivos `.json` en tu instancia de n8n.
2. [cite_start]Asegúrate de que el nodo **MCP Client** en el flujo principal esté apuntando a la URL del webhook de tu **MCP Server Trigger**[cite: 13, 14].
3. [cite_start]Configura el `projectId` de Firebase en los nodos correspondientes[cite: 15].

---
