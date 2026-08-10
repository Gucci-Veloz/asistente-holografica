# POR QUÉ SÍ / POR QUÉ NO — Justificación de Decisiones Técnicas
 
> Documento de respaldo estratégico — Fase 2, 28 jun 2026.
> Propósito: explicar en lenguaje claro el razonamiento detrás de cada
> decisión técnica del sistema. Útil para conversaciones con David y
> para la presentación final.
 
---
 
## 1. Cámara — "En Works ya tenemos cámaras"
 
**Lo que David va a decir:**
> "Tenemos cámaras de seguridad instaladas. ¿Para qué comprar otra?"
 
**La respuesta:**
Las cámaras de seguridad y las cámaras de reconocimiento facial tienen
propósitos opuestos — y por eso sus especificaciones son incompatibles.
 
| Dimensión | Cámara de seguridad de Works | Lo que necesita el sistema |
|---|---|---|
| Posición de montaje | Techo — ángulo picado hacia abajo | Altura de rostro (~1.5m) — ángulo frontal |
| Lo que graba | El área completa (para ver qué pasó) | El rostro específico (para identificar quién es ahora) |
| Propósito | Evidencia del pasado | Autenticación en tiempo real |
| Protocolo de salida | Propietario del fabricante (NVR/DVR) | Estándar abierto (USB/UVC) compatible con el sistema |
 
**El argumento definitivo en una línea:**
Una cámara en el techo ve la coronilla de la gente. El sistema necesita
ver la cara. Son ángulos físicamente incompatibles.
 
**Por qué la BRIO 4K y no una cámara más barata:**
La entrada de Works tiene luz de calle entrando por la puerta de vidrio.
El interior está más oscuro. Eso se llama entorno "backlit" (contraluz).
 
En esa condición, una cámara sin WDR (Wide Dynamic Range) produce rostros
oscuros o sobreexpuestos — el sistema no puede reconocer lo que no puede
ver con claridad. La Logitech BRIO 4K tiene RightLight 3, que ajusta
automáticamente la exposición en tiempo real, compensando exactamente
ese contraste de luz. La diferencia de $130 USD sobre una cámara básica
es el costo de que el sistema funcione en condiciones normales de uso.
 
---
 
## 2. Privacidad biométrica — "¿Por qué no usar la nube?"
 
**Lo que David va a decir:**
> "Servicios como AWS o Google ya hacen reconocimiento facial. ¿Por qué
> no usarlos?"
 
**La respuesta:**
La Ley Federal de Protección de Datos Personales en Posesión de los
Particulares (LFPDPPP) clasifica los datos biométricos —incluyendo
patrones faciales— como datos sensibles. El tratamiento de datos
sensibles requiere consentimiento explícito y documentado, y su
transferencia a terceros (incluyendo servidores en la nube) requiere
contratos específicos de transferencia de datos.
 
Usar un servicio en la nube para procesar los rostros de los miembros
de Works significa que esos datos viajan a servidores de Amazon, Google
o Microsoft. Eso no solo introduce complejidad legal — también es el
argumento que un cliente corporativo usará para NO contratar el servicio.
 
**Con el sistema on-premise:**
- Los datos biométricos nunca salen del edificio.
- El procesamiento ocurre en el servidor local (Beelink GTR9 Pro).
- David puede decirle a cualquier cliente potencial: *"Los datos de tus
  empleados no salen de tus instalaciones."*
- Eso no es un detalle técnico — es el argumento de venta central.
---
 
## 3. Arquitectura on-premise — "¿Por qué Ubuntu si el SDK de ZKTeco es Windows?"
 
**El problema real:**
El SDK de ZKTeco (plcommpro.dll) es una librería de Windows de 32 bits.
No existe versión nativa para Linux.
 
**Por qué no se usa Windows como sistema principal:**
El stack completo del sistema (LLM, reconocimiento facial, avatar, panel
de administración) está optimizado para Linux/Ubuntu. Forzarlo a Windows
introduce más problemas de los que resuelve: compatibilidad de librerías
de IA, gestión de dependencias, estabilidad del servidor a largo plazo.
 
**La solución elegida (Ubuntu + VM Windows ligera):**
El Beelink GTR9 Pro tiene 128GB de RAM. Se corre una máquina virtual
Windows que usa únicamente 8GB — el 6% de la memoria total. Esa VM
tiene una sola función: correr el SDK de ZKTeco y comunicarse con el
controlador de accesos. El resto del sistema corre en Ubuntu de forma
nativa, estable y sin compromisos.
 
