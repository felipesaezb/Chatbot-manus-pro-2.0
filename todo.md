# TODO - Chatbot con Voz

## Interfaz de Chat
- [x] Crear componente MessageBubble para mostrar mensajes
- [x] Crear componente ChatInput para entrada de texto
- [x] Implementar lista de mensajes con scroll automático
- [x] Agregar indicador de "escribiendo..." cuando el bot está procesando
- [ ] Mostrar timestamps en los mensajes

## Funcionalidades de Voz
- [x] Implementar botón de micrófono con animación
- [x] Integrar grabación de audio con expo-audio
- [x] Enviar audio al backend para transcripción
- [x] Mostrar texto transcrito en el chat
- [x] Implementar reproducción de respuestas de voz
- [x] Agregar indicador visual de reproducción de audio
- [x] Configurar permisos de micrófono

## Integración con IA
- [x] Crear endpoint en el backend para procesar mensajes
- [x] Integrar OpenAI GPT-4 para respuestas inteligentes
- [x] Configurar prompt del sistema en español
- [x] Mantener contexto de conversación
- [x] Integrar OpenAI Whisper para speech-to-text
- [x] Integrar OpenAI TTS para text-to-speech

## Almacenamiento Local
- [x] Guardar historial de chat en AsyncStorage
- [x] Cargar historial al iniciar la app
- [x] Implementar función para limpiar historial

## Pantalla de Configuración
- [ ] Crear pantalla de configuración
- [ ] Agregar toggle para respuestas de voz automáticas
- [ ] Agregar selector de velocidad de voz
- [ ] Implementar función para limpiar historial desde configuración
- [ ] Guardar preferencias en AsyncStorage

## Navegación
- [ ] Configurar tab navigation con Home y Settings
- [ ] Agregar íconos para las tabs

## Branding
- [x] Generar logo personalizado para el chatbot
- [x] Actualizar app.config.ts con nombre y logo
- [x] Copiar logo a todas las ubicaciones requeridas

## Testing y Pulido
- [ ] Probar flujo completo de mensaje de texto
- [ ] Probar flujo completo de mensaje de voz
- [ ] Verificar funcionamiento en modo oscuro
- [ ] Agregar feedback háptico en interacciones clave
- [ ] Optimizar animaciones y transiciones

## Bugs Reportados
- [x] Corregir problema: botón de grabación de audio no funciona (no graba nada al presionarlo)
- [x] Agregar logs de depuración para diagnosticar problemas en el flujo de audio
- [x] Mejorar mensajes de error para que el usuario sepa qué está fallando

## Nueva Funcionalidad - Asistente de Hotel
- [x] Crear archivo de configuración con información de Happy BnB
- [x] Modificar prompt del sistema para limitar respuestas a información del hotel
- [x] Actualizar nombre de la app a "Happy BnB Assistant"
- [ ] Actualizar logo para reflejar el hotel (opcional)

## Soporte Multiidioma
- [x] Modificar prompt del sistema para detectar y responder en el idioma del cliente
- [x] Permitir cambio de idioma cuando el cliente lo solicite
- [x] Corregir cambio inconsistente de idioma (cambia aleatoriamente sin razón)
- [x] Corregir problema: botón muestra "grabando" pero no captura audio real

