# 10 — Bitácora de Decisiones Recientes
 
> Documento de continuidad. Cualquier sesión nueva debe leer este archivo
> completo antes de responder, junto con los archivos 2 al 9 ya existentes
> y el system prompt del proyecto (que ya incluye las reglas de nombre,
> confidencialidad founder, disciplina SCPHA, numeración paralela y
> protocolo de bitácora — no hace falta repetirlas aquí).
>
> Este documento fue verificado línea por línea contra el contenido REAL
> de los archivos del proyecto el 8 de julio de 2026 — no es una versión
> de memoria de conversación, es evidencia contrastada con `view`.
 
---
 
## 1. LOS 7 DOCUMENTOS HTML — nombres y orden REAL confirmados
 
| # | Archivo | Función narrativa |
|---|---|---|
| 1 | `1-presentacion-works-v2.html` | Gancho emocional — producto, holograma, 3 decisiones interactivas |
| 2 | `2-presentacion-mercado.html` | Visión macro — tamaño de industria, gráficas animadas |
| 3 | `3-oportunidad-regulatoria.html` | Visión macro — reforma laboral 40h como urgencia |
| 4 | `4-presentacion-arquitectura.html` | Credibilidad — anatomía humanoide + hardware (2 caminos + display + accesorios) |
| 5 | `5-dashboard-recepcion-ia.html` | Operación práctica — mockup del panel de administración |
| 6 | `6-calculadora-roi.html` | Prueba personal — ahorro de David como comprador |
| 7 | `7-precio-de-venta.html` | Clímax de sociedad — utilidad del negocio en ventas futuras |
 
**Este es el orden real usado**, confirmado por Guus tras subir los archivos.
Lógica: gancho → visión macro (mercado + regulación) → credibilidad
(arquitectura) → operación (dashboard) → remate financiero doble (ROI +
precio de venta juntos al cierre).
 
**Deprecated:** `presentacion-works.html` (sin numeración, versión previa a v2).
 
---
 
## 2. ESTADO VERIFICADO DE LOS ARCHIVOS .MD (contrastado con `view`, 8 jul 2026)
 
| Archivo | Estado real | Acción |
|---|---|---|
| `2-tasks.md` | Presente | — |
| `3-contexto-proyecto.md` | Vigente | Sin cambios pendientes |
| `4-research-mercado.md` | Vigente, incompleto | Faltan: reforma laboral, factor de carga patronal, hardware de holograma nuevo. Bloque entregado por separado. |
| `5-reglas-decision.md` | **Completo y correcto** | **Verificado con `view` — la Regla de los Dos Caminos SÍ está, íntegra, líneas 35-55. No requiere ningún cambio.** |
| `6-scope-mvp.md` | Vigente | Sin cambios pendientes |
| `7-sdk-zkteco.md` | Vigente | Sin cambios pendientes |
| `8-justificacion-decisiones.md` | Vigente | Sin cambios urgentes |
| `9-dos-caminos-sistema.md` | Vigente, con 2 precios desactualizados | Fan holográfico y OLED transparente. Bloque entregado por separado. |
 
**Nota de proceso:** antes de afirmar el estado de cualquier archivo,
verificar con `view` — no asumir desde memoria de conversación. Este
documento se corrigió una vez por no haber hecho esto a la primera.
 
---
 
## 3. DATOS VERIFICADOS EN ESTA SESIÓN (con fuente)
 
- **Reforma laboral México:** DOF 3 marzo 2026 (constitucional) y 1 mayo
  2026 (LFT). Calendario 48h(2026)→46h(2027)→44h(2028)→42h(2029)→40h(2030).
  Multa: 250-5,000 UMA/trabajador ($29,328-$586,550 MXN). Fuentes: STPS,
  DOF, Senado.
- **Factor de carga patronal:** 25%-50% adicional al salario nominal,
  variable ajustable, no cifra fija. Fuentes: minu.mx, microsip.com.
