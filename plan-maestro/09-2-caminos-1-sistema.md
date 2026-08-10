# LOS DOS CAMINOS DEL SISTEMA — De 0 a 100
 
> Documento de arquitectura y costo — insumo directo para la presentación con David.
> Datos verificados con web_search a junio 2026. Precios de hardware en USD (fuente original);
> conversión a MXN aproximada, sujeta a cotización formal y tipo de cambio del día.
> Los precios de display están verificados en MXN (Coppel / Sanborns).
 
---
 
## La disyuntiva en una línea
 
El sistema es **idéntico en software y funcionalidad** en ambos caminos. Lo único que
cambia es el **servidor**. La decisión de David es una sola:
 
> **Camino 1 — AMD:** máxima economía. Un signo de interrogación técnico en el lip-sync del avatar (se valida).
> **Camino 2 — NVIDIA:** ~$2,700 USD más, cero riesgo técnico en el avatar. CUDA nativo.
 
Todo lo demás —reconocimiento facial, voz, cerebro de IA, control de puerta, WhatsApp,
privacidad on-premise— es exactamente lo mismo en los dos.
 
---
 
## BASE COMÚN — idéntica en ambos caminos
 
Esto no cambia elija David el camino que elija. Es la columna vertebral del producto.
 
### Software — costo de licencias: $0
 
| Componente | Tecnología | Licencia | Función |
|---|---|---|---|
| Cerebro (LLM) | Qwen 3.6-27B vía Ollama | Apache 2.0 | Conversación, entiende y responde |
| Oído (STT) | Whisper Large v3 Turbo (faster-whisper) | MIT | Transcribe la voz del visitante |
| Voz (TTS) | Chatterbox-Turbo (Resemble AI) | MIT | Voz del avatar, clonable, español nativo |
| Reconocimiento facial | DeepFace + RetinaFace + FaceNet512 | MIT / Apache 2.0 | Identifica al miembro |
| Anti-spoofing | Silent-Face-Anti-Spoofing (MiniVision) | Open source | Bloquea intentos con foto |
| Avatar / lip-sync | ai-avatar-system + MuseTalk v1.5 | MIT | Rostro que habla sincronizado |
 
**El argumento de venta:** todo corre dentro del edificio. Cero costo por uso, cero datos
de miembros hacia la nube, cero dependencia de internet para operar. Esto es lo que ningún
competidor ofrece con soporte local en México.
 
### Hardware común
 
| Componente | Modelo | Costo aprox. |
|---|---|---|
| Cámara de reconocimiento | Logitech BRIO 4K | ~$199 USD |
 
Justificación de la cámara: la entrada de Works es un entorno *backlit* (luz de calle por
la puerta de vidrio). La BRIO tiene WDR RightLight 3 por hardware, que compensa el contraluz.
No es un lujo — es el requisito para que el reconocimiento funcione en esa entrada.
 
### Comunicación — WhatsApp (decisión de David)
 
| Opción | Costo mensual Works | Perfil |
|---|---|---|
| Kapso | ~$55–90 MXN | Free tier 2,000 msgs/mes, MCP nativo. Plataforma joven. |
| Twilio | ~$145–215 MXN | 10+ años, SDK Python, soporte 24/7. Mayor estabilidad. |
 
Diferencia real: ~$90–125 MXN/mes. Se presentan ambas; David elige.
 
### Display (decisión de David) — el holograma siempre está en la mesa
 
| Opción | Precio aprox. MXN | Qué compra David |
|---|---|---|
| Fan holográfico LED | ~$2.5K–3.2K (Mercado Libre / Amazon, consumo) | El "holograma" que lo trajo. Avatar en loop pre-renderizado, **no** en tiempo real. Requiere pantalla táctil adicional (costo pendiente de cotizar). |
| OLED convencional 55" | ~$12K–15K (Coppel / Sanborns) | Avatar en tiempo real, táctil nativo, funcionalidad completa. Mejor precio/utilidad. |
| OLED transparente 55" | ~$26K–38.5K (Made-in-China, verificado) | Avatar flotante sobre fondo oscuro. Máximo impacto de showroom. |
 
