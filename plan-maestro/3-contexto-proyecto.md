# CONTEXTO DEL PROYECTO — HOLO AI

## El producto
**HOLO AI** es un sistema de recepción con Inteligencia Artificial que cubre las funciones de una recepcionista humana mediante presencia física en un punto de acceso: reconocimiento facial, conversación por voz con un avatar, control de accesos, gestión de visitantes y comunicación omnicanal. Opera con un kiosk de pantalla OLED transparente que presenta un avatar de IA conversacional.

**Diferenciador central:** todo el procesamiento de datos biométricos ocurre **on-premise** (servidor local en cada instalación). Los datos biométricos nunca salen del edificio. Principal argumento de venta, especialmente bajo la Ley Federal de Protección de Datos Personales en Posesión de los Particulares (LFPDPPP) de México.

## Visión y mercado objetivo

**Fase actual — validación en piloto.** HOLO AI está en fase de "Piloto en desarrollo": el stack técnico está definido, hubo una presentación completa a David con resultado positivo, pero **nada está instalado ni operando todavía**. El piloto ocurre en un espacio de coworking (ver "El cliente / socio piloto"), que sirve como validación de campo y showroom permanente — no como el mercado que define al producto.

**Tesis de escalamiento — hacia dónde apunta HOLO AI.** Tras la segunda reunión con David (con su padre y hermano presentes), el proyecto adoptó un pivote de posicionamiento: de "ahorro vs. recepcionista humana" hacia **objeto de deseo premium para Gobierno y empresas de alto ticket**, donde para un cliente de alto capital la novedad y el impacto vuelven el costo secundario frente al valor de ser el primero en tenerlo. El modelo de escalamiento por defecto es desplegar **múltiples unidades físicas idénticas** en un mismo sitio (recepciones de alto tráfico), no abaratar el costo unitario para vender "en masa". Fuente de este pivote: `10-bitacora-decisiones.md`, sección 6 — decisión ya registrada en `2-tasks.md` bajo el hito de la segunda reunión.

**Por qué esto importa para cualquiera que lea el resto de este contexto:** el MVP descrito en `6-scope-mvp.md` (paquetería, morosos, membresías) es deliberadamente específico de coworking porque es lo que necesita el piloto real — eso es correcto y no debe generalizarse de más. Pero **el MVP de coworking es el punto de entrada de validación, no el techo del producto.** Ningún entregable ni documento interno debe leerse como si HOLO AI fuera una herramienta diseñada exclusivamente para coworkings; es una plataforma de recepción con IA on-premise cuyo primer despliegue real ocurre en uno.

## El cliente / socio piloto
- **David**, dueño del espacio de coworking **"Works"** (Querétaro).
- Se acercó proactivamente a Guus — la demanda está validada antes de construir.
- Acuerdo verbal existente, nada firmado aún. Conversación seria.
- Aporta: el espacio físico, contactos y red comercial en Querétaro.
- Works funcionará como **showroom permanente** para demostrar el producto a futuros clientes.
- Ya hubo una presentación de avances completa a David (resultado positivo) y una segunda reunión posterior, con su padre y hermano presentes — ver `10-bitacora-decisiones.md` para el detalle narrativo de ambas.

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

## Arquitectura on-premise — decidida (Fase 2 cerrada)
- **Hardware candidato principal:** Beelink GTR9 Pro (AMD Ryzen AI Max+ 395 / 128GB LPDDR5X / 2TB SSD). Precio verificado: ~$1,985–$1,999 USD. Ver `4-research-mercado.md`.
- **OS principal:** Ubuntu (stack de Guus, LLM local, biométrica, avatar, panel de admin).
- **Integración ZKTeco:** VM Windows ligera dentro del Beelink, corriendo solo el SDK (`plcommpro.dll`) y ZKAccess. Ubuntu se comunica con la VM vía API local.
- **Pendiente [INVESTIGAR]:** viabilidad de Wine para eliminar la VM si `plcommpro.dll` corre estable en Ubuntu nativo.

## Naturaleza del proyecto
Híbrido en dos fases simultáneas: (1) encargo casi confirmado con cliente piloto real (Works), y (2) desde el inicio, visión de producto propio escalable. Guus propone la estrategia de escala; David aporta el espacio y la red. El detalle de hacia qué mercado escala está en "Visión y mercado objetivo", arriba — esta sección describe solo la mecánica bifásica del proyecto, no el target.

## Restricciones confirmadas
- **Presupuesto del piloto:** sin cifra fija. Estructura real: David paga hardware + software + fee de Guus. Costo real se construye en Fase 4 con cotizaciones verificadas en MXN.
- **Hardware de cómputo:** on-premise en cada instalación. Privacidad biométrica como argumento de venta central.
- **Display:** kiosk con pantalla OLED transparente. David rechaza biseles/marcos visibles — ni la OLED transparente lo convenció al 100%; propuso él mismo explorar proyección tipo Pepper's Ghost. Ver `10-bitacora-decisiones.md` sección 7.
- **Tipo de "holográfico":** avatar en kiosk con pantalla OLED transparente (NO proyección volumétrica real). La ruta de proyección Pepper's Ghost está en investigación, sin cotización local cerrada — no se trata todavía como decisión de producto.

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