**Analogía para David:**
Es como tener un departamento de contabilidad dentro de una empresa de
diseño. El 94% del trabajo pasa en el estudio de diseño (Ubuntu). El 6%
pasa en la oficina de contabilidad (VM Windows). Cada uno en su espacio,
sin interferirse.
 
---
 
## 4. Stack de IA — "¿Por qué no usar ChatGPT, Deepgram o ElevenLabs?"
 
**Lo que David va a preguntar:**
> "¿Por qué no usar los servicios de IA que ya existen?"
 
**La respuesta:**
Todos los servicios que mencionas —ChatGPT, Deepgram, ElevenLabs,
AssemblyAI— son servicios en la nube. Cada vez que el avatar escucha
a alguien (STT), piensa (LLM) o responde con voz (TTS), esa información
viaja a servidores externos.
 
Eso tiene tres problemas para este sistema:
 
**Problema 1 — Privacidad.**
La voz es dato biométrico. Si el STT es en la nube, el audio de cada
conversación con el avatar —incluyendo nombres de miembros, estados de
cuenta, información operativa— sale del edificio. Eso contradice el
diferenciador central del producto.
 
**Problema 2 — Costo recurrente.**
Los servicios en la nube cobran por uso: por token generado, por minuto
de audio, por carácter de texto. En un sistema que opera 8-12 horas
diarias, ese costo se acumula todos los meses. El hardware on-premise
tiene un costo único de adquisición.
 
**Problema 3 — Disponibilidad.**
Si la conexión a internet de Works se cae, un sistema dependiente de la
nube deja de funcionar. El sistema on-premise sigue operando con
conexión local.
 
**Lo que se eligió y por qué:**
- **LLM: Qwen 3.6-27B** (lanzado abr 2026) — corre localmente en el
  Beelink, Apache 2.0, sin costo por token.
- **STT: Whisper Large v3 Turbo** (oct 2024) — reconocimiento de voz
  local, 99 idiomas incluyendo español, MIT license.
- **TTS: Chatterbox-Turbo** (mar 2026) — voz local con clonación de
  voz, español nativo, MIT license. Ganó el 65% de preferencia vs
  ElevenLabs en prueba ciega.
Los tres corren dentro del Beelink. Cero datos de voz salen del edificio.
 
---
 
## 5. Stack de reconocimiento facial — "¿Por qué no InsightFace?"
 
**El contexto:**
InsightFace con el modelo buffalo_l es técnicamente el stack más preciso
disponible en open source para reconocimiento facial. Fue la primera
opción evaluada.
 
**Por qué NO se eligió:**
El código de InsightFace es MIT (libre), pero los modelos —incluyendo
buffalo_l— requieren licenciamiento comercial separado con costo no
publicado. Para usar buffalo_l en un producto comercial como este, se
debe contactar a InsightFace para negociar una licencia.
 
Dado que el hardware ya representa la inversión principal del piloto,
añadir un costo de licencia de modelo con precio incierto va en contra
de la estructura económica acordada.
 
**Lo que se eligió y por qué:**
DeepFace (MIT) con backend FaceNet512 (Apache 2.0):
- 97.4% de accuracy en pruebas reales para este tipo de caso de uso.
- 100% libre para uso comercial, sin contactar a ningún proveedor.
- Para 50 miembros en una entrada con iluminación controlada, la
  diferencia de accuracy vs. buffalo_l no es perceptible en operación.
- Liveness detection: Silent-Face-Anti-Spoofing (MiniVision, open source)
  para detectar intentos de acceso con fotos.
**La regla que guía esta decisión:**
La accuracy perfecta no justifica un costo de licencia incierto en un
piloto de validación. Si el producto escala y la diferencia de accuracy
se vuelve crítica, se re-evalúa para instalaciones enterprise.
 
---
 
## Principio transversal
 
Todas las decisiones anteriores siguen la misma lógica:
 
> **El sistema debe funcionar completamente dentro del edificio,
> sin depender de servicios externos, sin costos recurrentes por uso,
> y sin transferir datos de los miembros a terceros.**
 
Ese principio no es una restricción técnica — es el argumento de venta.
Un cliente corporativo que evalúe este sistema puede verificar, en
tiempo real, que ningún dato de sus empleados sale de sus instalaciones.
Eso es lo que lo diferencia de cualquier alternativa en el mercado.