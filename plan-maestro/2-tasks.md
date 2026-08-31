# TASKS — Plan de Negocio: HOLO AI (Sistema de Recepción con IA on-premise)

> Estado vivo. El agente lo consulta al arrancar cada sesión y propone actualizaciones al cerrar tareas.
> Leyenda: `[ ]` pendiente · `[x]` cerrado · `[~]` en progreso
> Etiquetas: **[DECIDIDO]** · **[INVESTIGAR]** (requiere web_search/SDK) · **[DECISIÓN-GUUS]**

---

## FASE 0 — Cierre de datos faltantes `[x]` CERRADA — 28 jun 2026

- [x] **[DECIDIDO]** Control de accesos en Works: ZKTeco / ZKAccess 3.5.3 Build0001+ / Pull SDK V2.2.0.205+ / Standalone SDK V6.2.5.31+. El MVP integra, no instala accesos.
- [x] **[DECIDIDO]** Puntos de acceso: 1 entrada doble desde la calle (ubicación del kiosk). 25 puertas internas con lector ZKTeco — descartadas permanentemente del scope del producto.
- [x] **[DECIDIDO — pendiente confirmar con David]** Plataforma de gestión: ninguna. Works opera con Excel.
- [x] **[DECIDIDO — pendiente confirmar con David]** Aforo: ~50 miembros activos. Visitantes: ~32/mes esporádicos (no estresan el sistema biométrico).
- [x] **[RESUELTO POR PROTOCOLO]** Precios de venta: el agente propone rangos basados en competidores verificados en Fase 4; Guus decide.
- [x] **[REPLANTEADO]** Presupuesto piloto: placeholder $5K–$15K USD descartado. Estructura real: David paga hardware + software + fee de Guus. Costo real se construye en Fase 4 con cotizaciones verificadas en MXN.

## FASE 1 — Producto y alcance del MVP `[x]` CERRADA — 28 jun 2026

- [x] **[DECIDIDO]** Funciones DENTRO del MVP: 6 módulos (M1–M6). Ver `6-scope-mvp.md`.
- [x] **[DECIDIDO]** Funciones FUERA del MVP: documentadas en `6-scope-mvp.md`.
- [x] **[DECIDIDO]** Diferenciador: privacidad biométrica on-premise.
- [x] **[DECIDIDO]** Display: kiosk OLED transparente.

### FASE 2 — Investigación y selección técnica `[x]` CERRADA — 29 jun 2026

### SDK ZKTeco — decidido
- [x] **[DECIDIDO]** Pull SDK V2.0. DLL 32 bits, Windows-only (`plcommpro.dll`).
  Aislado en VM Windows ligera. Funciones MVP confirmadas:
  `ControlDevice` (OperationID=1, abre puerta), `SetDeviceData` tabla `user`
  (miembros / morosos / tarjetas), `GetDeviceData` tabla `transaction`
  (logs tiempo real, Options="New Record"). Conexión TCP/IP puerto 4370,
  independiente de ZKAccess.
- [~] **[DECISIÓN-GUUS]** Gestión y desbloqueo de tarjetas desde avatar:
  técnicamente posible vía `SetDeviceData`. Pendiente decidir si entra en MVP.
- [ ] **[INVESTIGAR]** Concurrencia TCP: ¿ZKAccess y el bridge service pueden
  conectarse simultáneamente al mismo controlador sin conflicto?
- [ ] **[INVESTIGAR]** Wine para `plcommpro.dll` en Ubuntu — si estable,
  elimina la VM.
- [ ] **[INVESTIGAR]** Latencia real de apertura de puerta vía TCP y
  estabilidad de conexión en condiciones de Works.

### Camino 1 — Stack AMD (Beelink GTR9 Pro)
- [x] **[DECIDIDO]** Hardware: Beelink GTR9 Pro (AMD Ryzen AI Max+ 395 /
  128GB LPDDR5X / 2TB SSD) — ~$1,985–1,999 USD. Ver `4-research-mercado.md`.
