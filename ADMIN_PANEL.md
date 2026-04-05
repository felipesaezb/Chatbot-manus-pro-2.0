# Panel Administrativo - Bandeja de Entrada

## Descripción

Panel administrativo tipo "bandeja de entrada" para monitorear todas las conversaciones del chatbot con historial completo.

## Características Implementadas

### Base de Datos
- **Tabla `conversations`**: Almacena información de cada sesión de chat
  - `sessionId`: ID único de la sesión
  - `firstMessage`: Primer mensaje del usuario (para identificar la conversación)
  - `lastMessage`: Último mensaje de la conversación
  - `lastMessageAt`: Timestamp del último mensaje
  - `messageCount`: Contador de mensajes

- **Tabla `messages`**: Almacena todos los mensajes individuales
  - `conversationId`: Referencia a la conversación
  - `role`: "user" o "assistant"
  - `content`: Contenido del mensaje
  - `messageType`: "text" o "voice"
  - `timestamp`: Fecha y hora del mensaje

### API Endpoints

**`/api/admin/saveConversation`**
- Guarda automáticamente cada mensaje en la base de datos
- Crea o actualiza la conversación según el sessionId

**`/api/admin/getConversations`**
- Obtiene todas las conversaciones ordenadas por último mensaje
- Actualización automática cada 5 segundos

**`/api/admin/getConversationMessages`**
- Obtiene todos los mensajes de una conversación específica
- Actualización automática cada 3 segundos

### Interfaz de Usuario

**Ubicación**: Tab "Admin" en la barra de navegación inferior

**Layout de dos columnas**:
1. **Izquierda**: Lista de conversaciones
   - Número de conversación
   - Preview del primer/último mensaje
   - Fecha y hora del último mensaje
   - Contador de mensajes
   - Actualización en tiempo real (cada 5s)

2. **Derecha**: Vista detallada de mensajes
   - Burbujas de chat estilo WhatsApp
   - Mensajes del usuario (azul, derecha)
   - Mensajes del bot (gris, izquierda)
   - Indicador de mensajes de voz (🎤)
   - Timestamps de cada mensaje
   - Actualización en tiempo real (cada 3s)

### Integración Automática

El chatbot guarda automáticamente cada mensaje en la base de datos:
- Genera un `sessionId` único al iniciar cada sesión
- Guarda mensajes del usuario y del bot
- Detecta si es mensaje de texto o voz
- Marca el primer mensaje para identificar la conversación

## Cómo Usar

1. **Acceder al panel**: Hacer clic en el tab "Admin" en la barra inferior
2. **Ver conversaciones**: La lista se actualiza automáticamente con nuevas conversaciones
3. **Ver detalles**: Hacer clic en una conversación para ver todos los mensajes
4. **Monitoreo en tiempo real**: El panel se actualiza automáticamente sin necesidad de recargar

## Notas Técnicas

- **Persistencia**: Todos los mensajes se guardan en MySQL
- **Tiempo real**: Polling automático (no requiere WebSockets)
- **Escalabilidad**: Diseñado para manejar múltiples conversaciones simultáneas
- **Sin autenticación**: Actualmente usa `publicProcedure` (agregar auth si es necesario)

## Próximas Mejoras Sugeridas

- [ ] Agregar búsqueda/filtrado de conversaciones
- [ ] Implementar paginación para muchas conversaciones
- [ ] Agregar autenticación para proteger el panel admin
- [ ] Exportar conversaciones a CSV/PDF
- [ ] Agregar estadísticas (mensajes por día, conversaciones activas, etc.)
- [ ] Notificaciones cuando llega una nueva conversación
- [ ] Marcar conversaciones como "resueltas" o "pendientes"
