---
layout: post
title: "Construyendo El Resumen Campeche : un experimento para informar con agentes de IA"
date: 2026-08-01
author: Juan Renato Noh
---

## Cómo pasamos de una idea en un documento a un boletín que se publica solo todos los días

Todo buen proyecto comienza con una pregunta. En nuestro caso fue esta:

> **¿Puede un sistema de agentes de inteligencia artificial reemplazar la rutina
> editorial de un boletín de noticias local?**

No era una pregunta teórica. La planteamos con los pies en la tierra: en Campeche, con
medios locales, con información dispersa y con una audiencia que tiene poco tiempo. El
resultado fue un **experimento** —un *Proof of Concept* (PoC)— que hoy publica un resumen
diario de noticias de forma completamente automática.

Este artículo es la historia de cómo lo construimos: la idea, la especificación que la
sostiene y los agentes y herramientas que hacen el trabajo pesado.

---

## El punto de partida: una hoja de ruta en un documento

Nada de lo que hicimos fue improvisado. Antes de escribir una sola línea de código,
definimos el proyecto en un documento de planificación: nuestro **Lean Canvas**. Ahí
quedaron escritas las preguntas que todo experimento serio debe responder antes de
construir nada:

- **¿Qué problema resolvemos?** La tesis es el formato corto se esta convirtiendo en preferencia ,por lo que presentar informacion en formato corta y resumida pueda ser una forma de evitar desinformación o acercarla a la población que no la consume . 
- **¿A quién le hablamos?** Al ciudadano común
- **¿Qué valor ofrecemos?** Información sintetizada y resumida por diferentes canales . 
- **¿Cómo se sostiene?** Como todo buen experimento, al menor costo posible: de ser posible construccion y operación de 0 pesos . 

Ese documento se convirtió en la **constitución del experimento**: cada decisión técnica
posterior debía regresar a él. El objetivo nunca fue "hacer tecnología bonita", sino
validar una hipótesis: *un boletín 100% automatizado puede generar valor.

---

## La segunda pieza: el editor invisible

Si el Lean Canvas definió el **qué** y el **porqué**, hacía falta definir el **cómo**
. Ahí nació la pieza más importante de todo el sistema: **el prompt maestro**.

Piénsalo como el manual de estilo de un periódico, pero en forma de instrucciones para
un Modelo de IA. En él quedaron escritas las reglas editoriales:

- Buscar noticias publicadas estrictamente hoy, priorizando medios locales y fuentes
  oficiales.
- No inventar. No reutilizar noticias viejas. No caer en el sensacionalismo.
- Seleccionar los 7 acontecimientos con mayor impacto, en secciones fijas:
  Campeche, Seguridad, Nacional, Deportes y Clima.
- Redactar cada noticia en una sola línea, de 8 a 15 palabras, para que el boletín
  completo se lea en menos de un minuto.

Ese documento de texto es, en la práctica, el **Cerebro del producto**. La IA no "decide"
qué es noticia por su cuenta: sigue las reglas que le dimos. Nosotros definimos la
filosofía; ella ejecuta la redacción. Y la filosofía cabe en una frase:

> **"Primero informa, después permite profundizar."**

---


### El redactor (Reporter Agent)
Es el agente que escribe. Toma el prompt maestro, le inyecta la fecha de hoy y consulta al
**Modelo IA**. La IA sale a buscar con
herramientas de búsqueda integradas, selecciona lo relevante y redacta el boletín con el
tono y formato que le indicamos.

### El editor de distribución (Channel Publisher)
El boletín ya está listo; ahora hay que publicarlo. Aquí actúa el segundo agente: un
**orquestador de distribución** que entrega el contenido a cada canal registrado. Hoy
publica en **Telegram** y en **Facebook**, y está diseñado para sumar nuevos canales
(Instagram, Threads, X) con un simple cambio de configuración.

### La plantilla: 
La arquitectura del equipo editorial es modular: cada canal es un "publicador"
independiente. Si mañana queremos publicar en una plataforma nueva, solo hay que añadir
otro colaborador al equipo. El experimento crece sin reescribir lo ya construido.

---

## Qué estamos validando con este experimento

Un PoC no se construye para quedarse en el código: se construye para aprender. Nuestras
preguntas de validación son:

1. **¿La IA puede mantener un estándar editorial consistente** a lo largo de semanas y
   meses, sin que la calidad se degrade?
2. **¿La audiencia realmente adopta el hábito de informarse** con un resumen de un minuto?
3. **¿El modelo de costo cero es sostenible** en el tiempo y puede escalar a más canales , video , fotos

Cada día de publicación es una medición. Cada interacción en Telegram o Facebook es un
dato. La idea es simple: **si el experimento funciona, lo convertimos en producto. Si no,
aprendimos y ajustamos.**

---

## Te invitamos a ser parte del experimento

Esto es apenas la primera iteración. Donde el agente se encuentra publicando en Telegram y Facebook automaticante .

Aun no sabemos si tendra mas iteraciones pero si te interesa verlo funcionando o consumir la información te invito :

- **Telegram** → [https://t.me/elresumencampeche](https://t.me/elresumencampeche) y
  recibe el resumen cada mañana en menos de un minuto.
- **Facebook** → [https://www.facebook.com/elresumencampeche](https://www.facebook.com/elresumencampeche).

Si te es interesante 

- **Comparte el boletín** y ayúdanos a medir si la comunidad quiere (y adopta) esta forma
  de informarse.

- **Comenta en los canales**: toda observación es bienvenida, porque el propósito de un PoC es
  escuchar y aprender.