- [x] **[DECIDIDO]** LLM: Qwen 3.6-27B
  (lanzamiento: 22 abr 2026 / Apache 2.0 / Ollama en Ubuntu / ~16GB en 4-bit)
- [x] **[DECIDIDO]** STT: Whisper Large v3 Turbo vía faster-whisper
  (oct 2024 / MIT / 50–300ms local / 99 idiomas)
- [x] **[DECIDIDO]** TTS: Chatterbox-Turbo, Resemble AI
  (26 mar 2026 / MIT / voice cloning / español nativo / 9 idiomas)
- [x] **[DECIDIDO]** Reconocimiento facial: DeepFace (MIT) + RetinaFace
  (detector) + FaceNet512 (Apache 2.0) + Silent-Face-Anti-Spoofing (liveness).
  $0 licencias. 97.4% accuracy en condiciones controladas.
- [x] **[DECIDIDO]** Cámara: Logitech BRIO 4K (~$199 USD).
  USB, UVC nativo en Ubuntu, WDR RightLight 3 hardware (backlit). Ver `8-justificacion-decisiones.md`.
- [x] **[DECIDIDO]** Avatar / lip-sync: ai-avatar-system (PunithVT/GitHub,
  MIT, may 2026) + MuseTalk v1.5 (Tencent, MIT, mar 2025). Pipeline integrado:
  Whisper → Qwen (Ollama) → Chatterbox → MuseTalk. Manos libres, barge-in,
  100% local.
  [ ] **[INVESTIGAR]** Rendimiento MuseTalk en AMD Radeon 890M vía ROCm.
  Si insuficiente: evaluar Wav2Lip (alternativa compatible CPU/AMD, open source).

### Camino 2 — Stack NVIDIA
- [ ] **[INVESTIGAR]** + **[DECISIÓN-GUUS]** Hardware: servidor/workstation
  con GPU NVIDIA dedicada. Cotizar modelo, precio en MXN, y diferencial vs
  Beelink GTR9 Pro. Aplica si MuseTalk en AMD no alcanza rendimiento aceptable
  para el piloto.
- Nota: mismo stack de software (LLM, STT, TTS, reconocimiento facial).
  Ventaja principal: MuseTalk en CUDA a 30fps+ garantizado.

### Display — DECISIÓN-DAVID (presentar las 3 opciones)
- [x] **[DOCUMENTADO — precios corregidos 8 jul 2026]** Tres opciones verificadas en precio MXN:

  | Opción | Precio aprox. MXN | Lo que David compra |
  |---|---|---|
  | Fan holográfico LED | ~$2,500–3,200 MXN (+ bocinas $2,190 MXN si aplica) | El "holograma" que lo trajo. Avatar en loop pre-renderizado, no tiempo real. Requiere pantalla táctil adicional. |
  | OLED convencional 55" (LG/Samsung) | ~$12,000–15,000 MXN (Coppel/Sanborns) | Avatar perfecto, táctil nativo, funcionalidad completa. Mejor precio/utilidad. |
  | OLED transparente 55" | ~$26,000–38,500 MXN (Made-in-China, verificado) | Avatar flotante con fondo oscuro. Impacto máximo en showroom. |

  Corrección de higiene de datos: las cifras anteriores (~$11K–16K / ~$72K MXN)
  quedaron desactualizadas frente a `9-dos-caminos-sistema.md` y
  `10-bitacora-decisiones.md`. Se reemplazan por las vigentes.

  Recomendación para presentación: iniciar con fan holográfico (lo que lo
  entusiasmó), mostrar OLED convencional como la que cuida su bolsillo.
  OLED transparente como aspiracional. David elige.

### WhatsApp Business API — DECISIÓN-DAVID (presentar las 2 opciones)
- [x] **[DOCUMENTADO]** Dos opciones verificadas:

  | Opción | Costo mensual Works | Diferenciador |
  |---|---|---|
  | Kapso (MVP interno) | ~$55–90 MXN | Free tier 2K msgs, MCP N, lanza Dic 2025 |
  | Twilio (rec. a David) | ~$145–215 MXN | 10+ años, SDK Python, soporte 24/7 |

  Diferencia: ~$90–125 MXN/mes. David elige — predicción: Twilio.