## Mejoras de UX
- [x] Agregar visualización de onda de audio durante la grabación
- [x] Corregir problema: audios cortos a veces no se procesan correctamente
- [x] Cambiar colores del tema a azul (#1869ea primario, #001a3c oscuro)
- [x] Corregir problema persistente: algunos audios requieren grabarse dos veces
- [x] Reescribir hook de grabación para solucionar problema de doble intento definitivamente
- [x] Ajustar tono del asistente para que sea más descontraído y natural (conversacional)
- [x] Agregar manejo de groserías y comentarios inapropiados con profesionalismo
- [x] Refinar tono para ser coloquial pero sin modismos groseros o muy informales
- [x] Corregir: el asistente sigue usando "weón" a pesar de las instrucciones de evitarlo
- [x] Crear lista completa de modismos groseros prohibidos de múltiples países (Chile, Brasil, Argentina, Uruguay, Bolivia, Perú, USA, Europa)
- [x] Cambiar título de la app para que muestre "Happy BnB"
- [x] Agregar nombre del hotel al inicio del prompt

## Cambio de identidad: Happy BnB → Nomahost
- [x] Actualizar prompt del sistema con enfoque de consultora Nomahost
- [x] Cambiar nombre de la app a "Nomahost"
- [x] Actualizar mensaje de bienvenida
- [x] Cambiar toda referencia de Happy BnB a Nomahost
- [x] Actualizar app.config.ts con nuevo nombre
- [x] Corregir error: chatbot no responde o muestra "Lo siento, hubo un error al procesar tu mensaje"

## Mejoras de UX solicitadas
- [x] Hacer respuestas más cortas y conversacionales (no soltar toda la info de una vez)
- [x] Cambiar botón de audio a modo press-and-hold (mantener presionado para grabar, soltar para enviar automáticamente)

## Ajuste de tono más casual y humano
- [x] Modificar prompt para que el bot se presente como "Felipe"
- [x] Cambiar saludo inicial a estilo más conversacional: "Hola, ¿qué tal? Felipe por acá. ¿En qué te puedo ayudar?"
- [x] Actualizar mensaje de bienvenida en la interfaz

## Sonido de notificación
- [x] Buscar y descargar sonido de notificación sutil (campanita/tic)
- [x] Agregar sonido al proyecto en assets/sounds/
- [x] Reproducir sonido cuando llega respuesta del bot

## Correcciones de UI/UX
- [x] Arreglar problema en Android: botón de enviar se tapa con el botón de audio
- [x] Modernizar tipografía (más actual y limpia)
- [x] Hacer burbujas de mensajes más redondeadas y modernas (estilo bubble)
- [x] Mejorar espaciado y diseño general

## Comportamiento de botones estilo WhatsApp
- [x] Hacer que el botón de micrófono y enviar se alternen (no aparezcan ambos a la vez)
- [x] Sin texto: solo micrófono visible
- [x] Con texto: solo botón de enviar visible (micrófono oculto)

## Posición del botón de enviar
- [x] Mover botón de enviar al lado derecho del input (no abajo)
- [x] Mantener el comportamiento de alternancia con el micrófono

## Indicadores de lectura estilo WhatsApp
- [x] Agregar double check (✓✓) verde en mensajes del usuario
- [x] Mostrar checks al lado de la hora del mensaje

## Delay en checks de lectura
- [x] Agregar delay de 1-2 segundos antes de mostrar checks verdes
- [x] Implementar transición: sin checks → checks grises → checks verdes

## Bug: Input no se limpia después de enviar
- [x] Arreglar que el texto permanece en el input después de enviar mensaje en móvil
- [x] Asegurar que el input se limpia correctamente en todas las plataformas

## Cambiar sonido de notificación
- [x] Buscar sonido más "bubble" (burbujeante y suave)
- [x] Reemplazar el sonido actual de notificación

## Bug: Sonido no se reproduce en móvil
- [x] Arreglar autoplay de sonido de notificación en iOS/Android
- [x] Implementar solución para restricciones de autoplay en navegadores móviles

## Agregar recomendación de AskSuite
- [x] Actualizar prompt para que Felipe recomiende AskSuite cuando hablen de chatbots para hoteles
- [x] Incluir link de WhatsApp del consultor: wa.me/+5521991861536

## Correcciones en recomendación de asksuite
- [x] Cambiar "AskSuite" a "asksuite" (minúscula)
- [x] Hacer que el link sea clickeable sin mostrar el número literal

## Botón de Nueva Conversación
- [x] Agregar botón "Nueva conversación" en la interfaz
- [x] Implementar funcionalidad para limpiar el historial del chat
- [x] Agregar confirmación antes de limpiar (opcional)

## Conversación nueva en cada sesión
- [x] Eliminar botón de "Nueva conversación" (no solicitado)
- [x] Deshabilitar persistencia del historial en AsyncStorage
- [x] Cada vez que se cierra y abre la app, debe iniciar conversación nueva

## Botón "Hablar con consultor" para asksuite
- [x] Actualizar prompt para que no muestre el link literal
- [x] Implementar componente de botón clickeable en mensajes del bot
- [x] El botón debe decir "Hablar con consultor" y abrir WhatsApp

## Mejoras visuales para AskSuite y botón
- [x] Cambiar "asksuite" a "**AskSuite**" (negrita, A mayúscula) en el prompt
- [x] Rediseñar botón con color naranja #FF5722
- [x] Hacer el botón más atractivo visualmente

## Correcciones de estilo
- [x] Cambiar "**AskSuite**" a "**Asksuite**" (solo A mayúscula)
- [x] Rediseñar botón de forma más minimalista y limpia
- [x] Quitar flecha emoji del botón

## Renderizado de Markdown en mensajes
- [x] Implementar interpretación de formato Markdown en MessageBubble
- [x] **Asksuite** debe aparecer en negrita real, no con asteriscos visibles

## Mejoras de UX en mensajes e input
- [x] Arreglar renderizado de texto para que fluya mejor (sin saltos de línea innecesarios)
- [x] Mantener el foco en el input después de enviar un mensaje

## Actualizar descripción de Asksuite
- [x] Mencionar que Asksuite es la mejor IA del mercado de hoteles con más de una década de experiencia

## Panel Administrativo - Bandeja de Entrada
- [x] Diseñar esquema de base de datos para almacenar conversaciones
- [x] Crear endpoints API para guardar y recuperar conversaciones
- [x] Implementar almacenamiento automático de mensajes desde el chatbot
- [x] Crear nueva ruta /admin para el panel administrativo
- [x] Diseñar interfaz tipo bandeja de entrada con lista de conversaciones
- [x] Implementar vista detallada de cada conversación con historial completo
- [x] Agregar timestamps y metadata de cada conversación
- [ ] Implementar búsqueda/filtrado de conversaciones (mejora futura)
- [x] Diseño responsive para el panel admin
- [x] Probar flujo completo: chatbot → almacenamiento → visualización en admin

## BUG CRÍTICO - Grabación de Audio
- [ ] Diagnosticar por qué no funciona la grabación de audio
- [ ] Arreglar el sistema de grabación de voz
- [ ] Verificar permisos de micrófono
- [ ] Probar flujo completo de grabación y envío de audio

## Ocultar Panel Admin de Usuarios
- [x] Remover tab Admin de la navegación visible para usuarios
- [x] Panel admin accesible solo via URL directa (no aparece en tabs)
- [x] El chatbot muestra solo la interfaz de chat sin acceso al panel

## Acceso al Panel Admin con Clave
- [x] Implementar detección de clave "Nomita1130" en el chat
- [x] Redirigir al panel admin cuando se ingrese la clave
- [x] No mostrar la clave como mensaje en el historial

## Página Web Separada para Panel Admin
- [x] Crear ruta /admin-web independiente del chat
- [x] Copiar funcionalidad del panel admin a la nueva ruta
- [x] Generar URL directa accesible desde navegador
- [ ] Remover acceso por clave desde el chat (mantener ambas opciones)

## Integración del Chatbot en Websites Externos
- [x] Crear código HTML para widget flotante (botón en esquina)
- [x] Crear código HTML para iframe embebido (chat visible)
- [x] Crear documento con instrucciones de integración
- [x] Incluir ejemplos para WordPress, HTML puro, Shopify, Wix, Webflow

## Panel Admin Moderno con Kanban

- [x] Rediseñar panel admin con diseño moderno y estético
- [x] Implementar sistema kanban/embudo para organizar conversaciones por etapas
- [x] Agregar drag & drop para mover conversaciones entre columnas (botones)
- [x] Mejorar visualización de mensajes y metadata
- [x] Agregar estadísticas y métricas visuales
- [x] Pulir detalles visuales y animaciones

## Embudo de Ventas Real con Drag & Drop

- [x] Rediseñar etapas del embudo según proceso comercial (Lead, Calificado, Demo Agendada, Demo Realizada, Propuesta, Negociación, Cliente, Descartado)
- [x] Implementar drag & drop real para arrastrar tarjetas entre columnas (long press + tap column)
- [x] Actualizar esquema de base de datos con nuevas etapas
- [x] Actualizar endpoints API para las nuevas etapas
- [x] Mejorar visualización de tarjetas durante el arrastre
- [x] Diseño ultra profesional estilo SaaS moderno (sin emojis, colores sutiles, tipografía elegante)

## Panel Admin - Rediseño Final con Especificaciones Correctas

- [x] Actualizar esquema de base de datos con las 5 etapas correctas (Conversa Iniciada, Oportunidad, Meeting Held, Contrato, Inicio Proyecto)
- [x] Rediseñar panel admin con color principal #001a3c (azul oscuro)
- [x] Cambiar tipografía a Poppins en todo el panel
- [x] Implementar kanban con drag & drop real para las 5 etapas
- [x] Mostrar SOLO conversaciones reales de la base de datos (sin datos fake)
- [x] Ordenar conversaciones cronológicamente (más reciente primero)
- [x] Diseño profesional basado en referencia Pipedrive del usuario

## Panel Admin - Rediseño Profesional Estilo Pipedrive Real

- [x] Crear sidebar de navegación con logo y menú
- [x] Crear header con barra de búsqueda y botones de acción
- [x] Rediseñar tarjetas compactas estilo Pipedrive (más densas, con valores, avatares, badges)
- [x] Implementar drag & drop (long press + tap en columna)
- [x] Agregar badges de prioridad (círculos amarillos)
- [x] Mostrar valores monetarios en las tarjetas
- [x] Diseño más compacto y denso (más información en menos espacio)
- [x] Colores sutiles y profesionales
- [x] Tipografía Poppins en todo el panel

## Correcciones Urgentes del Panel Admin

- [ ] Cargar fuente Poppins correctamente desde Google Fonts (la tipografía actual se ve antigua)
- [ ] Implementar drag & drop REAL con mouse (mantener clickeado y arrastrar, no long press + tap)
- [ ] Verificar que la fuente Poppins se aplica correctamente en todo el panel
- [ ] Probar el drag & drop con el mouse en el navegador

## Actualización de Etapas del Embudo

- [x] Actualizar esquema de base de datos con las 8 nuevas etapas (Nuevo lead, Interesado, Lead calificado, Demo agendada, Propuesta enviada, Negociación, Venta cerrada, Perdido / No califica)
- [x] Actualizar server/routers.ts con las nuevas etapas
- [x] Actualizar server/db.ts con las nuevas etapas
- [x] Actualizar panel admin (app/admin-web/index.tsx) con las 8 columnas
- [x] Verificar que el drag & drop funciona con las nuevas etapas

## Reducción de Etapas del Pipeline a 6 Columnas

- [x] Eliminar etapas: Interesado, Lead calificado, Perdido / No califica
- [x] Mantener solo 6 etapas: Nuevo lead, Oportunidad, Demo agendada, Propuesta enviada, Negociación, Venta cerrada
- [x] Actualizar esquema de base de datos con las 6 etapas finales
- [x] Actualizar server/routers.ts y server/db.ts
- [x] Actualizar panel admin con 6 columnas balanceadas
- [x] Hacer el diseño más compacto y simétrico para escritorio

## Nuevas Funcionalidades del Panel Admin

- [x] Agregar campo dealValue (decimal) a la tabla conversations usando ALTER TABLE
- [x] Agregar campo notes (text) a la tabla conversations usando ALTER TABLE
- [x] Crear endpoint para actualizar dealValue de una conversación
- [x] Crear endpoint para actualizar notes de una conversación
- [x] Implementar UI para editar valores monetarios en las tarjetas del kanban (click en el valor para editar)
- [x] Agregar filtros por fecha en el header (Última semana, Último mes, Último trimestre, Todo)
- [x] Agregar campo de notas internas en el modal de conversación detallada (click para editar)
- [x] Mostrar el valor total del pipeline en el header (suma de todos los dealValues)

## Comportamiento Comercial del Chatbot

- [x] Actualizar prompt del chatbot para redirigir solicitudes fuera de alcance (botones, integraciones técnicas, etc.)
- [x] Agregar instrucción para preguntar explícitamente por demo después de explicar valor
- [x] Implementar detección automática de aceptación de demo (palabras clave: sí, me interesa, ok, dale, agendemos, etc.)
- [x] Mover automáticamente la conversación a etapa "Oportunidad" cuando el cliente acepta la demo
- [x] Agregar reglas de venta consultiva (no improvisar funcionalidades, no prometer acciones técnicas)

## Interfaz de Grabación de Audio Estilo WhatsApp

- [x] Crear UI de grabación con contador de tiempo en vivo (0:01, 0:02, etc.)
- [x] Agregar waveform animado durante la grabación
- [x] Implementar botón de eliminar (🗑️) a la izquierda
- [x] Implementar botón de pausar/reanudar (⏸️/▶️) en el centro
- [x] Implementar botón de enviar (▶️ verde) a la derecha
- [x] Diseño estilo WhatsApp (fondo beige, botón verde grande)
- [x] Cambiar a tap-to-record en lugar de long press

## Ajustes de Interfaz de Grabación y Transcripción

- [x] Cambiar colores de la interfaz de grabación a sobrios (#1869ea azul, grises elegantes)
- [x] Cambiar fondo del recorder de beige a gris oscuro elegante (#1F2937)
- [x] Cambiar botón de enviar de verde a azul #1869ea
- [x] Cambiar waveform de celeste a azul #1869ea
- [x] Agregar campo de transcripción y audioUrl en la tabla de mensajes del admin
- [x] Mostrar transcripción de audios en el panel admin con formato especial

## Corrección de Transcripción en Panel Admin

- [x] Mostrar transcripción SOLO en mensajes de voz del USUARIO (role === "user")
- [x] Los mensajes del bot (assistant) siempre deben mostrar el texto normal, nunca "audio transcrito"

## Sistema de Control Manual del Bot

- [x] Agregar campo `botPaused` (boolean) a la tabla conversations
- [x] Crear endpoint para pausar el bot en una conversación
- [x] Crear endpoint para reanudar el bot en una conversación
- [x] Crear endpoint para enviar mensajes manuales desde el admin
- [x] Agregar botones "⏸️ Pausar Bot" / "▶️ Reanudar Bot" en el panel admin
- [x] Agregar indicador visual del estado del bot (🔴 Bot pausado / 🟢 Bot activo)
- [x] Agregar campo de texto en el modal para responder manualmente
- [x] Implementar lógica en el chat para verificar si el bot está pausado antes de responder

## Corrección de Error de React Hooks

- [x] Mover las mutaciones toggleBotPaused y sendManualMessage al inicio del componente AdminScreen
- [x] Usar las mutaciones declaradas en lugar de llamar useMutation() dentro de onPress

## Corrección de Sistema de Control Manual del Bot

- [x] Arreglar verificación de bot pausado (el bot sigue respondiendo aunque esté pausado)
- [x] Arreglar envío de mensajes manuales al cliente (los mensajes no llegan a la app móvil)
- [x] Probar que el bot realmente se pause cuando se activa el botón
- [x] Probar que los mensajes manuales lleguen al cliente en tiempo real

## Implementación de WebSockets para Mensajes en Tiempo Real

- [x] Configurar servidor WebSocket en el backend (Socket.IO)
- [x] Crear cliente WebSocket en la app móvil
- [x] Emitir evento cuando admin envía mensaje manual
- [x] Recibir y mostrar mensajes en tiempo real en el cliente
- [x] Implementar reconexión automática si se pierde la conexión

## Sistema de Inactividad y Cierre Automático

- [x] Implementar timer de inactividad (3 minutos sin respuesta)
- [x] Enviar mensaje "¿Sigues ahí todavía?" después de 3 minutos
- [x] Implementar timer de cierre (1 minuto adicional sin respuesta)
- [x] Enviar mensaje de cierre y marcar conversación como finalizada
- [x] Permitir reanudar conversación si el usuario responde

## Captura de Datos del Usuario

- [x] Agregar campos a la base de datos (nombre, email, teléfono, DDI)
- [x] Implementar mini-formulario en el chat (uno por uno)
- [x] Crear selector de país para DDI (Chile, Brasil, México, Colombia, Perú, Bolivia, Argentina)
- [x] Actualizar prompt del bot para solicitar datos en momento natural
- [x] Guardar datos capturados en la base de datos

## Sistema de Tagging

- [x] Agregar campos de tagging a la base de datos (motivo, resultado)
- [x] Implementar detección automática de motivo principal (9 opciones)
- [x] Implementar detección automática de resultado final (4 opciones)
- [x] Mostrar tags en el panel admin
- [ ] Permitir filtrado por tags en el panel admin

## Cierre Amable

- [x] Actualizar prompt para cierre amable y profesional
- [x] Implementar mensaje de despedida personalizado


## Implementacion de WebSockets para Mensajes en Tiempo Real (COMPLETADO)

- [x] Configurar servidor WebSocket en el backend (Socket.IO)
- [x] Crear cliente WebSocket en la app movil
- [x] Emitir evento cuando admin envia mensaje manual
- [x] Recibir y mostrar mensajes en tiempo real en el cliente
- [x] Implementar reconexion automatica si se pierde la conexion

## Sistema de Inactividad y Cierre Automatico (COMPLETADO)

- [x] Implementar timer de inactividad (3 minutos sin respuesta)
- [x] Enviar mensaje "Sigues ahi todavia?" despues de 3 minutos
- [x] Implementar timer de cierre (1 minuto adicional sin respuesta)
- [x] Enviar mensaje de cierre y marcar conversacion como finalizada
- [x] Permitir reanudar conversacion si el usuario responde

## Captura de Datos del Usuario con Formulario Visual (COMPLETADO)

- [x] Agregar campos a la base de datos (nombre, email, telefono, DDI)
- [x] Implementar formulario visual en el chat (campos de input reales)
- [x] Crear selector de pais para DDI (Chile, Brasil, Mexico, Colombia, Peru, Bolivia, Argentina)
- [x] Actualizar prompt del bot para solicitar datos en momento natural
- [x] Mostrar formulario cuando bot incluya [FORM:data_capture]
- [x] Guardar datos capturados en la base de datos

## Sistema de Tagging de Motivo y Resultado (COMPLETADO)

- [x] Agregar campos de tagging a la base de datos (motivo, resultado)
- [x] Implementar deteccion automatica de motivo principal (9 opciones)
- [x] Implementar deteccion automatica de resultado final (4 opciones)
- [x] Mostrar tags en el panel admin
- [ ] Permitir filtrado por tags en el panel admin

## Cierre Amable (COMPLETADO)

- [x] Actualizar prompt para cierre amable y profesional
- [x] Implementar mensaje de despedida personalizado
