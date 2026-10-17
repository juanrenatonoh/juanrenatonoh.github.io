---
title: Por qué usamos Markdown cuando trabajamos con IA
date: 2026-10-17
layout: post
---

Esta semana, mientras trabajaba en mis flujos con IA, me detuve a cuestionar algo que hasta ahora había dado por sentado: ¿por qué usamos archivos Markdown (`.md`)?

No me refiero únicamente a por qué los desarrolladores los utilizamos, sino a si realmente entendemos la intención detrás de esta práctica o simplemente estamos replicando algo que vemos en las herramientas, los artículos y la industria.

Antes de cuestionar a los demás, decidí cuestionarme a mí mismo: ¿qué valor aporta esta práctica al proyecto, al flujo de trabajo y a mis compañeros? ¿O soy alguien más que la adopta porque parece ser lo que todos hacen?

Al reflexionar, recordé conceptos que había leído y las 4D del framework de Anthropic. Particularmente, la idea de que, si queremos delegar trabajo a un agente, primero debemos **describirlo de manera clara y precisa**.

Aquí encontré mi primer punto: necesitamos hacer explícitos el objetivo, el contexto, las restricciones y los resultados esperados. Los archivos Markdown pueden ayudarnos a organizar y comunicar esa información tanto a las personas como a los agentes.

Pero hay un segundo punto que me parece todavía más interesante.

Los modelos de lenguaje son no deterministas. No podemos asumir que, ante una misma instrucción, siempre obtendremos exactamente el mismo resultado ni que la respuesta generada será correcta por el simple hecho de haber seguido nuestras instrucciones.

Por eso, definir el trabajo no solo sirve para orientar al agente. También nos permite establecer una referencia contra la cual evaluar el resultado generado.

Si definimos adecuadamente los criterios de aceptación, podemos contrastar el código producido con lo que realmente solicitamos y utilizar pruebas, validadores y otros mecanismos para obtener evidencia de cumplimiento.

Así, estos archivos pueden convertirse en algo más que documentación: pueden formar parte de un proceso de trabajo en el que **delegamos con claridad y verificamos los resultados**.

Y aquí llegué a una última conclusión.

Decir «usemos Markdown» no es lo más importante. Entender por qué lo usamos es lo que realmente nos da valor.

Si comprendo la intención detrás de esta práctica, también tengo la libertad de elegir otro mecanismo cuando resulte más adecuado. Quizá Markdown para especificaciones e instrucciones, YAML para configuraciones, JSON para intercambiar datos estructurados u otros mecanismos para definir y verificar requisitos.

No significa que todos los formatos sean intercambiables, sino que la elección debe responder a las necesidades del problema y del flujo de trabajo.

**Cuando entendemos la intención detrás de una práctica, dejamos de replicar una receta y adquirimos el criterio para elegir la herramienta adecuada.**

Tal vez esta sea una de las habilidades que necesitamos desarrollar en esta nueva etapa de trabajo con IA: no adoptar prácticas únicamente porque funcionan para otros, sino cuestionarlas, entender qué valor aportan y comprobar si realmente mejoran nuestro trabajo.

Al final, la pregunta no es solamente por qué usamos Markdown.

Es cuántas de las prácticas que estamos adoptando para trabajar con IA entendemos realmente y cuántas estamos replicando porque las herramientas, los artículos o la industria nos dicen que así se hace.

---

*Idea y reflexión propias. Redacción final asistida por ChatGPT. Publicado por copilot*
