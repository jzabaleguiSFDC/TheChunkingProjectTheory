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

## Preguntas abiertas (para completar la teoría)

- ¿Cómo se **mide** el ritmo de respuesta del cliente para dimensionar el equipo?
- ¿Existen **tipos de proyecto** donde las dependencias con el cliente sean mínimas y el 10x sí se acerque a nivel de proyecto?
- ¿Se pueden **paralelizar chunks** para reducir la presión sobre las dependencias del cliente (frentes independientes que el cliente atiende en distinto momento)?
- Taxonomía completa de **tipos de chunk** por fase y por tipo de proyecto, con su set de herramientas asociado.
