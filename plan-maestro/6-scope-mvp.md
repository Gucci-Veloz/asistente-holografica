# SCOPE DEL MVP — Sistema de Recepción con IA on-premise
 
> Documento cerrado en Fase 1 — 28 jun 2026.
> Fuente de verdad del alcance del piloto en Works.
> Cualquier cambio de scope requiere decisión explícita de Guus y actualización de este archivo.
 
---
 
## Módulos DENTRO del MVP
 
### M1 — Kiosk con avatar conversacional
- Hardware: pantalla OLED transparente + cámara + micrófono + altavoces.
- Avatar de IA con voz, rostro y personalidad del espacio Works.
- Interacción por voz y/o pantalla táctil.
- Ubicación: entrada principal (única).
### M2 — Reconocimiento facial de miembros
- Base biométrica local: ~50 miembros activos.
- Procesamiento 100% on-premise. Datos biométricos nunca salen del servidor.
- Liveness detection (anti-spoofing con foto).
- Cumplimiento LFPDPPP: consentimiento documentado en enrolamiento.
### M3 — Control de acceso automático (entrada principal)
- Integración ZKTeco Pull SDK v2.0 — función `ControlDevice`.
- Flujo: cámara reconoce miembro → avatar saluda → puerta abre automáticamente.
- Gestión de morosos: si miembro tiene estado "moroso" en el sistema → puerta no abre → avatar indica acercarse a administración.
- Scope de integración SDK: **solo la entrada principal**. Las 25 puertas internas se excluyen permanentemente.
### M4 — Gestión de visitantes y paquetería
- **Visita agendada (QR):** visitante presenta QR pre-generado → avatar lo recibe → acceso temporal automático → notificación al anfitrión.
- **Visita sin aviso:** visitante se identifica en kiosk → avatar localiza al miembro → notifica → miembro aprueba/rechaza → acceso temporal o espera.
- **Paquetería:** repartidor llega → avatar activa flujo entrega → acepta automáticamente sin esperar al destinatario → registra: foto del repartidor + foto del paquete + firma en pantalla táctil del kiosk + timestamp → genera acuse PDF → notifica al miembro destinatario por WhatsApp con foto del paquete.
- Visitantes y repartidores no requieren biométricos. No acceden más allá de recepción.
### M5 — Notificaciones WhatsApp
- Canal principal de comunicación con miembros: WhatsApp Business API.
- Eventos que generan notificación automática:
  - Llegada de visitante (con foto).
  - Llegada de paquete (con foto + acuse PDF).
  - Alerta de pago próximo: 7, 5 y 3 días antes de fecha de corte.
  - Acceso denegado (miembro moroso intenta entrar).
- Proveedor de API: **[INVESTIGAR / DECISIÓN-GUUS]** en Fase 2 (Twilio vs. alternativas).
### M6 — Panel de administración
- Enrolamiento biométrico de miembros (registro de rostro + datos).
- Gestión de estado de cuenta por miembro: al corriente / moroso.
- Configuración de fecha de corte por miembro (activa alertas automáticas de M5).
- Gestión de tarjetas ZKTeco: notificación al admin si tarjeta bloqueada. Desbloqueo/reprogramación directa: **[INVESTIGAR]** según capacidades del SDK (Fase 2).
- Logs de acceso: entradas/salidas con timestamp y foto (desde `GetDeviceData`).
- Registro de entregas de paquetería con acuse PDF.
---
 
## Flujos conversacionales del avatar
 
| ID | Situación | Resultado |
|----|-----------|-----------|
| F1 | Miembro reconocido por cámara | Avatar saluda por nombre → puerta abre automáticamente |
| F2 | Visitante con QR (visita agendada) | Avatar escanea QR → da bienvenida → notifica anfitrión → acceso temporal |
| F3 | Visitante sin aviso previo | Avatar pregunta a quién visita → notifica al miembro → miembro aprueba o baja → acceso o espera |
| F4 | Consulta general | Avatar responde con LLM entrenado en info de Works (horarios, WiFi, salas, servicios) |
| F5 | Solicitud de ayuda o emergencia | Avatar escala a administrador o guardia de seguridad |
| F6 | Entrega de paquetería | Avatar activa flujo entrega → acepta → captura foto + firma → genera acuse → notifica al destinatario |
 
---
 
## Fuera del MVP — definitivo o diferido
 
| Ítem | Estado | Motivo |
|------|--------|--------|
| 25 puertas internas con ZKTeco | ❌ Descartado permanentemente | Flujo de tarjetas funciona; scope desproporcionado al valor agregado |
| Desbloqueo de tarjetas desde avatar | 🔄 Fase 2 | Depende de capacidades verificadas del SDK |
| Reserva de salas de juntas desde kiosk | ❌ Fuera MVP | Works usa Excel; no hay sistema que integrar |
| App móvil para miembros | ❌ Posterior | WhatsApp cubre la necesidad en MVP |
| Reportes y analytics avanzados | ❌ Posterior | No es necesario para validar el producto |
| Integración con pagos o facturación | ❌ Posterior | Fuera del scope de recepción |
| Multi-idioma (más de ES/EN) | ❌ Posterior | Querétaro no lo requiere en piloto |
 
---
 
## Notas de arquitectura relevantes para Fase 2
 
- El servidor on-premise es el Beelink GTR9 Pro corriendo Ubuntu.
- La VM Windows ligera dentro del Beelink corre solo el SDK ZKTeco y ZKAccess.
- Ubuntu (sistema principal) se comunica con la VM vía API local en red interna.
- La biométrica, el LLM, el avatar y el panel de admin corren en Ubuntu directamente.
- Pendiente verificar: si Wine permite correr `plcommpro.dll` de forma estable, la VM se elimina.