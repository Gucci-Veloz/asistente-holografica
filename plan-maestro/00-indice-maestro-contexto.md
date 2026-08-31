# ÍNDICE MAESTRO DE CONTEXTO — Proyecto HOLO AI

> Documento puente. Generado por el Project original de Claude Desktop del
> Sistema de Recepción con IA (co-dirección estratégica con Guus) para
> transferir contexto verificado al Project hermano en Claude Desktop-Cowork,
> nombrado **HOLO-AI**, que tiene acceso
> a la misma carpeta de archivos `.md`/`.html` pero no al historial conversacional
> donde se tomaron las decisiones y se corrigieron los errores.
>
> Cada afirmación de este documento cita el archivo fuente exacto. Donde el dato
> no tiene fuente verificable en archivo, se marca explícitamente como tal. No
> se rellenó ningún hueco con estimaciones. Este documento fue construido con
> `sequential-thinking` + `advanced-reasoning` revisando los 19 archivos de la
> carpeta uno por uno con la herramienta `view`, no desde memoria de conversación.

---

## 0. Cómo usar este documento

1. Lee primero la sección 1 (reglas no negociables) — son las que más fácil se
   rompen por accidente al continuar el trabajo sin el historial completo.
2. Lee la sección 8 (discrepancias sin resolver) antes de generar cualquier
   entregable nuevo — hay al menos una corrección urgente pendiente.
3. Usa la sección 3 (mapa de archivos) como tabla de contenidos para saber en
   qué archivo real está cada tema, en vez de releer todo cada vez.
4. Este documento **no reemplaza** a `2-tasks.md` como fuente de verdad de
   progreso — la complementa, porque `2-tasks.md` está desactualizado frente a
   eventos posteriores narrados en `10-bitacora-decisiones.md` (ver sección 8).

---

## 1. Reglas no negociables del proyecto

Estas reglas vienen del system prompt original del Project y de las 5 Reglas de
Oro. Se resumen aquí porque son las que un agente nuevo, sin el historial,
podría violar por desconocimiento.

### 1.1 Nombre del producto
El producto se llama **HOLO AI** — así lo confirma Guus en la sesión donde se
solicitó este documento. Punto crítico: **ningún archivo de la carpeta base
(ni `2-tasks.md`, ni ninguno de los 7 `.html`) refleja todavía este nombre.**
`2-tasks.md` línea 150 dice literalmente: *"Nombre del producto: PENDIENTE —
Guus decide."* Esto es un desfase de sincronización entre lo decidido en
conversación y lo escrito en archivo — no un dato inventado por este índice,
sino algo que debe confirmarse con Guus y luego propagarse a los archivos base.

**El nombre del coworking piloto/cliente de Guus es un dato distinto: es el
espacio físico donde ocurre el piloto, propiedad de la familia de David.** Ese
nombre **nunca** debe usarse como si fuera el nombre comercial del producto,
en ningún entregable dirigido a clientes o a terceros. Uno de los siete `.html`
existentes (`1-presentacion-works-v2.html`) sí usa el nombre del coworking en
su título y en el texto del "hero" — eso es correcto únicamente en su función
original (presentación específica para ese piloto), pero **no debe copiarse
ese patrón de naming a ningún documento nuevo del producto genérico**, y ese
archivo en particular queda marcado para revisión de naming antes de reusarse
con otro cliente (ver sección 8).

### 1.2 Confidencialidad del contexto de fundador
Todo lo relativo a estructura societaria de Guus (vehículos corporativos
existentes, participación, planes de escalar a otra figura legal, rondas de
capital) es **estrictamente confidencial y nunca debe aparecer en documentación
que pueda llegar a David o a cualquier cliente/socio.** Ver detalle en sección
7.3 — marcado con alerta.

### 1.3 Anti-invención (las 5 reglas de oro, resumidas)
1. Ningún modelo, hardware, precio, latencia o cifra se afirma sin fuente
   verificada (`web_search` en tiempo real o ya verificado en
   `4-research-mercado.md`).
2. Si no se sabe con certeza, se dice explícitamente — nunca se rellena.
3. Donde hay opciones (modelos, hardware, nombres, precios de venta), el
   agente presenta comparativa y **Guus o David deciden** — nunca se asume.
4. Este Project es de estrategia y negocio — no genera código de producción.
5. No se avanza de fase sin cerrar la anterior, salvo autorización explícita.

### 1.4 Regla de los Dos/Tres Caminos
Cualquier decisión con impacto económico que David vaya a ver se presenta como
caminos completos de sistema (nunca add-ons sueltos). Aplica desde Fase 2 en
adelante. Fuente: `5-reglas-decision.md`, líneas 35-55.

---

