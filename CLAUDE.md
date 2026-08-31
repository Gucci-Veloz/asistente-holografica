# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Qué es este repositorio

Este repositorio **no es una base de código**. Es el repositorio de estrategia y
entregables del proyecto de negocio **HOLO AI** (sistema de recepción con IA
on-premise: avatar conversacional, reconocimiento facial, control de accesos y
notificaciones WhatsApp para coworkings y oficinas). No hay build, ni linter,
ni test runner, ni dependencias que instalar — los `.html` de `entregables/`
se abren directamente en el navegador y los `.md` de `plan-maestro/` se leen
como documentación.

Regla explícita del propio proyecto (`3-contexto-proyecto.md`): el rol de este
espacio es **dirección estratégica y de negocio — no genera código de
producción**. No conviertas tareas de este repo en tareas de ingeniería de
software salvo que el usuario lo pida explícitamente para otro proyecto.

## Leer primero: el índice maestro

`plan-maestro/00-indice-maestro-contexto.md` es el documento puente que
consolida el estado real del proyecto citando siempre el archivo fuente. Es
más reciente y más confiable que releer todos los `.md` sueltos. Antes de
generar cualquier entregable nuevo o afirmar el estado del proyecto:

1. Lee su sección 1 (reglas no negociables) — resumidas abajo.
2. Lee su sección 8 (discrepancias sin resolver) — hay overclaiming activo y
   desfases de sincronización entre archivos que **no se deben asumir como
   corregidos**.
3. Usa su sección 3 (mapa de archivos) como punto de partida, pero verifica
   contra el filesystem real antes de citar un nombre de archivo — ver
   "Discrepancia conocida" más abajo, ese mapa ya está desactualizado en un
   punto concreto.

`2-tasks.md` es la fuente de verdad de *progreso por fase*. **Ya fue
actualizado** (tras la creación de este CLAUDE.md) para incorporar el hito de
la segunda reunión con David, el pivote premium, el nombre "HOLO AI"
propagado y los precios de display corregidos — es decir, resolvió en el
propio archivo varias de las discrepancias que `00-indice-maestro-contexto.md`
sección 8 señala (8.1, 8.4, 8.5). **Esa sección 8 del índice puede estar ya
desactualizada respecto al `2-tasks.md` actual** — verifica el estado real de
`2-tasks.md` en vez de asumir que las discrepancias del índice siguen
vigentes. Sí sigue vigente 8.2 (overclaiming en `2-presentacion-mercado.html`,
ver más abajo) y 8.3 (los 7 `.html` sin reflejar el pivote premium).

## Reglas no negociables (violarlas por desconocimiento es el error más caro)

1. **Nombre del producto: HOLO AI.** El coworking piloto se llama **Works**,
   propiedad de la familia de David (cliente/socio piloto). "Works" es el
   nombre del *espacio físico donde ocurre el piloto*, no del producto —
   nunca debe usarse como marca comercial genérica en un entregable nuevo
   dirigido a otro cliente. `1-presentacion-works-v2.html` usa el naming de
   Works deliberadamente porque es la presentación específica de ese piloto;
   eso es correcto solo ahí, no es un patrón a copiar.
2. **Confidencialidad de estructura societaria y de dinámica relacional.**
   Todo lo relativo a los vehículos corporativos de Guus (SAS de CV,
   escalamiento a SAPI de CV, participación en otras SAPIs, rondas de
   capital) es estrictamente confidencial. Nunca debe aparecer en ningún
   documento que pueda llegar a David, a Works, o a cualquier tercero. Mismo
   nivel de confidencialidad aplica a `13-bitacora-relacional-socios.md`
   (lecturas de Guus sobre la dinámica familiar de David/Works) — es
   explícitamente "uso interno de Guus, nunca cliente-facing", ver detalle
   abajo.
3. **Anti-invención (5 reglas de oro):**
   - Ningún modelo, precio, latencia, hardware o cifra de mercado se afirma
     sin fuente verificada (búsqueda web en tiempo real, o ya verificada en
     `4-research-mercado.md`). El conocimiento base del modelo no basta —
     este proyecto cambia con datos de mercado que pueden haberse movido
     desde el entrenamiento.
   - Si un dato no se sabe con certeza, se dice explícitamente — nunca se
     rellena con una estimación no marcada como tal.
   - Donde hay opciones (hardware, nombres, precios de venta, proveedor de
     WhatsApp), se presenta comparativa — **Guus o David deciden, nunca el
     agente asume.**
   - No se propone naming genérico ni combinaciones baratas de siglas
     (lección ya registrada en `5-reglas-decision.md`); los nombres deben
     ser evocadores y presentarse siempre como opciones.
   - No se avanza de fase sin cerrar la anterior, salvo autorización
     explícita.
4. **Regla de los Dos Caminos** (`5-reglas-decision.md`): cualquier
   componente con impacto económico que David vea se documenta como dos
   caminos completos de sistema — nunca como add-ons sueltos:
   - **Camino 1 — AMD (Beelink GTR9 Pro):** Ryzen AI Max+ 395, 128GB LPDDR5X
     unificada, ~$1,985–1,999 USD. Punto abierto: MuseTalk (lip-sync) corre
     vía ROCm en AMD y requiere validación en hardware real; si no rinde, cae
     a Wav2Lip.
   - **Camino 2 — NVIDIA (DGX Spark):** GB10 Grace Blackwell, CUDA nativo,
     ~$3,999→~$4,699 USD. MuseTalk garantizado a 30fps+.
   - Nunca mezclar piezas de caminos distintos en una sola propuesta. Nunca
     recomendar un camino sin costo verificado de ambos. El agente presenta;
     David elige; Guus cierra la venta.

