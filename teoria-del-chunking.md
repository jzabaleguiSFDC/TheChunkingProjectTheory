# The Chunking Project Theory

> Fuente de verdad de la teoría. El deck HTML se genera a partir de este documento.

## Premisa: la obsesión del 10x

Las empresas de implementación de proyectos están obsesionadas con ir **10x más rápido** gracias a la IA. La aspiración es comprimir un proyecto de 1 año en 1 mes.

Esta teoría sostiene que esa compresión **no es posible en el caso general**, y explica por qué.

## Tesis central

El **camino crítico** de un proyecto de implementación no lo determina la velocidad del implementador. Lo determinan las **dependencias con el cliente**.

La IA acelera el lado del implementador. No acelera —automáticamente— la capacidad del cliente de adaptarse a esa aceleración. El cliente podrá, o no, seguir el ritmo.

Por tanto: acelerar el lado que no está en el camino crítico no comprime el proyecto.

## Concepto clave: chunks

Un proyecto se puede partir en **dependencias con el cliente**. Entre esas dependencias existen unidades de trabajo que llamamos **chunks**.

Propiedades de un chunk:

- **Tiene un tipo**, que depende de la **fase** del proyecto y del **tipo de proyecto**.
- **Requiere una o varias herramientas de IA**, distintas según su tipo.
- Está **acotado por dependencias con el cliente** en sus extremos: normalmente empieza y/o termina en un punto donde se necesita al cliente (feedback, reunión, verbalización de requerimientos, aprobación).

Ejemplos de chunks por fase:

- **Discovery** — reuniones y workshops son esenciales. El cliente explica y el integrador captura. Herramientas de IA básicas: transcribir reuniones, generar casos de uso, documentarlos. Ejemplos concretos: **Elements.cloud**, **NotebookLM**, **Claude Code**.
- **Implementación** — herramientas como Cursor, Claude Code, Codex son necesarias para implementar y configurar.

Cada fase y cada tipo de proyecto produce chunks de tipo distinto, y por tanto exige un conjunto de herramientas de IA distinto.

## Anatomía de un chunk: puertas y trabajo interno

Todo chunk tiene **tres partes**, no una:

```
[PUERTA DE ENTRADA] → ( trabajo interno ) → [PUERTA DE SALIDA]
      el cliente          integrador + IA          el cliente
```

- **Puerta de entrada** — el cliente la abre para que el chunk *empiece*: entrega datos, especificaciones, accesos, una decisión o su presencia. Sin ella, el chunk está **bloqueado**.
- **Trabajo interno** — es del integrador. Es lo único que la IA comprime. Tiene un **color** según qué lo topa (ver taxonomía).
- **Puerta de salida** — el cliente la abre para *cerrar* el chunk y avanzar: feedback, aprobación, firma, sign-off.

Principios:

- **Ambas puertas las abre el cliente.** La IA **no abre puertas** — solo acelera el trabajo entre ellas.
- **Las puertas son los puntos de inflexión del proyecto.** Son, exactamente, las dependencias con el cliente. El camino crítico se dibuja puerta a puerta.
- **El trabajo y la puerta son cosas distintas.** El trabajo de redactar un SOW se comprime muchísimo; la *firma* de ese SOW es una puerta y no se comprime. No hay que confundir el color del trabajo con la puerta que lo rodea.
- **Un chunk bloqueado** es un chunk con la puerta de entrada cerrada. El trabajo interno —aunque sea verde y la IA lo haría en horas— ni siquiera empieza. Ejemplos típicos:
  - **Integraciones** — bloqueadas sin las **especificaciones de las APIs** (y accesos) del cliente o de terceros.
  - **Migración de datos** — bloqueada sin los **datos limpios** del cliente.

## El giro de la tesis: la IA encoge las cajas, no mueve las puertas

Con esta anatomía, la tesis se vuelve geométrica:

> La IA **encoge las cajas** (el trabajo interno). Las **puertas entre cajas no se mueven**. Si encoges las cajas 10x, el proyecto pasa a estar hecho, sobre todo, de **puertas**.

El camino crítico es la suma de *puertas + trabajo*. Cuando el trabajo se vuelve pequeño, **las puertas dominan** el plazo total. Acelerar el trabajo interno (que casi siempre es verde) no comprime un proyecto cuyo tiempo vive ya en las puertas del cliente.

## El mecanismo: aceleración asimétrica

La IA reduce la duración del trabajo *dentro* de un chunk en el lado del implementador. Ejemplo:

> Un sprint clásico tomaba **3 semanas**. Con IA, el mismo trabajo toma **3 días**.

Pero el chunk está limitado por el cliente en sus fronteras. El cliente que antes daba feedback, tenía reuniones y verbalizaba requerimientos **cada 3 semanas** no está garantizado que pueda hacerlo **cada 3 días**.

Si el implementador va 10x más rápido pero el cliente no reduce sus tiempos de respuesta en la misma proporción, el proyecto **no se comprime 10x**. Se comprime solo hasta donde el cliente permite.

## Corolario: reducir equipo o es imposible

Cuando el cliente **no puede** reducir sus tiempos de respuesta al ritmo de la aceleración, quedan dos salidas:

