# 🔄 Keep-Alive Configuration - Nomahost Chatbot

Este documento explica cómo mantener el servidor **siempre activo** para que nunca se duerma.

---

## ¿Por qué se duerme el servidor?

Manus hibernates servers automáticamente cuando no reciben tráfico por un tiempo. Esto es para ahorrar recursos.

**Solución:** Hacer que algo "pinguee" el servidor cada 5 minutos para mantenerlo activo.

---

## 🚀 Cómo Activar Keep-Alive

### **Opción 1: Ejecutar localmente (Desarrollo)**

```bash
# Terminal 1: Inicia el servidor normalmente
npm run dev

# Terminal 2: En otra ventana, inicia el keep-alive
npm run keep-alive
```

El script pinguea `http://localhost:3000/api/health` cada 5 minutos.

---

### **Opción 2: Usar en Producción (Publicado)**

Cuando publiques el proyecto en Manus:

1. El servidor backend se despliega en una URL permanente (ej: `https://api.nomahost.manus.app`)
2. Configura una tarea cron o servicio externo que pinguee esa URL cada 5 minutos

**Ejemplo con cURL (desde terminal):**
```bash
# Pinguea el servidor cada 5 minutos
while true; do
  curl https://api.nomahost.manus.app/api/health
  sleep 300
done
```

**Ejemplo con UptimeRobot (gratuito):**
1. Ve a https://uptimerobot.com
2. Crea un monitor HTTP GET
3. URL: `https://api.nomahost.manus.app/api/health`
4. Intervalo: 5 minutos
5. ¡Listo! El servidor nunca se dormirá

---

## 📊 Cómo Funciona

El script `scripts/keep-alive.js`:

1. **Pinguea** el endpoint `/api/health` cada 5 minutos
2. **Registra** en consola si el servidor responde
3. **Mantiene activo** el servidor indefinidamente

**Logs de ejemplo:**
```
[Keep-Alive] Starting keep-alive service for http://localhost:3000
[Keep-Alive] Pinging every 300 seconds
[2026-02-03T15:00:00.000Z] ✅ Server is alive (status: 200)
[2026-02-03T15:05:00.000Z] ✅ Server is alive (status: 200)
[2026-02-03T15:10:00.000Z] ✅ Server is alive (status: 200)
```

---

## 🎯 Recomendación

**Para producción, usa UptimeRobot (gratuito):**
- ✅ Funciona 24/7
- ✅ No consume tus créditos
- ✅ Notificaciones si el servidor cae
- ✅ Historial de uptime

**Pasos rápidos:**
1. Crea cuenta en https://uptimerobot.com
2. Agrega monitor HTTP GET
3. URL: `https://api.nomahost.manus.app/api/health`
4. Intervalo: 5 minutos
5. ¡Listo!

---

## 🔗 Endpoint de Health Check

El servidor tiene un endpoint de health check:

```
GET /api/health
```

**Respuesta:**
```json
{
  "ok": true,
  "timestamp": 1675360800000
}
```

Este endpoint es muy ligero y no consume recursos. Perfecto para keep-alive.

---

## ❓ Preguntas Frecuentes

**P: ¿Cuánto cuesta UptimeRobot?**
R: Es gratuito para monitoreo básico (hasta 50 monitores)

**P: ¿Cada cuánto debo pinguear?**
R: Cada 5 minutos es suficiente. Más frecuente consume más recursos.

**P: ¿Qué pasa si el servidor cae?**
R: UptimeRobot te notifica por email. Puedes configurar alertas.

**P: ¿Afecta el performance del chatbot?**
R: No. El endpoint `/api/health` es muy ligero.

---

## 📞 Soporte

Si tienes dudas sobre la configuración, contacta al equipo de desarrollo.

**¡Tu servidor nunca volverá a dormirse! 🎉**
