# Integración del Chatbot Nomahost en tu Website

Este documento contiene los códigos necesarios para integrar el chatbot de Nomahost en cualquier sitio web.

---

## Opción 1: Widget Flotante (Recomendado)

Un botón flotante en la esquina inferior derecha que abre el chat en una ventana modal.

### Código HTML

Copia y pega este código **antes de la etiqueta `</body>`** de tu sitio web:

```html
<!-- Nomahost Chatbot Widget -->
<div id="nomahost-chatbot-widget">
  <!-- Botón flotante -->
  <button id="nomahost-chat-button" style="
    position: fixed;
    bottom: 20px;
    right: 20px;
    width: 60px;
    height: 60px;
    border-radius: 50%;
    background: linear-gradient(135deg, #0a7ea4 0%, #0891b2 100%);
    border: none;
    box-shadow: 0 4px 12px rgba(0, 0, 0, 0.15);
    cursor: pointer;
    z-index: 9998;
    display: flex;
    align-items: center;
    justify-content: center;
    transition: transform 0.2s, box-shadow 0.2s;
  " onmouseover="this.style.transform='scale(1.1)'" onmouseout="this.style.transform='scale(1)'">
    <svg width="28" height="28" viewBox="0 0 24 24" fill="none" stroke="white" stroke-width="2">
      <path d="M21 15a2 2 0 0 1-2 2H7l-4 4V5a2 2 0 0 1 2-2h14a2 2 0 0 1 2 2z"></path>
    </svg>
  </button>

  <!-- Ventana del chat (oculta por defecto) -->
  <div id="nomahost-chat-window" style="
    position: fixed;
    bottom: 90px;
    right: 20px;
    width: 380px;
    height: 600px;
    max-width: calc(100vw - 40px);
    max-height: calc(100vh - 120px);
    border-radius: 16px;
    box-shadow: 0 8px 32px rgba(0, 0, 0, 0.2);
    overflow: hidden;
    z-index: 9999;
    display: none;
    background: white;
  ">
    <!-- Header del chat -->
    <div style="
      background: linear-gradient(135deg, #0a7ea4 0%, #0891b2 100%);
      padding: 16px;
      display: flex;
      justify-content: space-between;
      align-items: center;
    ">
      <div style="display: flex; align-items: center; gap: 12px;">
        <div style="
          width: 40px;
          height: 40px;
          border-radius: 50%;
          background: white;
          display: flex;
          align-items: center;
          justify-content: center;
          font-size: 20px;
        ">👋</div>
        <div>
          <div style="color: white; font-weight: 600; font-size: 16px;">Felipe</div>
          <div style="color: rgba(255,255,255,0.8); font-size: 12px;">Asistente de Nomahost</div>
        </div>
      </div>
      <button id="nomahost-close-button" style="
        background: transparent;
        border: none;
        color: white;
        cursor: pointer;
        font-size: 24px;
        padding: 0;
        width: 32px;
        height: 32px;
        display: flex;
        align-items: center;
        justify-content: center;
      ">×</button>
    </div>

    <!-- Iframe del chat -->
    <iframe 
      src="https://8081-irggjf4w8uny958wz223n-17c432b4.us2.manus.computer"
      style="
        width: 100%;
        height: calc(100% - 72px);
        border: none;
      "
      allow="microphone"
    ></iframe>
  </div>
</div>

<script>
(function() {
  const button = document.getElementById('nomahost-chat-button');
  const chatWindow = document.getElementById('nomahost-chat-window');
  const closeButton = document.getElementById('nomahost-close-button');

  button.addEventListener('click', function() {
    if (chatWindow.style.display === 'none') {
      chatWindow.style.display = 'block';
      button.style.display = 'none';
    }
  });

  closeButton.addEventListener('click', function() {
    chatWindow.style.display = 'none';
    button.style.display = 'flex';
  });
})();
</script>
<!-- Fin Nomahost Chatbot Widget -->
```

### Características del Widget:
- ✅ Botón flotante con animación hover
- ✅ Ventana modal responsive
- ✅ Header personalizado con avatar y nombre
- ✅ Botón de cerrar (X)
- ✅ Funciona en móvil y desktop
- ✅ No interfiere con el contenido de tu sitio

---

## Opción 2: Iframe Embebido

Chat visible directamente en una sección de tu página.

### Código HTML

Copia y pega este código donde quieras que aparezca el chat:

```html
<!-- Nomahost Chatbot Embebido -->
<div style="width: 100%; max-width: 500px; margin: 0 auto;">
  <div style="
    border-radius: 16px;
    overflow: hidden;
    box-shadow: 0 4px 16px rgba(0, 0, 0, 0.1);
    background: white;
  ">
    <!-- Header opcional -->
    <div style="
      background: linear-gradient(135deg, #0a7ea4 0%, #0891b2 100%);
      padding: 20px;
      text-align: center;
    ">
      <h2 style="color: white; margin: 0; font-size: 24px;">Chatea con Felipe</h2>
      <p style="color: rgba(255,255,255,0.9); margin: 8px 0 0 0; font-size: 14px;">
        Tu asistente virtual de Nomahost
      </p>
    </div>

    <!-- Iframe del chat -->
    <iframe 
      src="https://8081-irggjf4w8uny958wz223n-17c432b4.us2.manus.computer"
      style="
        width: 100%;
        height: 600px;
        border: none;
        display: block;
      "
      allow="microphone"
    ></iframe>
  </div>
</div>
<!-- Fin Nomahost Chatbot Embebido -->
```

### Características del Iframe:
- ✅ Integración directa en la página
- ✅ Header personalizable
- ✅ Responsive (se adapta al ancho del contenedor)
- ✅ Altura ajustable (cambia `height: 600px` al valor que necesites)

---

## Instrucciones por Plataforma

### WordPress

1. Ve a **Apariencia → Editor de temas** (o usa un plugin como "Insert Headers and Footers")
2. Pega el código del **Widget Flotante** en el footer (antes de `</body>`)
3. Guarda los cambios

**Alternativa con plugin:**
- Instala el plugin "Code Snippets" o "Insert Headers and Footers"
- Pega el código en la sección "Footer"

### HTML Puro

1. Abre tu archivo `index.html` (o el archivo donde quieras el chat)
2. Pega el código antes de `</body>` (widget flotante) o donde quieras (iframe embebido)
3. Guarda el archivo

### Shopify

1. Ve a **Tienda online → Temas → Acciones → Editar código**
2. Busca el archivo `theme.liquid`
3. Pega el código del **Widget Flotante** antes de `</body>`
4. Guarda

### Wix

1. Ve a **Configuración → Seguimiento y análisis**
2. Pega el código en "Código personalizado → Body - end"
3. Guarda

### Webflow

1. Ve a **Project Settings → Custom Code**
2. Pega el código en "Footer Code"
3. Publica el sitio

---

## Personalización

### Cambiar colores del widget

Busca estas líneas en el código y modifica los valores:

```css
background: linear-gradient(135deg, #0a7ea4 0%, #0891b2 100%);
```

Cambia `#0a7ea4` y `#0891b2` por los colores de tu marca.

### Cambiar posición del botón flotante

Modifica estos valores:

```css
bottom: 20px;  /* Distancia desde abajo */
right: 20px;   /* Distancia desde la derecha */
```

Para ponerlo a la izquierda:
```css
bottom: 20px;
left: 20px;    /* Cambia 'right' por 'left' */
```

### Cambiar tamaño de la ventana del chat

Modifica estos valores:

```css
width: 380px;   /* Ancho de la ventana */
height: 600px;  /* Alto de la ventana */
```

---

## Notas Importantes

⚠️ **Permisos del micrófono**: El atributo `allow="microphone"` permite que los usuarios graben mensajes de voz.

⚠️ **HTTPS requerido**: La grabación de voz solo funciona en sitios con HTTPS (no HTTP).

⚠️ **URL del chatbot**: La URL actual es temporal. Cuando publiques el chatbot en producción, deberás reemplazar:
```
https://8081-irggjf4w8uny958wz223n-17c432b4.us2.manus.computer
```
por la URL definitiva de tu chatbot.

---

## Soporte

Si tienes problemas con la integración:
1. Verifica que el código esté pegado correctamente
2. Asegúrate de que tu sitio use HTTPS
3. Revisa la consola del navegador (F12) para ver errores
4. Contacta al equipo de desarrollo para ajustes personalizados

---

## Vista Previa

**Widget Flotante:**
- Botón circular azul en la esquina inferior derecha
- Al hacer clic, se abre una ventana modal con el chat
- Botón X para cerrar

**Iframe Embebido:**
- Chat visible directamente en la página
- Header con título y descripción
- Integrado en el flujo de la página