## 2. Estado real del proyecto — consolidado

**Producto:** sistema de recepción con inteligencia artificial on-premise —
kiosk con avatar conversacional, reconocimiento facial, control de accesos y
comunicación omnicanal, para coworkings y oficinas corporativas. Diferenciador
central: 100% del procesamiento biométrico ocurre dentro del edificio, nunca
en la nube (argumento de venta bajo la LFPDPPP). Fuente: `3-contexto-proyecto.md`.

**Fase de madurez real:** "Piloto en desarrollo". El stack técnico está
definido y ya hubo una presentación completa al cliente/socio piloto con
resultado positivo, pero **nada está instalado ni operando todavía.** Esto es
importante porque uno de los siete `.html` (`2-presentacion-mercado.html`)
contiene lenguaje en tiempo presente que contradice este estado — ver alerta
en sección 8, punto 8.2.

**Cliente/socio piloto:** dueño de un coworking en Querétaro, quien se acercó
proactivamente a Guus (demanda validada antes de construir). Aportó espacio,
contactos y red comercial. Acuerdo verbal, nada firmado aún. Ese coworking
funcionará como showroom permanente. Fuente: `3-contexto-proyecto.md`,
`10-bitacora-decisiones.md`.

**Naturaleza del proyecto:** híbrido — encargo casi confirmado con el cliente
piloto + visión de producto propio escalable desde el inicio. Fuente:
`3-contexto-proyecto.md`.

**Progreso por fases según `2-tasks.md`** (última actualización de ese archivo:
29 jun 2026 en su cuerpo, con anotaciones sueltas hasta días después):
- Fase 0 (cierre de datos faltantes): **cerrada** — 28 jun 2026.
- Fase 1 (producto y alcance del MVP): **cerrada** — 28 jun 2026.
- Fase 2 (investigación y selección técnica): **cerrada** — 29 jun 2026.
- Fase 3 (arquitectura técnica): abierta en el archivo, pero de facto ya
  existe un documento de arquitectura terminado (`4-presentacion-arquitectura.html`).
- Fase 4 (modelo de negocio y economía): abierta en el archivo, pero de facto
  ya existen dos herramientas construidas (`6-calculadora-roi.html` y
  `7-precio-de-venta.html`) — ver sección 6.
- Fases 5 a 8: abiertas según el archivo.
- **Importante:** `2-tasks.md` no refleja que ya hubo una presentación
  completa a David con una segunda reunión posterior — eso solo vive en
  `10-bitacora-decisiones.md`. Ver discrepancia en sección 8.1.

---

## 3. Mapa de archivos fuente

Dos series de numeración independientes y no relacionadas entre sí: los `.md`
(2 en adelante) son estrategia/referencia; los `.html` (1 en adelante) son
entregables de presentación (formato SCPHA: un solo archivo, sin dependencias
externas, tipografía serif en títulos, paleta de tokens CSS consistente).

### 3.1 Archivos `.md`

| Archivo | Contenido | Vigencia |
|---|---|---|
| `2-tasks.md` | Fuente de verdad de progreso por fase, decisiones tomadas, pendientes | Vigente similar a `10-bitacora-decisiones.md` (ver sección 8.1) |
| `3-contexto-proyecto.md` | Producto, cliente piloto, infraestructura existente, restricciones, perfil de Guus | Vigente |
| `4-research-mercado.md` | Datos de mercado y hardware verificados con fuente y fecha (28 jun / 8 jul 2026) | Vigente |
| `5-reglas-decision.md` | Matriz de autorización, test de 3 filtros, regla de los Dos Caminos | Vigente y completa (verificada línea por línea en `10-bitacora-decisiones.md` sección 2) |
| `6-scope-mvp.md` | Los 6 módulos del MVP (M1-M6), 6 flujos conversacionales (F1-F6), lo que queda fuera de scope | Vigente — cerrado en Fase 1 |
| `7-sdk-zkteco.md` | Documentación técnica cruda del SDK ZKTeco Pull SDK V2.0 (funciones, parámetros, códigos de error) | Vigente — referencia técnica, no narrativa |
| `8-justificacion-decisiones.md` | Por qué se eligió cada pieza técnica, en formato pregunta-de-David / respuesta | Vigente |
| `9-dos-caminos-sistema.md` | Comparativa completa Camino 1 (AMD/Beelink) vs Camino 2 (NVIDIA/DGX Spark), base común, display, componentes descartados | Vigente — es el documento de precios de display correcto (ver 8.4) |
| `10-bitacora-decisiones.md` | Bitácora de continuidad verificada línea por línea contra los archivos reales (8 jul 2026): orden real de los 7 HTML, resultado de la presentación con David, pivote premium, hallazgos de investigación de holograma | **El documento más reciente y completo sobre el estado narrativo real del proyecto** |
| `11-investigacion-holograma-premium.md` | Investigación de mercado sobre Pepper's Ghost por proyección + panorama de hardware premium de holograma (gobierno/Fortune 500) | Vigente — ver nota de duplicado en sección 9 |
| `12-investigacion-profundidad-sin-marcos.md` | **Idéntico byte a byte a `11-investigacion-holograma-premium.md`** | Duplicado — ver sección 9 |
| `POSIBLE_BASURA_creada.md` | El prompt de investigación que generó los archivos 11/12 | Metadata de proceso, no contenido de negocio — ver sección 9 |