[!][Nota estratégica] con el precio corregido, el fan holográfico sigue siendo el hardware más barato de los tres — pero sigue sin resolver tiempo real ni interacción táctil propia. El argumento ya no es "termina siendo más caro", es "es barato pero limitado en función": el OLED convencional sigue siendo la mejor relación precio/función completa.
 
**Actualización pendiente:** existe una cuarta ruta en investigación — Holograma por Efecto Pepper's Ghost mediante proyección sobre lámina acrílica angulada (proyector + acrílico local, misma arquitectura AMD/NVIDIA, sin hardware propietario). No se agrega a la tabla hasta tener cotización local real — ver `10-bitacora-decisiones.md` sección 6.
 
---
 
## CAMINO 1 — Stack AMD (Beelink GTR9 Pro)
 
**La apuesta:** máxima economía sobre el hardware que ya se venía manejando.
 
### Servidor
| Especificación | Detalle |
|---|---|
| Modelo | Beelink GTR9 Pro |
| Procesador | AMD Ryzen AI Max+ 395 |
| Memoria | 128 GB LPDDR5X unificada |
| Almacenamiento | 2 TB SSD |
| GPU | AMD Radeon 890M integrada |
| **Costo** | **~$1,985–1,999 USD** |
 
### Cómo corre el sistema completo
- **Ubuntu 24** como sistema principal: LLM, STT, TTS, reconocimiento facial, avatar, panel admin.
- **VM Windows ligera** (8 GB de los 128 GB): solo el SDK de ZKTeco (`plcommpro.dll`) y ZKAccess.
  Se comunica con Ubuntu vía puente local. El 94% del sistema en Ubuntu, el 6% en la VM.
- Conexión al controlador de puerta por TCP/IP puerto 4370.
### El único signo de interrogación
MuseTalk (el lip-sync del avatar) está optimizado para CUDA (NVIDIA). Sobre la GPU AMD
corre vía ROCm. **Requiere validación en hardware real**: si el rendimiento no alcanza,
se cae a un motor de lip-sync alternativo compatible con AMD/CPU (Wav2Lip). Esto se prueba
antes de instalar en Works — no se estima, se mide.
 
### Costo total Camino 1 (sin display, en USD)
| Concepto | Costo |
|---|---|
| Servidor Beelink GTR9 Pro | ~$1,985–1,999 USD |
| Cámara BRIO 4K | ~$199 USD |
| Software (licencias) | $0 |
| **Subtotal hardware de cómputo** | **~$2,184–2,198 USD** |
 
---
 
## CAMINO 2 — Stack NVIDIA (DGX Spark)
 
**La apuesta:** cero riesgo técnico en el avatar. CUDA nativo, Ollama preinstalado.
 
### Servidor
| Especificación | Detalle |
|---|---|
| Modelo | NVIDIA DGX Spark (GB10 Grace Blackwell) |
| Procesador | 20-core ARM + GPU Blackwell (mismo die, NVLink-C2C) |
| Memoria | 128 GB LPDDR5X unificada |
| Cómputo | 1 PetaFLOP FP4 |
| Ecosistema | CUDA nativo, Ollama preinstalado, Linux |
| **Costo** | **~$3,999 USD (lanzamiento) → ~$4,699 USD (actual, feb 2026)** |
 
Fuente: el precio subió de $3,999 a $4,699 en febrero 2026 por escasez de memoria LPDDR5X.
Verificado a junio 2026.
 
### Cómo corre el sistema completo
- Mismo software exacto que el Camino 1.
- Ventaja decisiva: MuseTalk corre en CUDA a pleno rendimiento (30fps+), sin el signo de
  interrogación del Camino 1. El avatar habla fluido sin validación adicional.
