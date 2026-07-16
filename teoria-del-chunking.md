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

## El rol del integrador: conduce la IA y trabaja las puertas

La IA no opera sola. En cada chunk hay una **persona al mando —el integrador—** y su rol es el más crítico del modelo. Tiene dos frentes:

- **Dentro de la caja** — el integrador **conduce la IA y la supervisa en cada paso**. La IA acelera el trabajo interno, pero no decide sola: alguien la dirige, revisa lo que produce y responde por el resultado. Sin ese conductor, no hay trabajo verde comprimido; hay output sin control.
- **En las puertas** — su trabajo más crítico es **ayudar al cliente a abrir la puerta de entrada y cerrar la de salida, a tiempo**. Las puertas las abre el cliente, pero el integrador es quien las provoca: prepara el artefacto listo para decidir, persigue el input que falta, reduce la latencia de cada dependencia. Quien mueve el proyecto hacia adelante es el humano, no la IA.

Por eso, aunque la IA encoja las cajas, **el camino crítico lo trabaja una persona**: la IA no abre puertas ni se conduce sola.

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

## Dos palancas de aceleración: AI Fluency y AI Solutions

La teoría nombra **dos palancas** distintas con las que la IA encoge el trabajo interno de un chunk. Son **independientes**: un chunk puede acelerarse con una, con la otra, o con ambas.

### AI Fluency

- **Qué es** — la capacidad de los integradores (las personas) de usar elementos **básicos** de IA y saber **cuándo** usarlos.
- **Nivel** — horizontal, una habilidad humana. Manejar la IA "como si fuera Excel".
- **IA básica** = nivel prompt / LLM, transcripción, automatización simple.
- **Ejemplos** — ya nadie toma notas: se transcribe y se automatiza. Ante un problema donde una IA básica ayuda, saber reconocerlo, aplicarla y manejarse mínimamente.
- Es una **alfabetización base**, no un producto.

### AI Solutions

- **Qué es** — soluciones **completas** que aceleran un chunk de punta a punta, creadas con IA y que a su vez pueden usar IA. A todos los efectos, **assets basados en IA**.
- **Nivel** — un escalón de abstracción **por encima** de la fluency. Empaquetadas.
- **Qué cuenta** — cualquier solución IA end-to-end que resuelva el chunk: propia o de terceros, genérica o vertical.
- **Ejemplos (stack actual)** — Setup Agents / AI Driven Framework (CDF-native: extracción de epics, field mapping, sizing, generación de tech enablers), Slackbot (guías técnicas, riesgos y modelos de datos en una sesión), LucidAI (Story Maps visuales dentro de Lucidchart), **OAT (Org Assessment Tool)** — herramienta creada por Servicios Profesionales de Iberia que analiza el estado, la customización y la configuración de una org del cliente; reduce un trabajo de muchas semanas a días.

### Relación entre ambas

Son **dos palancas independientes**. Cada una acelera el chunk por su cuenta; no hay jerarquía obligatoria entre ellas.

### Efecto sobre el modelo de puertas

El efecto **principal** de ambas palancas es **encoger la caja** (el trabajo interno). Pero, de forma **secundaria, ambas pueden reducir la fricción de las puertas**: no *abren* la puerta —eso solo lo hace el cliente— pero pueden hacer que el cliente la abra **antes**. Un integrador con fluency prepara un artefacto claro y listo para decidir, y la aprobación tarda un día en vez de una semana; un AI Solution pre-estructura lo que el cliente debe entregar, y el input llega más limpio y más rápido.

La puerta sigue siendo del cliente y sigue en el camino crítico. La buena práctica solo **recorta su latencia**, no la elimina.

## Cómo los arquitectos dominan la IA: Fluency vs Assets

Las dos palancas exigen dos cosas distintas de las personas. Un arquitecto de Salesforce debe **dominar la AI Fluency** y **conocer los AI Assets** (las AI Solutions). No son el mismo esfuerzo ni se adquieren igual.

- **Dominar la Fluency** — es una habilidad interna, como aprender a usar Excel hace veinte años. No se compra; se entrena.
- **Conocer los Assets** — es saber qué soluciones existen, qué chunk resuelve cada una y cuándo tirar de ellas (SEAP, LucidAI, OAT, Setup Agents…). No hay que reconstruirlas: hay que saber usarlas.