### 3.2 Archivos `.html` (entregables de presentación, formato SCPHA)

Orden narrativo real confirmado por Guus (fuente: `10-bitacora-decisiones.md`
sección 1): gancho → visión macro (mercado + regulación) → credibilidad técnica
→ operación → remate financiero.

| # | Archivo | Función narrativa | Alerta de vigencia |
|---|---|---|---|
| 1 | `1-presentacion-works-v2.html` | Gancho emocional — producto, holograma, 3 decisiones interactivas (display/motor/WhatsApp) | Usa el nombre del coworking piloto como marca del documento (ver 1.1). Muestra únicamente Fan/OLED/Transparente como las 3 opciones de display — **anterior al pivote premium**, ver 8.3 |
| 2 | `2-presentacion-mercado.html` | Visión macro — tamaño de industria (gráficas animadas) | **Contiene overclaiming en tiempo presente sin corregir** — ver 8.2, máxima prioridad |
| 3 | `3-oportunidad-regulatoria.html` | Visión macro — reforma laboral mexicana (reducción de jornada) como urgencia | Vigente, sin overclaiming detectado |
| 4 | `4-presentacion-arquitectura.html` | Credibilidad — anatomía del sistema (7 "órganos" del avatar) + hardware (2 caminos + display + accesorios) | Vigente. Menciona el nombre del coworking piloto una sola vez, en su rol correcto ("piloto en [coworking]") |
| 5 | `5-dashboard-recepcion-ia.html` | Operación práctica — mockup del panel de administración | Usa placeholder genérico "Coworking Piloto", no el nombre real ni el del producto |
| 6 | `6-calculadora-roi.html` | Prueba personal — calculadora interactiva de ahorro vs. recepcionista humana | Herramienta/metodología lista; campos son inputs ajustables, sin resultado precargado con datos reales — ver sección 6 |
| 7 | `7-precio-de-venta.html` | Clímax de sociedad — calculadora COGS vs. precio de venta, descreme de precios | Cifras de ejemplo en el JS (hardware $25,000, instalación $15,000, soporte $48,000, multiplicador 3.2x) son **ilustrativas del framework, no decisiones de precio cerradas** — el propio documento lo dice explícitamente |

Todos los 7 preceden al pivote premium narrado en `10-bitacora-decisiones.md`
sección 6 (ver 8.3) — ninguno refleja todavía la dirección hacia gobierno y
empresas premium, ni la investigación de Pepper's Ghost/AR de los archivos 11/12.

---

## 4. Producto — resumen técnico consolidado

### 4.1 Scope del MVP (fuente: `6-scope-mvp.md`)
Seis módulos: M1 kiosk con avatar conversacional · M2 reconocimiento facial de
miembros (on-premise, liveness detection, consentimiento LFPDPPP) · M3 control
de acceso automático en la entrada principal (vía SDK ZKTeco) · M4 gestión de
visitantes y paquetería (QR, sin aviso, paquetería con foto+firma+acuse PDF) ·
M5 notificaciones WhatsApp (visita, paquete, alertas de pago, acceso denegado)
· M6 panel de administración (enrolamiento, estado de cuenta, logs).

Fuera del MVP, definitivo: las 25 puertas internas con lector ZKTeco del
coworking piloto (se mantienen con su flujo actual de tarjeta/huella, sin
tocar), reserva de salas, app móvil, analytics avanzados, pagos/facturación,
multi-idioma más allá de ES/EN.

### 4.2 Arquitectura on-premise (fuente: `3-contexto-proyecto.md`, `6-scope-mvp.md`, `8-justificacion-decisiones.md`)
- Ubuntu 24 como sistema principal: LLM, STT, TTS, reconocimiento facial,
  avatar, panel de administración.
- VM Windows ligera (8 GB de los 128 GB disponibles) dedicada exclusivamente
  al SDK ZKTeco (`plcommpro.dll`, DLL de 32 bits, Windows-only) y ZKAccess.
  Comunicación con Ubuntu vía API local.