- La arquitectura ZKTeco (VM Windows o Wine) aplica igual.
### Costo total Camino 2 (sin display, en USD)
| Concepto | Costo |
|---|---|
| Servidor DGX Spark | ~$4,699 USD |
| Cámara BRIO 4K | ~$199 USD |
| Software (licencias) | $0 |
| **Subtotal hardware de cómputo** | **~$4,898 USD** |
 
### Nota — alternativa NVIDIA de mayor velocidad
Existe una workstation con RTX 5090 (32 GB GDDR7, 1.8 TB/s de ancho de banda) que supera al
DGX Spark en velocidad pura de inferencia para modelos que caben en 32 GB — y Qwen 27B en 4-bit
(~16 GB) cabe. Un build completo ronda ~$4,500 USD. Se documenta por transparencia, pero el
Camino 2 canónico usa el DGX Spark por ser el espejo exacto del Beelink (mini-PC, 128 GB
unificados, Ollama listo), lo que hace la comparación limpia. Si David prioriza velocidad
de inferencia sobre capacidad de modelo, la RTX 5090 se cotiza aparte como su propia variante.
 
---
 
## COMPARATIVA LADO A LADO
 
| Dimensión | Camino 1 — AMD (Beelink) | Camino 2 — NVIDIA (DGX Spark) |
|---|---|---|
| Servidor | ~$1,985–1,999 USD | ~$4,699 USD |
| Diferencia | — | **+~$2,700 USD** |
| Memoria | 128 GB unificada | 128 GB unificada |
| Software | Idéntico, $0 | Idéntico, $0 |
| Reconocimiento facial | Igual | Igual |
| Voz / LLM | Igual | Igual |
| Lip-sync del avatar | Vía ROCm — **a validar** | CUDA nativo — **garantizado** |
| Ecosistema IA | Ollama en Ubuntu | Ollama preinstalado, CUDA |
| Perfil | Máxima economía | Máxima tranquilidad técnica |
| Riesgo técnico | Medio (avatar) | Bajo |
 
**La pregunta para David, limpia:**
¿Ahorrar ~$2,700 USD asumiendo que el lip-sync en AMD se valida y ajusta (Camino 1),
o pagar ~$2,700 USD más por CUDA nativo y cero riesgo en el avatar (Camino 2)?
 
No hay trampa, no hay componentes sueltos, no hay add-ons. Dos servidores completos,
mismo software, distinto perfil de precio y riesgo.
 
---
 
## COMPONENTES EVALUADOS Y DESCARTADOS
 
Se documentan para mostrar el rigor del proceso: cada elección venció a alternativas reales.
 
| Componente | Descartado | Por qué |
|---|---|---|
| LLM | Qwen 3.7 | Propietario / solo por API — viola on-premise |
| STT | distil-whisper | Solo inglés — Works necesita español |
| TTS | Coqui XTTS v2 | Licencia CPML no comercial + empresa cerrada |
| TTS | Kokoro | Sin clonación de voz |
| Reconocimiento facial | InsightFace / buffalo_l | Modelo requiere licencia comercial de pago (costo incierto) |
| Avatar | RAVATAR | Cloud-dependent — viola el diferenciador de privacidad |
| Display (como avatar real) | Fan holográfico solo | Solo reproduce loop, no avatar en tiempo real |
 
---
 
## RESUMEN PARA LA PRESENTACIÓN
 
1. **Base común** — se muestra primero: el sistema completo, el software $0, la privacidad
   on-premise. Esto es lo que hace único al producto.
2. **Los dos caminos** — se presenta como elección de David, no como recomendación impuesta.
3. **El display** — se presenta con el holograma incluido (lo que lo trajo), y se deja ver
   por qué el OLED convencional cuida su bolsillo.
4. **Los descartados** — se mencionan para demostrar que detrás de cada pieza hubo análisis.
El costo de cómputo total va de **~$2,184 USD (Camino 1)** a **~$4,898 USD (Camino 2)**,
más el display que David elija. Los precios finales en MXN se cierran con cotización formal.
 