### El *tricky part*: entrenar la Fluency con muchos vendors

Lo difícil no es querer, es **cómo**. El mercado ofrece capacidades **parecidas de formas distintas** — Gemini, Codex, Cursor, Claude Code, ChatGPT — y por encima soluciones más específicas (Elements.cloud, LucidAI…) que ya son **AI Assets**, no Fluency. Para la teoría, dominar la Fluency es **dos cosas**:

1. **Conocer el jargon básico** — el vocabulario mínimo para operar (prompt, contexto, agente, modelo, memoria…).
2. **Amoldar la mente** — sobre todo, adoptar la **nueva forma de pensar**. Esto es el verdadero músculo, y no se copia: se desarrolla.

### El problema del ruido

Hay un segundo obstáculo, más silencioso que el de los vendors: el **ruido**. Mucha gente está **ansiosa por compartir** sus logros, lo que ha aprendido, lo que usa. Bien intencionado, pero el volumen hace que los arquitectos **pierdan el foco de lo que de verdad importa**.

- El ruido es **inevitable** — viene con la adopción masiva de IA, no se puede apagar.
- **Distinguir la señal del ruido es, en sí mismo, parte de la AI Fluency.** El músculo no es solo saber usar la IA; es saber **a qué prestar atención** y qué ignorar.
- Por eso las **AI Pills** son deliberadamente **señal, no ruido**: son iniciativas **validadas y curadas** (100% válidas), no un feed abierto de "mira lo que hice". Es la diferencia entre una vitamina y el zumbido de fondo.

### AI Pills: vitaminas para la Fluency

En España el equipo fomenta la Fluency con **AI Pills**: pequeñas iniciativas **validadas** que actúan como **vitaminas** —señal curada frente al ruido de fondo. No quitan el esfuerzo —hay que dedicar tiempo, instalar, investigar— pero **ayudan a desarrollarlo**. Vienen de varias formas:

1. **Compartir casos de uso (workflow de Slack)** — los arquitectos envían de qué forma innovadora, o que les haya ahorrado tiempo, han usado la IA, **y cómo reproducirlo**. Se comparte con el resto del equipo.
2. **Sesiones de socialización (viernes)** — sesiones semanales exclusivas para compartir cómo la IA ha mejorado casos de uso reales.
3. **KSO assets con IA (Iberia)** — todos los assets producidos como parte de los KSOs deben **usar IA**: o para crearlos, o el propio asset la usa (p. ej. el **OAT — Org Assessment Tool**).

### La Pill más sutil: entender qué copiar y qué no

La última forma de Pill es aprender **qué hay que entender y qué hay que copiar y pegar**. En Iberia se entiende que los **skills** son muy útiles — pero **no para copiar y pegar como si fueran un asset**. Un asset es otra cosa: **autocontenido y elaborado**. Un skill sirve para **abrir la mente**: ese skill está cubriendo un **caso de uso** que podrías haber resuelto **sin copiarlo**, si se te hubiera ocurrido la idea.

El objetivo no es reutilizar el trabajo del otro, sino **desarrollar el músculo de ver el caso de uso**. La reutilización vive en el **AI Asset**; el músculo vive en la **AI Fluency**. Confundirlos es tratar la Fluency como si fuera un asset — y así no se entrena.

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

## Encaje en Salesforce: SEAP y Quantum Leap

El modelo de puertas separa dos ejes de acción que la industria confunde: **encoger las cajas** (lado oferta, del integrador) y **mover las puertas** (lado cliente, el único que toca el camino crítico). Dos iniciativas de Salesforce se colocan, cada una, en un eje distinto.

### SEAP — el AI Solution que aspira a cubrir todos los chunks

- **Qué es** — una **multitool** que llama al LLM haciéndole **adoptar roles** y guarda automáticamente en **memoria** lo que se va haciendo. Aspira a situarse **por encima de todos los project chunks** y resolver varios de golpe.
- **Dónde encaja** — es un **AI Solution** (mismo eje que Setup Agents, Slackbot, LucidAI, OAT), solo que con **mayor alcance**: en vez de encoger una caja, intenta encoger **muchas cajas a la vez**.
- **Lo que la teoría dice de él** — SEAP **no cambia las puertas** ni el hecho de que **el cliente no puede ir más deprisa de lo que va**. Comprime el lado oferta a mayor escala; el camino crítico —que vive en las puertas del cliente— **queda intacto**. Sigue siendo, geométricamente, encoger cajas.