- Pendiente de investigar (no resuelto): si Wine permite correr
  `plcommpro.dll` de forma estable en Ubuntu nativo, eliminando la VM.
- Integración ZKTeco vía Pull SDK V2.0, TCP/IP puerto 4370. Funciones clave:
  `ControlDevice` (abre puerta), `SetDeviceData` tabla `user` (altas/bajas de
  tarjetas), `GetDeviceData` tabla `transaction` (logs en tiempo real).
  Documentación completa de parámetros y códigos de error en `7-sdk-zkteco.md`.
- Scope de integración: **solo la entrada principal** del coworking piloto.

### 4.3 Stack de software — idéntico en ambos caminos de hardware, costo $0 en licencias
(fuente: `9-dos-caminos-sistema.md`, `8-justificacion-decisiones.md`, `2-tasks.md`)

| Función | Tecnología | Licencia | Fecha de lanzamiento / verificación |
|---|---|---|---|
| LLM (cerebro) | Qwen 3.6-27B vía Ollama | Apache 2.0 | Lanzado 22 abr 2026 |
| STT (oído) | Whisper Large v3 Turbo vía faster-whisper | MIT | oct 2024 · 50-300ms local · 99 idiomas |
| TTS (voz) | Chatterbox-Turbo (Resemble AI) | MIT | 26 mar 2026 · español nativo · 9 idiomas · ganó 65% preferencia vs. ElevenLabs en prueba ciega |
| Reconocimiento facial | DeepFace + RetinaFace (detector) + FaceNet512 (Apache 2.0) | MIT/Apache 2.0 | 97.4% accuracy en condiciones controladas |
| Anti-spoofing | Silent-Face-Anti-Spoofing (MiniVision) | Open source | Detecta intentos de acceso con foto |
| Avatar / lip-sync | ai-avatar-system (PunithVT/GitHub) + MuseTalk v1.5 (Tencent) | MIT | may 2026 / mar 2025 |

Componentes evaluados y descartados, con motivo (fuente: `9-dos-caminos-sistema.md`):
Qwen 3.7 (propietario, viola on-premise) · distil-whisper (solo inglés) ·
Coqui XTTS v2 (licencia CPML no comercial) · Kokoro (sin clonación de voz) ·
InsightFace/buffalo_l (licencia comercial de modelo con costo incierto) ·
RAVATAR como plataforma de avatar (cloud-dependent).

### 4.4 Hardware — Regla de los Dos Caminos (fuente: `9-dos-caminos-sistema.md`)

**Camino 1 — AMD (Beelink GTR9 Pro):** AMD Ryzen AI Max+ 395, 128 GB LPDDR5X
unificada, 2 TB SSD, GPU Radeon 890M integrada. Costo: **~$1,985-1,999 USD**
(precio de lista $2,399 USD; precio real de mercado frecuente ~$1,999 USD;
fuente: ServeTheHome + Notebookcheck + bee-link.com oficial, verificado 28 jun
2026 — nota explícita en `4-research-mercado.md`: la cifra de $3,999 USD **no**
corresponde a este equipo en ninguna fuente verificada). Único punto abierto:
MuseTalk (lip-sync) está optimizado para CUDA; sobre AMD corre vía ROCm y
**requiere validación en hardware real** — si no alcanza rendimiento, se cae a
Wav2Lip como alternativa compatible AMD/CPU. Esto se mide, no se estima.

**Camino 2 — NVIDIA (DGX Spark):** GB10 Grace Blackwell, 20-core ARM + GPU
Blackwell, 128 GB LPDDR5X unificada, 1 PetaFLOP FP4, CUDA nativo, Ollama
preinstalado. Costo: **~$3,999 USD (lanzamiento) → ~$4,699 USD (precio
actual, subió en feb 2026 por escasez de memoria LPDDR5X)**, verificado a jun
2026. Ventaja: MuseTalk corre a 30fps+ garantizado en CUDA, sin el punto
abierto del Camino 1. Diferencia de costo vs. Camino 1: **~$2,700 USD más**.

Nota de precaución de lectura: el "$3,999 USD" del DGX Spark (precio de
lanzamiento) y el "$3,999 USD" que `4-research-mercado.md` advierte que **no**
corresponde al Beelink son la misma cifra numérica por coincidencia — no debe
confundirse un producto con otro al citar precios.

Existe también, documentada por transparencia y no como camino canónico, una
workstation con RTX 5090 (32 GB GDDR7) ~$4,500 USD como variante de mayor
velocidad de inferencia pura, cotizable aparte si David prioriza velocidad
sobre el espejo exacto de arquitectura del Beelink.

