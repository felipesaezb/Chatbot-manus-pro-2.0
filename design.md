# Diseño de Interfaz - Chatbot con Voz

## Orientación y Uso
- **Orientación**: Móvil vertical (9:16)
- **Uso**: Una mano
- **Plataforma**: iOS/Android/Web

## Pantallas

### 1. Pantalla Principal (Chat)
**Contenido principal**:
- Historial de mensajes del chat (usuario y bot)
- Cada mensaje muestra:
  - Avatar (usuario o bot)
  - Texto del mensaje
  - Timestamp
- Área de entrada de texto en la parte inferior
- Botón de micrófono grande y accesible

**Funcionalidad**:
- Enviar mensajes de texto
- Grabar y enviar mensajes de voz
- Escuchar respuestas del bot en voz
- Scroll automático al último mensaje
- Indicador de "escribiendo..." cuando el bot está procesando

**Layout**:
- Header: Título "VoiceBot" + botón de configuración
- Body: ScrollView con mensajes (flex-1)
- Footer: Input de texto + botón enviar + botón micrófono

### 2. Pantalla de Configuración
**Contenido principal**:
- Toggle para activar/desactivar respuestas de voz automáticas
- Selector de velocidad de voz (lento, normal, rápido)
- Toggle para modo oscuro/claro
- Botón para limpiar historial de chat

**Funcionalidad**:
- Guardar preferencias del usuario
- Aplicar cambios en tiempo real

## Flujos de Usuario

### Flujo 1: Enviar mensaje de texto
1. Usuario escribe en el input de texto
2. Usuario presiona botón "Enviar"
3. Mensaje aparece en el chat
4. Bot procesa y responde
5. Respuesta aparece en el chat
6. (Opcional) Respuesta se reproduce en voz

### Flujo 2: Enviar mensaje de voz
1. Usuario presiona y mantiene botón de micrófono
2. Indicador visual muestra que está grabando
3. Usuario habla
4. Usuario suelta el botón
5. Audio se transcribe a texto
6. Texto transcrito aparece en el chat
7. Bot procesa y responde
8. Respuesta aparece en el chat
9. Respuesta se reproduce en voz

### Flujo 3: Escuchar respuesta
1. Bot envía respuesta de texto
2. Sistema convierte texto a voz
3. Audio se reproduce automáticamente
4. Indicador visual muestra que está reproduciendo
5. Usuario puede pausar/detener la reproducción

## Paleta de Colores

### Tema Claro
- **Primary**: #0a7ea4 (azul vibrante)
- **Background**: #ffffff (blanco)
- **Surface**: #f5f5f5 (gris muy claro)
- **Foreground**: #11181C (negro suave)
- **Muted**: #687076 (gris medio)
- **Border**: #E5E7EB (gris claro)

### Tema Oscuro
- **Primary**: #0a7ea4 (azul vibrante)
- **Background**: #151718 (negro suave)
- **Surface**: #1e2022 (gris oscuro)
- **Foreground**: #ECEDEE (blanco suave)
- **Muted**: #9BA1A6 (gris claro)
- **Border**: #334155 (gris oscuro)

## Componentes Clave

### MessageBubble
- Burbujas de mensaje con bordes redondeados
- Usuario: alineado a la derecha, color primary
- Bot: alineado a la izquierda, color surface
- Incluye timestamp y estado de reproducción de audio

### VoiceButton
- Botón circular grande (64x64)
- Ícono de micrófono
- Animación de pulso cuando está grabando
- Feedback háptico al presionar
- Cambio de color cuando está activo

### ChatInput
- Input de texto con placeholder
- Botón de enviar integrado
- Auto-focus después de enviar
- Manejo de teclado (dismiss on send)

### AudioPlayer
- Indicador visual de reproducción
- Botón de play/pause
- Barra de progreso
- Duración del audio

## Interacciones

### Feedback Táctil
- **Botón de micrófono**: Haptic medium al presionar/soltar
- **Botón de enviar**: Haptic light al enviar
- **Botones de configuración**: Haptic light al cambiar

### Animaciones
- **Mensaje nuevo**: Fade in + slide up (250ms)
- **Grabando**: Pulso del botón de micrófono (loop)
- **Reproduciendo**: Onda de audio animada (loop)
- **Escribiendo**: Tres puntos animados

## Consideraciones Técnicas

### Reconocimiento de Voz
- Usar expo-audio para grabación
- Enviar audio al backend para transcripción con OpenAI Whisper
- Mostrar texto transcrito en tiempo real si es posible

### Síntesis de Voz
- Usar expo-audio para reproducción
- Generar audio con OpenAI TTS en el backend
- Cachear audios para respuestas frecuentes

### IA
- Usar OpenAI GPT-4 para respuestas inteligentes
- Mantener contexto de conversación (últimos 10 mensajes)
- Configurar idioma español en el prompt del sistema

### Almacenamiento
- Guardar historial de chat en AsyncStorage
- Guardar preferencias de usuario en AsyncStorage
- No requiere backend para almacenamiento (solo para IA y voz)