- **Precios de display vigentes:**
  - Fan holográfico consumo: $2,500-3,200 MXN (Mercado Libre/Amazon)
  - OLED convencional 55": $12,000-15,000 MXN (Coppel/Sanborns)
  - OLED transparente 55": $26,000-38,500 MXN (Made-in-China)
  - Bocinas Steren: $2,190 MXN
- **Servidores:** Beelink GTR9 Pro ~$1,999 USD · NVIDIA DGX Spark ~$4,699 USD
- **Fee de Guus:** desarrollo/instalación $45,000-65,000 MXN, soporte
  mensual $3,000-5,000 MXN
---
 
## 4. CONCEPTOS DE NEGOCIO NOMBRADOS
 
- **COGS vs. Precio de Venta con margen de utilidad** — separados
  explícitamente en el Doc 7.
- **Descreme de precios (Price Skimming)** — framework estratégico
  ajustable, no dato de mercado verificado.
- **Regla de los Dos/Tres Caminos** — ya vive completa en
  `5-reglas-decision.md`, confirmado. Aplica a hardware de cómputo; el
  display sigue su propia disciplina de "siempre 3 opciones con la
  emocional incluida".
---
 
## 5. BUG RESUELTO EN `4-presentacion-arquitectura.html`
 
Bug de alineación de hotspots: `.silhouette-wrapper` sin ancho explícito
causaba que el SVG interno renderizara más angosto que su contenedor.
Fix: `width:240px; margin:0 auto`. Confirmado por captura del usuario.
Se agregó también un 7º órgano ("Memoria") y una sección de Accesorios
y Montaje (cámara, bocinas, gabinete).
 
**Nota técnica para `2-presentacion-mercado.html`:** las gráficas
animadas tuvieron el mismo patrón de causa raíz (cadena de `height:%`
rota en un contenedor flex) — resuelto dando altura explícita al
contenedor directo de la barra. Si se retoca CSS de gráficas en
cualquier documento, revisar que el elemento con `height:var(--h)`
tenga un ancestro con altura EXPLÍCITA, no heredada de flex.
 
---
 
## 6. RESULTADO DE LA PRESENTACIÓN CON DAVID
 
**Positivo.** David solicitó una segunda reunión — el "sí" a continuar
está implícito. David ya no busca convencerse, está en fase de co-diseño.
 
### Requisitos nuevos que dio David:
- No quiere que se vean los marcos/bisel de una pantalla. Ni la OLED
  transparente lo convenció al 100%.
- **La idea del proyector la propuso David**, no Guus.
- Piensa en escalar el hardware físico para vender a **Gobierno** y
  **empresas premium de high-ticket**. "En masa" = escalar la
  comercialización (replicar a más clientes), NO abaratar costo unitario.
- Quiere sensación de "varios avatares" atendiendo simultáneamente para
  corporativos de alto tráfico.
  - **Decisión tomada:** se dirige la venta hacia la **Opción B —
    múltiples unidades físicas idénticas** desplegadas juntas. No se
    descarta Opción A para negociaciones específicas, pero no es la
    ruta que se promueve por defecto. Postura "ahorro" de un cliente:
    se resuelve caso por caso, no bloqueante.
- David dispuesto a **adaptar físicamente la entrada de Works**
  (iluminación, paneles) para que el efecto funcione.
- **Inspiración en AR (no VR)** — por su experiencia con Oculus.
- **Objetivo de negocio:** empresas grandes compitiendo por adquirirlo
  primero. Redefine el segmento: ya no solo "ahorro vs. recepcionista
  humana" (Doc 6/ROI) sino **objeto de deseo premium**, donde para el
  cliente de alto capital la novedad vuelve el costo irrelevante. Este
  ángulo de venta no está construido en ningún documento todavía.