Cámara común a ambos caminos: **Logitech BRIO 4K (~$199 USD)** — elegida por
WDR RightLight 3 por hardware, necesario porque la entrada del coworking
piloto es un entorno backlit (luz de calle por la puerta de vidrio). No es
sustituible por una cámara de seguridad existente: propósito, ángulo de
montaje y protocolo de salida son incompatibles (detalle completo en
`8-justificacion-decisiones.md`, sección 1).

### 4.5 Display — decisión pendiente del cliente/socio (siempre 3 opciones, la emocional incluida)
Precios **vigentes y correctos** (fuente cruzada: `9-dos-caminos-sistema.md`,
`10-bitacora-decisiones.md` sección 3, y los 7 `.html`):

| Opción | Precio MXN | Qué compra |
|---|---|---|
| Fan holográfico LED | ~$2,500-3,200 MXN | El "holograma" que generó el entusiasmo inicial. Avatar en loop pre-renderizado, **no en tiempo real**. Requiere pantalla táctil adicional (costo pendiente de cotizar) |
| OLED convencional 55" | ~$12,000-15,000 MXN | Avatar en tiempo real, táctil nativo, audio integrado. Mejor relación precio/función completa |
| OLED transparente 55" | ~$26,000-38,500 MXN | Avatar flotante sobre fondo oscuro. Máximo impacto de showroom |

Bocinas (solo si se elige fan holográfico o transparente, ya que el OLED
convencional trae audio integrado): ~$2,190 MXN.

**Existe una cuarta ruta en investigación, no agregada aún a esta tabla ni a
ningún `.html`:** Holograma por Efecto Pepper's Ghost mediante proyección
sobre lámina acrílica angulada. Ver sección 5.2 y 8.3 — pendiente de
cotización local real antes de documentarse como opción formal.

### 4.6 WhatsApp Business API — decisión pendiente del cliente/socio
(fuente: `9-dos-caminos-sistema.md`, `2-tasks.md`)

| Opción | Costo mensual (coworking piloto) | Perfil |
|---|---|---|
| Kapso | ~$55-90 MXN | Free tier 2,000 msgs/mes, MCP nativo, plataforma joven (lanza dic 2025) |
| Twilio | ~$145-215 MXN | 10+ años en el mercado, SDK Python, soporte 24/7 |

Diferencia real: ~$90-125 MXN/mes. Predicción documentada (no decisión
cerrada): el cliente elegiría Twilio.

---

## 5. Mercado y regulación — datos verificados

(fuente: `4-research-mercado.md`, verificado 28 jun / 8 jul 2026)

### 5.1 Tamaño de mercado
- Asistentes holográficos con IA (global): ~$842M USD (2025) → ~$6,355M USD
  (2035), CAGR ~22.4%. Fuente: Fact.MR.
- Reconocimiento facial (México): proyección ~$129.6M USD a 2030, CAGR ~9.36%.
  Fuente: Statista.
- Recepcionistas virtuales con IA (global): ~$4.64B USD estimado para 2026.
  Fuente: ALM Corp.

### 5.2 Competencia
- **RAVATAR + RAVABOX:** avatares 3D en holoboxes, casos reales en hotelería y
  gobierno internacional. Presencia en México: un evento puntual (holograma de
  Tesla, Universidad Panamericana CDMX, 2025), sin presencia comercial
  establecida en recepción corporativa.
- **Proto Hologram:** hardware propietario + ProtoOS, SOC-2/HIPAA, sin
  presencia identificada en LATAM. Más de 20 clientes/socios Fortune 500
  declarados (H&M, Christie's, T-Mobile, DHL, PwC, Netflix, AT&T — fuente:
  protohologram.com/faqs, 2025) y despliegues gubernamentales documentados en
  EE.UU. (aeropuerto de Jacksonville, SFO, Gobernador de Nebraska).
- **ALICE Receptionist:** visitor management con avatar, desde $199 USD/mes,
  sin presencia en México ni soporte en español.
- **Gap de mercado identificado:** ningún actor integra localmente avatar +
  biometría + gestión operativa de coworking/accesos + soporte local en
  México. Fuente: `4-research-mercado.md`.

### 5.3 Reforma laboral mexicana (verificado 8 jul 2026)
Reforma constitucional publicada en DOF 3 mar 2026; reforma a la LFT publicada
1 may 2026. Calendario de reducción de jornada: 48h(2026) → 46h(2027) →
44h(2028) → 42h(2029) → 40h(2030). Registro electrónico de jornada obligatorio
(Art. 132 fracción XXXIV). Multa: 250 a 5,000 UMA por trabajador
($29,328-$586,550 MXN), Art. 994 fracción IV Bis. Fuentes: STPS, DOF, Senado.

