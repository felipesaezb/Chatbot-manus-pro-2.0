# 🚀 Guía de Plantilla Reutilizable - Chatbot Inteligente

Esta es una **plantilla profesional y reutilizable** para crear chatbots inteligentes para cualquier empresa en minutos.

---

## 📋 Estructura de la Plantilla

```
config/
├── company.ts          ← Información de la empresa (nombre, colores, contacto)
├── personality.ts      ← Personalidad del bot (tono, reglas, respuestas)
├── knowledge.ts        ← Base de conocimiento (servicios, FAQ, políticas)
├── prompts.ts          ← Generador de prompts dinámicos
└── index.ts            ← Exporta todo centralizado

app/(tabs)/
├── index.tsx           ← Chat (reutilizable, usa config)
└── admin.tsx           ← Panel de administración

components/
├── screen-container.tsx
└── whatsapp-voice-recorder.tsx
```

---

## 🎯 Cómo Crear un Nuevo Chatbot para un Cliente

### **Paso 1: Clonar/Copiar el Proyecto**

```bash
cp -r voice-chatbot hotel-chatbot
cd hotel-chatbot
```

### **Paso 2: Editar `config/company.ts`**

```typescript
export const company = {
  name: "Hotel Paradise",
  slug: "hotel-paradise",
  colors: {
    primary: "#8B4513",      // Marrón (color del hotel)
    primaryDark: "#5C2E0F",
    secondary: "#4ade80",
    // ... resto de colores
  },
  avatar: {
    url: "https://... (URL del avatar del hotel)",
    alt: "María - Recepcionista Virtual",
  },
  contact: {
    phone: "+56912345678",
    email: "reservas@hotelparadise.cl",
    website: "https://hotelparadise.cl",
    hours: "Disponible 24/7",
  },
  // ... resto de info
};
```

### **Paso 3: Editar `config/personality.ts`**

```typescript
export const personality = {
  name: "María",  // Cambiar nombre del bot
  tone: "Cálido, acogedor y profesional",
  description: "Recepcionista virtual del hotel, siempre lista para ayudarte",
  values: ["Hospitalidad", "Confort", "Servicio excepcional"],
  rules: [
    "Siempre ser cálido y acogedor",
    "Ofrecer soluciones rápidas",
    "Sugerir servicios adicionales del hotel",
    // ... más reglas específicas del hotel
  ],
  responses: {
    greeting: "¡Bienvenido a Hotel Paradise! 🏨 Soy María, tu recepcionista virtual. ¿Cómo puedo ayudarte?",
    // ... otras respuestas
  },
};
```

### **Paso 4: Editar `config/knowledge.ts`**

```typescript
export const knowledge = {
  services: [
    {
      name: "Habitación Estándar",
      description: "Cómoda habitación con vista al jardín",
      price: "$80/noche",
    },
    {
      name: "Suite Presidencial",
      description: "Lujo y comodidad máxima",
      price: "$250/noche",
    },
    // ... más servicios
  ],
  faq: [
    {
      question: "¿Cuál es el horario de check-in?",
      answer: "Check-in a partir de las 15:00 y check-out hasta las 11:00",
    },
    // ... más preguntas
  ],
  // ... resto de información
};
```

### **Paso 5: Generar Avatar con IA**

1. Usa el comando para generar un avatar único:
   ```bash
   # Generar avatar para el hotel
   manus-generate-image "Hotel receptionist avatar, woman, professional, friendly, modern style"
   ```

2. Sube la imagen a S3 y actualiza la URL en `config/company.ts`

### **Paso 6: Actualizar Widget HTML**

Actualiza el archivo `nomahost-chatbot-final.html` con:
- Nuevo avatar URL
- Nuevos colores
- Nuevo nombre del bot

### **Paso 7: Publicar y Listo**

```bash
# El chat automáticamente usará la nueva configuración
npm run dev
```

---

## 💡 Ejemplos de Clientes

### **Hotel**
- **Nombre del bot:** María
- **Tono:** Cálido, acogedor
- **Servicios:** Habitaciones, restaurante, spa, tours
- **Colores:** Marrón, dorado

### **Banco**
- **Nombre del bot:** Carlos
- **Tono:** Profesional, confiable
- **Servicios:** Cuentas, créditos, inversiones
- **Colores:** Azul, plata

### **Tienda de Bebidas**
- **Nombre del bot:** Alex
- **Tono:** Joven, descontracturado
- **Servicios:** Bebidas, promociones, entregas
- **Colores:** Rojo, naranja

### **Clínica Dental**
- **Nombre del bot:** Dra. Sofia
- **Tono:** Profesional, tranquilizador
- **Servicios:** Limpiezas, ortodoncia, implantes
- **Colores:** Blanco, azul claro

---

## ⚙️ Cómo Funciona la Configuración

### **Sistema Dinámico**

El archivo `config/prompts.ts` genera automáticamente el **system prompt** usando la configuración:

```typescript
const systemPrompt = generateSystemPrompt();
// Resultado: Un prompt personalizado que incluye:
// - Nombre del bot
// - Personalidad
// - Servicios
// - FAQ
// - Políticas
// - Reglas de comportamiento
```

### **Uso en el Chat**

En `app/(tabs)/index.tsx`:

```typescript
import { generateSystemPrompt } from "@/config";

// El chat automáticamente usa el prompt generado
const systemPrompt = generateSystemPrompt();

// Enviar a OpenAI
const response = await openai.chat.completions.create({
  system: systemPrompt,
  messages: conversationHistory,
});
```

---

## 🔄 Flujo de Actualización

Si necesitas cambiar algo para un cliente:

1. **Edita el archivo de configuración** correspondiente
2. **El chat se actualiza automáticamente** (no necesitas cambiar código)
3. **El prompt se regenera** con la nueva información

---

## 📊 Tiempo de Implementación

| Tarea | Tiempo |
|-------|--------|
| Copiar proyecto | 1 min |
| Editar configuración | 10 min |
| Generar avatar | 2 min |
| Actualizar widget HTML | 2 min |
| Pruebas | 5 min |
| **TOTAL** | **~20 minutos** |

---

## 🎨 Personalización Avanzada

Si necesitas cambios más profundos:

1. **Agregar nuevas reglas:** Edita `personality.rules`
2. **Cambiar respuestas:** Edita `personality.responses`
3. **Agregar servicios:** Edita `knowledge.services`
4. **Agregar FAQ:** Edita `knowledge.faq`

---

## 🚀 Próximos Pasos

1. **Crear chatbot para Hotel Paradise** (ejemplo)
2. **Crear chatbot para Banco XYZ** (ejemplo)
3. **Crear dashboard de múltiples clientes**
4. **Agregar integración con CRM**
5. **Agregar formulario de captura de leads**

---

## 📞 Soporte

Si tienes dudas sobre cómo personalizar la plantilla, contacta al equipo de desarrollo.

**¡Ahora puedes crear chatbots profesionales en 20 minutos! 🎉**