### Conversación de Partnership (mencionada, NO accionable, confidencial):
Guus le dijo a David que la estructura depende de "hasta dónde lo veamos"
— SAS de CV inicial, escalar a SAPI de CV si crece. Marcado como "más
adelante". **No se toca en documentos cliente-facing** — regla ya
codificada en el system prompt (#7).
 
---
 
## 7. INVESTIGACIÓN DEL HOLOGRAMA — hallazgos verificados
 
**Fan de consumo** ($2,500-3,200 MXN): ecosistema cerrado, sin entrada de
video en vivo — limitación intrínseca al hardware.
 
**Fan comercial HDMI/streaming** (HYPERVSN SmartV, línea "Digital
Avatar"): ~$4,000-6,000 USD, solo cotización, resolución 1080×1080.
 
**Pepper's Ghost comercial** (Proto Hologram): $5,900-6,900 USD (mesa)
hasta $29,000-65,000 USD (tamaño real). Ya desplegado en aeropuertos,
bancos, retail con avatares de IA conversacionales reales.
 
**Hallazgo técnico crítico:** latencia movimiento-a-fotón bajo 50-70ms,
arquitectura de tres capas (nube/edge/dispositivo) — más compleja que
el pipeline actual. Comprar hardware caro no resuelve esto solo.
 
**Limitación física:** Pepper's Ghost se debilita con luz ambiental
fuerte — mitigado parcialmente porque David ofreció adaptar la
iluminación de Works.
 
### La ruta viable — nombre técnico correcto:
> **Holograma por Efecto Pepper's Ghost mediante proyección sobre lámina
> acrílica angulada.**
 
Un proyector estándar siempre trae HDMI de fábrica (~$500-3,000 MXN) —
a diferencia del fan, no es un ecosistema cerrado. Permite retransmitir
literalmente la misma señal que va a la OLED, mismo Beelink/cámara, sin
hardware propietario caro.
 
**Refinamiento validado:** si el proyector+acrílico hace el trabajo
visual, la OLED puede reducirse de 55" a solo pantalla táctil (10-15"),
bajando su costo de hardware — pero el costo de "obra" (fabricación
local del acrílico + carcasa + calibración) no baja proporcional, es
trabajo de precisión semi-fijo. El costo se desplaza de hardware a mano
de obra local.
 
**Pendiente:** cotización real local (Querétaro). Prompt de investigación
ya entregado a Guus para ejecutar en herramienta externa. No editar
ningún HTML con esta opción hasta tener el dato real.
 
---
 
## 8. REGLAS VIGENTES (ya codificadas en el system prompt del proyecto)
 
Ya no se repiten aquí en detalle — viven en el system prompt: nombre del
producto, confidencialidad founder, disciplina SCPHA, numeración
paralela, protocolo de bitácora, Fase 4 con método construido.
 
Reglas operativas adicionales de esta bitácora:
1. Antes de afirmar el estado de un archivo del proyecto, verificar con
   `view` — no asumir desde memoria de conversación.
2. Los documentos HTML 1-7 reflejan el modelo de display ANTERIOR al
   pivote premium (sección 6). El Doc 1 en particular sigue mostrando
   Fan/OLED/Transparente como únicas 3 opciones — requiere revisión
   cuando se cierre la investigación de la ruta Pepper's Ghost.
---
 
## 9. PENDIENTES INMEDIATOS
 
- [ ] Agenda de la segunda reunión con David.
- [ ] Resultados del prompt de investigación (Pepper's Ghost local +
      panorama premium/AR) — pendiente de que Guus lo ejecute.
- [ ] Pegar los bloques de actualización en `4-research-mercado.md` y
      `9-dos-caminos-sistema.md` (entregados por separado).
- [ ] Reconsiderar si el pivote premium abre un 8vo documento HTML.
- [ ] Revisar Doc 1 — sus opciones de display pueden estar parcialmente
      desalineadas con lo que David pidió en la última reunión.
- [ ] Fase 6 (Acuerdo con David, roadmap, riesgos) sigue pausada.
 