1. **Mantener el tamaño de los chunks y reducir el equipo.** Si el cliente solo puede cerrar dependencias cada 3 semanas, no tiene sentido un equipo dimensionado para producir cada 3 días. Se ajusta el equipo al ritmo real del cliente, no al ritmo posible del implementador.
2. **Reconocer que la compresión pretendida es imposible.** No se puede hacer el proyecto de 1 año en 1 mes, porque el camino crítico está fuera del control del implementador.

La aceleración por IA no elimina el camino crítico del cliente. Solo cambia quién es el cuello de botella.

## Implicaciones

- El "10x" es real **dentro** de los chunks del implementador, no **a nivel de proyecto**.
- Dimensionar el proyecto por la velocidad del implementador (y no por el ritmo del cliente) lleva a sobredimensionar el equipo y a expectativas irreales de plazo.
- La palanca real de gestión no es "más velocidad", sino **ajustar el equipo al ritmo de las dependencias del cliente**.

## Taxonomía de chunks (v2)

Cada chunk se describe por su **puerta de entrada** (qué abre el cliente para empezar), su **trabajo interno** (color según qué lo topa) y su **puerta de salida** (qué abre el cliente para cerrar). Las herramientas mostradas son el stack actual en uso.

| # | Chunk | Puerta ENTRADA (cliente) | Trabajo interno | Puerta SALIDA (cliente) | Herramientas IA |
|---|---|---|---|---|---|
| 0 | Análisis + redacción SOW | Brief / RFP inicial | 🟢 verde | Firma del SOW (decisión) | Setup Agents (sizing), Slackbot, Gemini |
| 1 | Workshop de elicitación | Cliente presente (agenda) | 🔴 presencia | Alimenta #2 | Gemini (transcribe), LucidAI |
| 2 | Síntesis post-workshop | Transcripts (de #1) | 🟢 verde | Feedback opcional | Gemini, Slackbot, NotebookLM |
| 3 | Story mapping visual | Entendimiento (#2) | 🟢 verde | Valida el mapa (feedback) | LucidAI (Story Maps en Lucidchart) |
| 4 | Extracción de epics + sizing | Mapa validado | 🟢 verde | Prioriza (decisión) | Setup Agents / AI Driven Framework (CDF) |
| 5 | Field mapping / modelo de datos | **Esquema origen** (input) 🚩 | 🟢 verde | Confirma modelo (feedback) | Setup Agents, Slackbot (data models) |
| 6 | Tech enablers + guías/riesgos | Diseño (interno) | 🟢 verde | Aprobación de diseño (decisión) | Setup Agents, Slackbot |
| 7 | Build / configuración | Diseño aprobado | 🟢 verde (10x real) | Alimenta test | Cursor, Claude Code |
| 8 | Integraciones con terceros | **Specs de API + accesos** (input) 🚩🔒 | 🟢 verde | Sandbox / endpoint del 3º | Cursor, Claude Code |
| 9 | Migración de datos | **Datos limpios** (input) 🚩🔒 | 🟢 verde | Valida datos migrados | Cursor, Claude Code |
| 10 | UAT | Testers presentes | 🔴 el cliente prueba, el integrador espera | Sign-off (decisión) | — |
| 11 | Fix post-UAT | Feedback de UAT | 🟢 verde | Re-test | Cursor, Claude Code |
| 12 | Formación / change management | Usuarios presentes | 🔴 presencia | Adopción / go-live | Gemini (materiales) |

Leyenda:

- 🟢 **verde** — trabajo interno del integrador; la IA lo comprime de verdad (hasta 10x).
- 🔴 **rojo** — trabajo topado por el cliente (presencia, el cliente ejecuta); la IA no lo mueve.
- 🚩 **puerta de entrada tipo *input*** — candidata a **bloqueo** si el cliente no entrega a tiempo.
- 🔒 — los dos bloqueos crónicos: **specs de API** (integraciones) y **datos limpios** (migración).

Lo que revela la tabla: **casi todo el trabajo interno es verde** — la IA lo aplasta. El problema nunca es el color del trabajo. El problema es que **las puertas (entrada + salida) son casi todas del cliente** y no comprimen. Ahí vive el camino crítico.

## Preguntas abiertas (para completar la teoría)

- ¿Cómo se **mide** el ritmo de apertura de puertas del cliente para dimensionar el equipo?
- ¿Existen **tipos de proyecto** con pocas puertas (mucho verde interno) donde el 10x sí se acerque a nivel de proyecto? (Hipótesis: dev puro vs. transformacional.)
- ¿Se pueden **paralelizar chunks** para aliviar la presión sobre el cliente? Solo sirve si abren **puertas distintas**; si varios verdes convergen en la *misma* puerta del cliente, el paralelismo no ayuda.
- ¿Puede un chunk **cambiar de color/velocidad** según la madurez del cliente? Un cliente ágil abre puertas más rápido — palanca de gestión.
- ¿Cómo se **anticipan los bloqueos** (🔒 specs de API, datos limpios) para pedir esas puertas de entrada al inicio y no a mitad de proyecto?