### 5.4 Factor de carga patronal
25%-50% adicional al salario nominal en México, según nivel salarial y estado
(IMSS, Infonavit, aguinaldo, prima vacacional, ISN). **No hay cifra única
confiable** — se usa como variable ajustable en la calculadora de ROI, no
como dato fijo. Fuentes: minu.mx, microsip.com.

### 5.5 Hardware de holograma premium — investigación reciente (fuente:
`11-investigacion-holograma-premium.md`, duplicada en `12-...`)

**Bloque A — Pepper's Ghost por proyección (ruta económica local):**
proyectores con especificación ANSI real (no lúmenes LED de marketing)
recomendados entre 3,000-5,000 ANSI lúmenes DLP, 1080p nativo, con fondo negro
absoluto en el contenido. Opciones disponibles en México: desde Wanbo X5 Pro
($5,117 MXN, 1,100 ANSI) hasta ViewSonic PA503HD ($13,109 MXN, 4,000 ANSI).
Lámina de acrílico a medida: desde $859 MXN por hoja base; corte, pulido de
canto y tratamiento antirreflejante se cotizan aparte localmente. Estimación
de costo total del conjunto (piloto DIY): **~$8,000 MXN (rango bajo) a
~$16,000-20,000 MXN (rango alto)**, más producción de contenido — **sin
cotización local formal todavía**, no debe tratarse como precio cerrado.

