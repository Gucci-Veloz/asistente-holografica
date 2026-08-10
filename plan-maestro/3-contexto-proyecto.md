# CONTEXTO DEL PROYECTO
 
## El productoeñ mniimer
Sistema de recepción con Inteligencia Artificial que cubre funciones de una recepcionista humana en espacios de coworking y oficinas corporativas. Opera con un kiosk de pantalla OLED transparente que presenta un avatar de IA conversacional, con reconocimiento facial, control de accesos, gestión de visitantes y comunicación omnicanal.
 
**Diferenciador central:** todo el procesamiento de datos biométricos ocurre **on-premise** (servidor local en cada instalación). Los datos biométricos nunca salen del edificio. Principal argumento de venta, especialmente bajo la Ley Federal de Protección de Datos Personales en Posesión de los Particulares (LFPDPPP) de México.
 
## El cliente / socio piloto
- **David**, dueño del espacio de coworking **"Works"** (Querétaro).
- Se acercó proactivamente a Guus — la demanda está validada antes de construir.
- Acuerdo verbal existente, nada firmado aún. Conversación seria.
- Aporta: el espacio físico, contactos y red comercial en Querétaro.
- Works funcionará como **showroom permanente** para demostrar el producto a futuros clientes.
- Próxima junta: jueves (semana del 28 jun 2026) — presentación de avances a David.
## Infraestructura existente en Works (confirmada)
- **Control de acceso:** marca **ZKTeco**.
- **Software:** ZKAccess 3.5 Security System, versión 3.5.3 Build 0001 y superiores.
- **OS del servidor ZKAccess:** Windows 10 (equipo viejo — a reemplazar por Beelink GTR9 Pro).
- **SDKs disponibles:** Pull SDK V2.0 (DLL de 32 bits, Windows-only: `plcommpro.dll`). Funciones clave del MVP: `ControlDevice` (apertura de puerta), `SetDeviceData` (gestión de usuarios/tarjetas), `GetDeviceData` (logs de acceso).
- **Puntos de acceso:**
  - 1 entrada doble desde la calle — ubicación del kiosk. Con lector ZKTeco.
  - 25 puertas internas con lector ZKTeco — descartadas permanentemente del scope del producto. Se mantiene flujo existente (tarjeta/huella) sin modificación.
- **Aforo:** ~50 miembros activos. ~32 visitantes/mes esporádicos. (Datos a confirmar con David.)
- **Gestión de coworking:** ningún software. Operan con Excel. (Confirmar con David.)
- **Implicación clave:** el MVP NO instala control de accesos desde cero — integra el ZKTeco existente vía Pull SDK en la entrada principal únicamente.
## Arquitectura on-premise — decidida (Fase 2 en curso)
- **Hardware candidato principal:** Beelink GTR9 Pro (AMD Ryzen AI Max+ 395 / 128GB LPDDR5X / 2TB SSD). Precio verificado: ~$1,985–$1,999 USD. Ver `4-research-mercado.md`.
- **OS principal:** Ubuntu (stack de Guus, LLM local, biométrica, avatar, panel de admin).
- **Integración ZKTeco:** VM Windows ligera dentro del Beelink, corriendo solo el SDK (`plcommpro.dll`) y ZKAccess. Ubuntu se comunica con la VM vía API local.
- **Pendiente [INVESTIGAR]:** viabilidad de Wine para eliminar la VM si `plcommpro.dll` corre estable en Ubuntu nativo.
## Naturaleza del proyecto
Híbrido en dos fases simultáneas: (1) encargo casi confirmado con cliente piloto real (Works), y (2) desde el inicio, visión de producto propio escalable. Guus propone la estrategia de escala; David aporta el espacio y la red.
 
## Restricciones confirmadas
- **Presupuesto del piloto:** sin cifra fija. Estructura real: David paga hardware + software + fee de Guus. Costo real se construye en Fase 4 con cotizaciones verificadas en MXN.
- **Hardware de cómputo:** on-premise en cada instalación. Privacidad biométrica como argumento de venta central.
- **Display:** kiosk con pantalla OLED transparente.
- **Tipo de "holográfico":** avatar en kiosk con pantalla OLED transparente (NO proyección volumétrica real).
## Estrategia de IP — a debatir (Fase 5)
Tres rutas a presentar con recomendación: (A) tecnología propia end-to-end; (B) integrador de plataformas existentes; (C) híbrido (integrar en MVP, migrar a propio al escalar). El agente analiza y recomienda; Guus decide.
 
## Perfil de Guus
- Consultor de IA y desarrollador de sistemas agénticos. Solopreneur. Querétaro, México.
- Perfil técnico avanzado: Linux/Ubuntu, desarrollo web, integración de IA, arquitectura agéntica, MCP servers.
- ADHD + alta capacidad cognitiva: baja fricción, comunicación directa sin relleno, captura sobre perfección.
- Stack: Claude Desktop (codirector estratégico), Claude Code (constructor de código), Antigravity IDE (constructor alterno).
- **Este Project es de dirección estratégica y negocio. NO genera código.**
## Objetivo final
Un Plan de Negocio maestro completo y sin datos inventados, del cual se derivará (Fase 8) una presentación profesional para David.