### Quantum Leap — el programa que sí mueve las puertas

- **Qué es** — el **programa global de Servicios Profesionales** para transformar el modelo de entrega hacia una metodología **AI-native**. No es "usar herramientas de IA": es un **rediseño completo del operating model**.
- **Lo que la teoría dice de él** — Quantum Leap es una metodología de **compromiso bilateral**:
  - el **cliente** se compromete a **mover y acortar sus dependencias** (abrir las puertas antes y más juntas);
  - **Salesforce** se compromete a **usar agentes para optimizar todos los chunks al máximo** (encoger todas las cajas).
- **Por qué es distinto** — es la **única palanca de la teoría que actúa sobre las puertas**, no sobre las cajas. Y solo puede hacerlo porque es **bilateral**: las puertas son del cliente, así que moverlas exige su compromiso explícito. Por eso Quantum Leap es lo único que puede acercarse a comprimir un proyecto **a nivel de proyecto**, no solo dentro de los chunks.
- **El gran reto** — alinear los **compromisos de velocidad de ambas partes en el contrato**. Mover puertas no es una buena intención: es una obligación contractual recíproca (el cliente ata su ritmo de apertura, Salesforce ata su optimización). Sin ese anclaje contractual, no hay Quantum Leap.

### Sin Quantum Leap: AI Delivery (y a dónde va la aceleración)

Cuando la IA encoge las cajas pero **nadie mueve las puertas**, lo que queda es **AI Delivery**: la IA ayuda a entregar más rápido *dentro* de los chunks, pero el plazo del proyecto **no baja** —sigue topado por las puertas del cliente.

La capacidad liberada no desaparece; **se reconvierte**. Como el tiempo de calendario no se puede recuperar, el margen ganado dentro de las cajas se gasta en una de dos cosas:

1. **Más scope** — se mete más trabajo en el mismo plazo.
2. **Más calidad** — se pule más el mismo scope en el mismo plazo.

Es decir: **AI Delivery cambia *qué* entregas (más o mejor), no *cuándo* lo entregas.** Solo Quantum Leap —moviendo puertas por contrato— cambia el *cuándo*.

### El mapa completo

| Palanca | Eje | Qué toca | ¿Mueve el camino crítico? |
|---|---|---|---|
| AI Fluency | oferta | encoge la caja (gente) | No (recorta latencia de puerta, no la mueve) |
| AI Solutions | oferta | encoge la caja (assets) | No (íd.) |
| **SEAP** | oferta | encoge **muchas cajas** a la vez | **No** |
| **AI Delivery** | oferta | encoge cajas, puertas quietas → **más scope o más calidad** | **No** (default sin Quantum Leap) |
| **Quantum Leap** | **cliente + oferta** | **mueve las puertas** (por contrato) + encoge cajas | **Sí** — único |

Corolario: por muchas cajas que encojas —una, varias o todas con SEAP— el proyecto sigue topado por las puertas. Sin acuerdo, ese es el mundo de **AI Delivery**: la aceleración se reinvierte en **scope o calidad**, no en plazo. Solo un acuerdo que **mueva las puertas contractualmente** (Quantum Leap) cambia el camino crítico. Todo lo demás optimiza el lado que no era el cuello de botella.

## Preguntas abiertas (para completar la teoría)

- ¿Cómo se **mide** el ritmo de apertura de puertas del cliente para dimensionar el equipo?
- ¿Existen **tipos de proyecto** con pocas puertas (mucho verde interno) donde el 10x sí se acerque a nivel de proyecto? (Hipótesis: dev puro vs. transformacional.)
- ¿Se pueden **paralelizar chunks** para aliviar la presión sobre el cliente? Solo sirve si abren **puertas distintas**; si varios verdes convergen en la *misma* puerta del cliente, el paralelismo no ayuda.
- ¿Puede un chunk **cambiar de color/velocidad** según la madurez del cliente? Un cliente ágil abre puertas más rápido — palanca de gestión.
- ¿Cómo se **anticipan los bloqueos** (🔒 specs de API, datos limpios) para pedir esas puertas de entrada al inicio y no a mitad de proyecto?