## Discrepancia conocida entre el índice maestro y el filesystem real

`00-indice-maestro-contexto.md` sección 3.2 describe `entregables/` con un
mapa que **ya no coincide con los archivos reales de la carpeta**: cita un
`3-oportunidad-regulatoria.html` que no existe, y ubica
`4-presentacion-arquitectura.html` en la posición 4. En el filesystem actual,
la presentación de arquitectura es `3-presentacion-arquitectura.html`, y
existen **dos** archivos de dashboard (`4-dashboard-recepcion-ia.html` y
`5-dashboard-recepcion-ia.html`, mismo `<title>`, probablemente dos
versiones/iteraciones del mismo panel — no se ha determinado cuál es la
vigente). Antes de citar o editar un `.html` por número, confirma su
contenido real (`<title>`) en vez de confiar ciegamente en la tabla del
índice.

También nota: `plan-maestro/7-sdk-zkteco.md` existe pero está vacío (0
líneas) pese a que el índice lo describe como "documentación técnica cruda
del SDK ZKTeco" — el contenido referenciado en `2-tasks.md`/`8-...md` sobre
funciones del SDK vive en esos otros archivos, no ahí.

## Estructura de archivos

Dos series independientes de numeración, sin relación entre sí:

### `plan-maestro/` — estrategia y referencia (`.md`)

| Archivo | Contenido |
|---|---|
| `00-indice-maestro-contexto.md` | Documento puente/índice — leer primero |
| `2-tasks.md` | Progreso por fase (0–8), decisiones, pendientes — actualizado con el hito de la 2ª reunión y el pivote premium; ver nota arriba sobre discrepancias del índice ya resueltas aquí |
| `3-contexto-proyecto.md` | Producto, cliente piloto (David/Works), infraestructura ZKTeco existente, perfil de Guus |
| `4-research-mercado.md` | Datos de mercado y hardware con fuente y fecha |
| `5-reglas-decision.md` | Matriz de autorización y Regla de los Dos Caminos |
| `6-scope-mvp.md` | Módulos M1–M6 del MVP, flujos conversacionales F1–F6, fuera de scope |
| `7-sdk-zkteco.md` | Vacío actualmente — ver nota arriba |
| `08-justificacion-decisiones.md` | Por qué se eligió cada pieza técnica, formato pregunta-de-David/respuesta |
| `09-2-caminos-1-sistema.md` | Comparativa completa Camino 1 vs Camino 2, display, componentes descartados |
| `10-bitacora-decisiones.md` | Bitácora narrativa más reciente y completa del estado del proyecto |
| `11-investigacion-holograma-premium.md`, `12-investigacion-profundidad-sin-marcos.md` | Contenido idéntico byte a byte (duplicado confirmado, no resuelto cuál conservar) — investigación de hardware de holograma premium (Pepper's Ghost, Proto, ARHT, Looking Glass) |
| `13-bitacora-relacional-socios.md` | **CONFIDENCIAL — uso interno de Guus, nunca cliente-facing.** Capa relacional (quién estuvo, dinámica, lecturas de Guus) de la segunda junta con David/Works — complementa, sin repetir, los hechos técnicos ya en `10-bitacora-decisiones.md`. Usa etiquetado ANTES/DURANTE/DESPUÉS × `[HECHO]`/`[LECTURA-GUUS]`; una `[LECTURA-GUUS]` nunca se trata como hecho confirmado, y lo desconocido se marca `[PENDIENTE DE CONFIRMAR]`, nunca se rellena. Si Guus narra esto de forma no lineal en una sesión futura, captura primero y clasifica después, sin inventar fechas/nombres/roles no dichos explícitamente. Nota: `2-tasks.md` referencia este archivo como `13-bitacora-relacional-david.md` — el nombre real en disco es `13-bitacora-relacional-socios.md`. |

### `entregables/` — presentaciones cliente-facing, formato SCPHA (`.html`)

SCPHA = *Self-Contained Portable HTML Application*: un solo archivo, cero
dependencias externas (sin CDN, sin build), paleta de tokens CSS en
`:root` (`--bg`, `--gold`, `--cyan`, `--green`, `--coral`...), tipografía
serif (Georgia/Times) en títulos y sans-serif de sistema en el resto,
tema oscuro. Al crear o editar un entregable nuevo, sigue este mismo
estándar de un solo archivo autocontenido y reutiliza la paleta de tokens ya
usada en los existentes en vez de introducir una nueva.

Orden narrativo previsto (gancho → visión macro → credibilidad técnica →
operación → remate financiero) — verifica el `<title>` de cada archivo antes
de asumir su rol, ver discrepancia arriba:
`1-presentacion-works-v2.html` (gancho, usa naming de Works — ver regla 1) ·
`2-presentacion-mercado.html` (**contiene overclaiming en tiempo presente sin
corregir, ver `00-indice...` sección 8.2 — no reutilizar sin corregir primero**) ·
`3-presentacion-arquitectura.html` · `4-dashboard-recepcion-ia.html` ·
`5-dashboard-recepcion-ia.html` (posible duplicado/iteración de 4, sin
confirmar cuál es vigente) · `6-calculadora-roi.html` (cifras son inputs
ajustables, sin datos reales precargados de Works) ·
`7-precio-de-venta.html` (cifras de ejemplo del framework de descreme de
precios, explícitamente no cerradas como decisión de precio).

Ninguno de los 7 refleja todavía el pivote hacia Gobierno/empresas premium
narrado en `10-bitacora-decisiones.md` (rechazo de biseles visibles, ruta de
proyección Pepper's Ghost, ángulo de "objeto de deseo premium").