--------------

## FASE 3 — Arquitectura técnica `[ ]`

- [ ] Diagrama
- [ ] Validar latencia objetivo de conversación (medir/investigar, no estimar).

## FASE 4 — Modelo de negocio y economía `[ ]`

- [ ] **[INVESTIGAR]** Costos reales por instalación en MXN (suma de cotizaciones de Fase 2).
- [ ] **[DECISIÓN-GUUS]** Estructura de ingresos (instalación + licencia mensual + hardware).
- [ ] **[DECISIÓN-GUUS]** Precios de venta finales (el agente propone rango con base en competidores verificados).
- [ ] Economía unitaria con números reales.

## FASE 5 — Estrategia de propiedad intelectual `[ ]`

- [ ] Análisis de las 3 rutas (propia / integrador / híbrida) con datos reales.
- [ ] **[DECISIÓN-GUUS]** Ruta de IP elegida.

## FASE 6 — Acuerdo con David, roadmap y riesgos `[ ]`

- [ ] Estructura formal del acuerdo piloto (aportaciones de cada parte).
- [x] **[DECIDIDO]** Acuerdo escrito antes de instalar nada.
- [x] **[DECIDIDO]** Cumplimiento LFPDPPP para datos biométricos.
- [ ] Roadmap por fases.
- [ ] Matriz de riesgos y mitigación.

## FASE 7 — Ensamblaje del Plan maestro `[ ]`

- [ ] Unir todas las fases en documento final formato entregable.
- [ ] Revisión: cero datos sin fuente.

## FASE 8 — Presentación para David `[ ]` (posterior)

- [ ] **[DECISIÓN-GUUS]** Formato visual de la presentación.
- [ ] Derivar presentación del plan maestro.

---

## DECISIONES YA TOMADAS (registro)

- Producto: **HOLO AI** — sistema de recepción con IA on-premise para coworking/corporativo.
- Piloto: Works de David en Querétaro (se acercó proactivamente; será showroom permanente).
- Naturaleza: híbrido — encargo piloto + producto propio escalable.
- Display: kiosk OLED transparente (NO proyección volumétrica).
- Diferenciador: privacidad biométrica on-premise (LFPDPPP).
- Control de accesos: integración Pull SDK ZKTeco v2.0 — DLL 32 bits Windows-only, aislada en VM.
- Infraestructura Works: 1 entrada principal (kiosk aquí). 25 puertas internas — descartadas permanentemente del scope del producto.
- Aforo Works: ~50 miembros activos, ~32 visitantes/mes esporádicos. Confirmar con David.
- Gestión Works: sin software de coworking. Opera con Excel. Confirmar con David.
- OS ZKAccess actual: Windows 10 (equipo viejo a reemplazar por Beelink GTR9 Pro).
- Arquitectura on-premise: Ubuntu principal + VM Windows ligera para SDK/ZKAccess en Beelink GTR9 Pro.
- Hardware candidato principal: Beelink GTR9 Pro (~$1,985–$1,999 USD). Documentado en `4-research-mercado.md`.
- Estructura acuerdo Works: Guus = desarrollo; David = hardware + software + fee de Guus.
- Scope MVP: 6 módulos (M1–M6), 6 flujos conversacionales (F1–F6). Ver `6-scope-mvp.md`.
- Nombre del producto: **HOLO AI** — decidido.
- Stack de voz: Qwen 3.6-27B / Whisper Large v3 Turbo / Chatterbox-Turbo.
  100% on-premise, licencias MIT/Apache 2.0, español nativo.
- Reconocimiento facial: DeepFace + FaceNet512 + Silent-Face-Anti-Spoofing.
  $0 licencias, uso comercial libre.