**Bloque B — Panorama premium (gobierno / Fortune 500):** Proto Epic/Luma
($29,000-$65,000 USD) · Proto M mesa ($5,900-$6,900 USD) · ARHT Capsule
(desde $60,000 USD) · Looking Glass (light-field, sin precio público general,
$10,000-$20,000+ USD según tamaño) · HYPERVSN SmartV (~$3,200 USD por unidad,
modular). Estado del arte "glasses-free" 2026: Samsung Spatial Signage
(85", profundidad percibida hasta 500mm, sin precio de lista divulgado).
Caso documentado de gobierno pagando premium por "ser los primeros": ciudad
de Jacksonville, FL, pagó ~$75,000 USD por una unidad Proto Box — caso
**altamente polémico** en auditoría pública, retirado a los 6 meses.
**Advertencia estratégica ya documentada en la fuente:** para un pitch a
gobierno mexicano, conviene anclar el producto a su función de servicio
(reducción de filas, atención multilingüe) y no a la novedad tecnológica, por
el mismo riesgo de escrutinio de gasto público.

---

## 6. Modelo de negocio — estado de la Fase 4

`2-tasks.md` marca la Fase 4 (modelo de negocio y economía) como abierta, pero
ya existen dos herramientas construidas que implementan su método (fuente:
`6-calculadora-roi.html`, `7-precio-de-venta.html`):

- **Calculadora de ROI** (`6-calculadora-roi.html`): compara costo real de una
  recepcionista humana (salario + factor de carga patronal ajustable 25-50%)
  contra la inversión del sistema (servidor + display + fee de desarrollo
  $45,000-65,000 MXN + soporte mensual $3,000-5,000 MXN). Los campos son
  inputs interactivos — **no hay resultado precargado con datos reales
  confirmados del coworking piloto** (salario real de su recepcionista actual,
  tipo de cambio del día, etc.). La herramienta está lista; falta alimentarla.
- **Calculadora de precio de venta** (`7-precio-de-venta.html`): separa COGS
  (hardware + instalación + soporte anual por unidad futura, distinto al fee
  del piloto) de precio de venta, usando el framework de descreme de precios
  (price skimming) con un multiplicador ajustable sobre el costo. Las cifras
  visibles en el documento (hardware $25,000, instalación $15,000, soporte
  anual $48,000, multiplicador 3.2x, 4 unidades/año) son **valores ilustrativos
  del framework — el propio documento aclara que no son un dato de mercado ni
  una decisión de precio cerrada.**

No existe todavía economía unitaria con números reales del coworking piloto ni estructura
de ingresos decidida por Guus — eso sigue abierto según `2-tasks.md` Fase 4.

---

## 7. Historial con el cliente/socio piloto y contexto estratégico

### 7.1 Estructura del acuerdo piloto
El cliente/socio piloto paga hardware + software + fee de Guus. No hay
presupuesto fijo predefinido — se construye con cotizaciones reales en MXN.
Fee de desarrollo/instalación: $45,000-65,000 MXN (pago único). Soporte
mensual: $3,000-5,000 MXN. Fuente: `2-tasks.md`, `10-bitacora-decisiones.md`.
Acuerdo escrito antes de instalar nada — decidido como buena práctica
irrefutable. Cumplimiento LFPDPPP para datos biométricos — decidido.

### 7.2 Resultado de la primera presentación (fuente: `10-bitacora-decisiones.md` sección 6)
**Positivo.** El cliente/socio piloto solicitó una segunda reunión — el "sí"
a continuar el proyecto está implícito; ya no busca convencerse, está en fase
de co-diseño. En esa segunda reunión participaron también su padre y su
hermano, lo que introduce dinámicas relacionales y estratégicas nuevas que
Guus estaba documentando con un sistema de etiquetado (ANTES/DURANTE/DESPUÉS
× HECHO/LECTURA-GUUS) al momento del corte de este índice — sin que ese
documento de etiquetado específico exista todavía como archivo en esta carpeta.

**Requisitos y direcciones nuevas que dio el cliente/socio piloto** (todos
con fuente en `10-bitacora-decisiones.md` sección 6, no inferidos):
- No quiere que se vean los marcos/bisel de una pantalla — ni la OLED
  transparente lo convenció al 100%.
- **La idea del proyector (Pepper's Ghost) la propuso él, no Guus.**
- Piensa en escalar el hardware físico hacia **Gobierno** y **empresas
  premium de high-ticket**. Su definición de "en masa" es escalar la
  comercialización (replicar a más clientes), **no** abaratar el costo
  unitario.
- Quiere sensación de "varios avatares" atendiendo simultáneamente para
  corporativos de alto tráfico. Decisión tomada al respecto: se dirige la
  venta por defecto hacia desplegar **múltiples unidades físicas idénticas**
  juntas (etiquetada en la fuente como "Opción B"), sin descartar una
  configuración distinta (etiquetada como "Opción A", ligada a una postura de
  ahorro de cliente) para negociaciones específicas caso por caso. La fuente
  no detalla en qué consiste exactamente la "Opción A" más allá de esa
  asociación con ahorro — no se debe inventar el detalle.
- Dispuesto a **adaptar físicamente la entrada** (iluminación, paneles) del
  coworking piloto para que el efecto visual funcione.
- Inspiración explícita en AR (no VR), por experiencia previa con Oculus.
- **Objetivo de negocio declarado:** empresas grandes compitiendo por
  adquirirlo primero. Esto redefine el segmento — ya no es solo "ahorro vs.
  recepcionista humana" (el ángulo de los docs 6/7), sino **objeto de deseo
  premium**, donde para un cliente de alto capital la novedad vuelve el costo
  irrelevante. **Este ángulo de venta todavía no está construido en ningún
  documento** — es un punto abierto de trabajo futuro, no una tarea resuelta.

### 7.3 Contexto de estructura societaria — CONFIDENCIAL, NUNCA CLIENTE-FACING
Guus mencionó al cliente/socio piloto que la estructura legal del proyecto
depende de "hasta dónde lo veamos" — arrancando como SAS de CV y escalando a
SAPI de CV si crece. Esto fue mencionado en conversación, marcado como "más
adelante" y **explícitamente no accionable todavía**. Fuente:
`10-bitacora-decisiones.md` sección 6.

**Regla aplicable, sin excepción:** nada de esta sección 7.3 aparece jamás en
ningún entregable, presentación, o documento que pueda llegar al cliente/socio
piloto o a cualquier tercero.

---

## 8. Discrepancias detectadas — requieren confirmación explícita de Guus

Ninguno de estos puntos se resolvió por cuenta propia. Se listan con su
evidencia para que Guus decida cómo proceder.

### 8.1 Dos fuentes de "avance" que no coinciden
`2-tasks.md` marca las Fases 3 a 8 como abiertas y no menciona ninguna
presentación ya realizada. `10-bitacora-decisiones.md` sección 6 narra que la
presentación **ya ocurrió**, con resultado positivo, y que hubo una segunda
reunión con información estratégica nueva (pivote premium). **Pregunta para
Guus:** ¿se actualiza `2-tasks.md` para reflejar este hito y reabrir/reordenar
las fases según lo que realmente falta, o el criterio de "fase cerrada" de
`2-tasks.md` se refiere a algo distinto (cierre de decisiones de contenido,
no de eventos con el cliente)?

### 8.2 Overclaiming sin corregir en `2-presentacion-mercado.html`
Este documento, en su estado actual (verificado por lectura directa, no por
memoria), afirma en tiempo presente: *"Ya existe un primer caso funcionando
de verdad... hay un primer piloto operando en un espacio real de coworking en
Querétaro — el avatar reconoce, conversa, abre la puerta y avisa por WhatsApp,
hoy"* y *"El sistema opera en un espacio real, con miembros reales, todos los
días. Probado, no prometido."* Esto contradice el estado real del proyecto
(nada instalado todavía) y es exactamente el tipo de error que las reglas de
oro del proyecto buscan prevenir. **No se debe asumir que ya se corrigió en
otra sesión** — el archivo, tal como está en la carpeta ahora, sigue así.
Corrección pendiente de máxima prioridad antes de reutilizar este documento.

### 8.3 Los 7 `.html` preceden al pivote premium
Ninguno de los siete documentos de presentación refleja: la dirección hacia
Gobierno/empresas premium, el rechazo del cliente a biseles visibles de
pantalla, la ruta de Pepper's Ghost por proyección, ni el ángulo de venta de
"objeto de deseo premium" (vs. solo ahorro operativo). El propio
`10-bitacora-decisiones.md` sección 8 ya lo señala como pendiente de revisión,
específicamente para el documento 1. **Pregunta para Guus:** ¿se actualizan
los `.html` existentes o se construye un octavo documento nuevo para el
ángulo premium, como ya se contempla como pregunta abierta en la bitácora?

### 8.4 Precios de display: dos cifras distintas en la misma carpeta
`2-tasks.md` (líneas 72-83, dentro de la Fase 2 ya cerrada) muestra el fan
holográfico en ~$11K-16K MXN y la OLED transparente en ~$72K MXN. Estas cifras
**no coinciden** con las de `9-dos-caminos-sistema.md`, `10-bitacora-decisiones.md`
sección 3, ni con ninguno de los 7 `.html` (que usan $2,500-3,200 MXN y
$26,000-38,500 MXN respectivamente). La bitácora confirma explícitamente que
las segundas son las vigentes a 8 jul 2026. Se recomienda tratar las cifras de
`2-tasks.md` en esa sección como obsoletas y actualizar el archivo para evitar
confusión futura — pero esa edición no se hizo aquí, solo se señala.

### 8.5 Nombre del producto no propagado a los archivos base
Ver sección 1.1. `2-tasks.md` y los 7 `.html` no contienen el nombre "HOLO AI"
en ningún punto. Se recomienda una pasada de actualización de naming en
`2-tasks.md` (registro de decisión) una vez que Guus confirme que el nombre
está cerrado en definitiva, y una revisión de los `.html` cuando se retomen
para el pivote premium (no antes, para no duplicar trabajo con la revisión
de 8.3).

### 8.6 Confirmación de duplicado
`11-investigacion-holograma-premium.md` y
`12-investigacion-profundidad-sin-marcos.md` son idénticos byte a byte
(103 líneas cada uno, mismo contenido exacto). Ver higiene de archivos en
sección 9 — no se decidió cuál conservar, solo se documenta el hallazgo.

---

## 9. Higiene de archivos — observación, no decisión

- `11-investigacion-holograma-premium.md` y
  `12-investigacion-profundidad-sin-marcos.md`: contenido idéntico. El nombre
  de archivo que el propio prompt de investigación pedía era
  `11-investigación-holograma-proyector.md` (ver `POSIBLE_BASURA_creada.md`,
  última línea) — ninguno de los dos archivos reales coincide exactamente con
  ese nombre solicitado, lo que sugiere una generación duplicada por error de
  proceso, no dos investigaciones distintas. Queda a criterio de Guus
  conservar uno y archivar/eliminar el otro.
- `POSIBLE_BASURA_creada.md`: no es contenido de negocio — es el prompt de
  investigación usado para generar los archivos 11/12. Es metadata de
  proceso, útil solo como registro de cómo se pidió esa investigación.

---

## 10. Glosario técnico mínimo

- **LFPDPPP:** Ley Federal de Protección de Datos Personales en Posesión de
  los Particulares — clasifica datos biométricos como sensibles en México.
- **SCPHA:** Self-Contained Portable HTML Application — un solo archivo
  `.html`, cero dependencias externas, usado como formato estándar de los
  entregables visuales del proyecto.
- **STT / TTS:** Speech-to-Text / Text-to-Speech.
- **ROCm / CUDA:** stacks de cómputo GPU de AMD y NVIDIA respectivamente —
  determinan si el módulo de lip-sync (MuseTalk) corre garantizado (CUDA) o
  requiere validación (ROCm).
- **Pepper's Ghost:** técnica óptica de proyección sobre una lámina angulada
  (acrílico/vidrio) que crea la ilusión de una figura flotante — la base
  técnica real detrás de casi todos los "hologramas" comerciales actuales,
  incluyendo los de gobierno/Fortune 500 documentados en la sección 5.5.
- **ANSI lúmenes:** medida real y estandarizada de brillo de proyector —
  distinta de los "lúmenes LED" de marketing que anuncian los proyectores
  económicos chinos, que son engañosamente más altos que su brillo real.

---

*Fin del índice maestro. Cualquier actualización de este documento debe
seguir el mismo estándar: cada afirmación con su archivo fuente, cada hueco
marcado como tal, cada decisión de negocio presentada como pendiente hasta
que Guus la confirme.*