- Cámara: Logitech BRIO 4K (~$199 USD). WDR hardware para entorno backlit.
- Avatar / lip-sync: ai-avatar-system + MuseTalk v1.5. MIT. On-premise total.
- Display: tres opciones documentadas para presentación con David.
  Pendiente decisión de David.
- WhatsApp API: Kapso (MVP) / Twilio (recomendada a David). Pendiente decisión.
- Dos caminos de sistema: AMD (Beelink GTR9 Pro) y NVIDIA alternativo.
  David elige camino en presentación.
- Posicionamiento premium: pivote confirmado tras segunda reunión con David
  (padre y hermano presentes) — de "ahorro vs. recepcionista humana" hacia
  "objeto de deseo premium" para Gobierno y empresas de alto ticket.
- Escalamiento por defecto: múltiples unidades físicas idénticas por sitio
  ("Opción B"), no una sola unidad compleja. Configuración alternativa
  ligada a ahorro ("Opción A") disponible para negociaciones puntuales —
  detalle sin especificar todavía.
- Display: David rechaza biseles/marcos visibles de pantalla; propuso él
  mismo la ruta de proyección Pepper's Ghost como 4ta opción — en
  investigación, sin cotización local cerrada.

---

## HITO — Presentación con David completada
- [x] Presentación realizada. Resultado: positivo. David solicitó segunda
      reunión para seguir avanzando — SÍ implícito a continuar el proyecto.
- [x] **Segunda reunión realizada** — asistieron también el padre y el
      hermano de David. Introduce dinámicas relacionales/estratégicas
      nuevas, documentadas por Guus con etiquetado
      ANTES/DURANTE/DESPUÉS × HECHO/LECTURA-GUUS (sin archivo propio
      todavía en esta carpeta).
- [x] **[DECIDIDO — pivote premium]** Requisitos y dirección nuevos que dio
      David en la segunda reunión:
  - No quiere marcos/bisel de pantalla visibles — ni la OLED transparente lo
    convenció al 100%.
  - La idea del proyector (Pepper's Ghost) la propuso David, no Guus.
  - Dirección de escalamiento: Gobierno y empresas premium de high-ticket.
    "En masa" = replicar comercialización, NO abaratar costo unitario.
  - Venta dirigida por defecto a múltiples unidades físicas idénticas
    desplegadas juntas ("Opción B"). No se descarta una configuración
    distinta ligada a ahorro ("Opción A") para negociaciones puntuales.
  - David dispuesto a adaptar físicamente la entrada (iluminación, paneles)
    para el efecto Pepper's Ghost.
  - Inspiración explícita en AR (no VR), por experiencia previa con Oculus.
  - Objetivo de negocio: empresas grandes compitiendo por adquirirlo
    primero — redefine el segmento hacia "objeto de deseo premium", no solo
    ahorro vs. recepcionista humana. Ángulo de venta aún no construido en
    ningún documento.
- [x] **[INVESTIGAR]** Cotización local: lámina acrílica + proyector +
      carcasa para Efecto Pepper's Ghost (4ta opción de display). No editar
      HTML hasta tener precio real.
- [ ] **[PENDIENTE]** Actualizar los 7 documentos HTML para reflejar el
      pivote premium — o evaluar un 8vo documento HTML dedicado al ángulo
      premium/gobierno.
- [ ] **[PENDIENTE — corrección urgente]** `2-presentacion-mercado.html`
      contiene overclaiming en tiempo presente ("el sistema opera... hoy",
      "miembros reales, todos los días"). Corregir a lenguaje prospectivo
      antes de reutilizar este documento.
- [ ] **[PENDIENTE]** Llenar `13-bitacora-relacional-david.md` con el detalle
      de la segunda junta (Don Fernando y hermano de David presentes).

## FASE 6 — Acuerdo con David, roadmap y riesgos `[ ]`
- Reactivada — la segunda reunión ya aportó insumos (dirección de
  escalamiento, objetivo de negocio). Sigue pendiente estructurar acuerdo
  formal, roadmap por fases y matriz de riesgos con estos elementos.
