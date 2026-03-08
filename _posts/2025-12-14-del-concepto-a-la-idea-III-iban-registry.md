---
layout: post
title: Del concepto a la idea III  IBAN Registry
date: 2025-12-14
author: Juan Renato Noh
---


*En los artículos anteriores el objetivo era seleccionar una idea , diseñarla y finalmente desplegarla.  Durante ese  camino seleccionamos un tema muy común : “El catálogo de días inhábiles”  . Al tener nuestra idea seleccionada procedimos a seleccionar nuestra tecnología **FastAPI** , la cual configuramos y  empaquetamos con **Docker**.* 

*La intención en este tercer capítulo es finalmente desplegar nuestra app .* 

*Como suele pasar en la vida (y muy seguido en el desarrollo) los proyectos cambian , por lo que decidí cambiar el api a desplegar a una con la  cual he estado trabajando recientemente , un api para obtener las reglas del **IBAN Registry**.*

***IBAN Registry.***

*Para entrar en contexto primero es necesario conocer el IBAN  , es decir el número de cuenta que utilizamos para realizar transferencias internacionales por medio del canal SWIFT .* 

*¿ Suena algo complicado ? Si es nuevo para ti te dejo el siguiente link para que puedas leer mas acerca del tema .* 

[*https://www.bbva.mx/educacion-financiera/banca-digital/productos-digitales/cuenta-digital-codigo-iban.html*](https://www.bbva.mx/educacion-financiera/banca-digital/productos-digitales/cuenta-digital-codigo-iban.html)

*Ahora hagamos el  siguiente supuesto* 

*Una institución financiera la cual realiza transferencias utilizando este tipo de estructuras de cuentas necesita validar que la estructura del IBAN es correcta y cumple con las normas de SWIFT para cada país , es más comparto la estructura de cada uno de ellos .*

[*https://es.iban.com/estructura*](https://es.iban.com/estructura)

*¿Cómo podemos obtener estas reglas , para luego tener una fuente desde donde validar dichas cuentas?*  

*Una forma es tomarlas de la fuente origen y ese es el IBAN Registry . El IBAN Registry no es más que el archivo oficial con las estructuras de cada país el cual es mantenido por SWIFT y está bajo el estándar ISO 13616\.*

 

### ***Del TXT al API***

*El IBAN Registry se encuentra en 2 formatos txt y pdf, por practicidad tome el txt para extraer las reglas.* 

*Decidí continuar con la base del proyecto anterior* 

* ***FastAPI** para una API clara y bien documentada*  
* ***MongoDB** como almacenamiento*  
* ***Docker***

*De igual forma decidí agregar **Docker Compose** para que  cualquiera pueda extender o probar la aplicación si lo desea con los siguientes archivos .*

* ***Modo desarrollador**, usando `docker-compose.dev`, pensado para explorar, modificar o extender el proyecto.*  
* ***Modo pruebas**, usando  `docker-compose.test`  que ocupa directamente la imagen Docker ya publicada, ideal para probar el API.*

*De todas formas en el repositorio del proyecto pueden encontrar más detalles.*

### ***Por fin el despliegue***

*Para cerrar el ciclo decidí desplegarlo en **Render**. No es la plataforma más robusta ni era la idea hacer algo productivo, pero **cumple perfectamente el objetivo**: tener un demo público y funcional.*

*El deployment es **temporal**. Corre en la capa free y en cualquier momento puede desaparecer… y eso está bien. Mañana ese espacio puede convertirse en otro experimento.*

***API pública (temporal):***  
[*https://open-iban-registry.onrender.com/*](https://www.blogger.com/blog/post/edit/6135588547422670371/400410571138615857#)

***OpenAPI Specification:***  
[*https://open-iban-registry.onrender.com/openapi.json*](https://www.blogger.com/blog/post/edit/6135588547422670371/400410571138615857#)

***Swagger UI:***  
[*https://open-iban-registry.onrender.com/docs*](https://www.blogger.com/blog/post/edit/6135588547422670371/400410571138615857#)

### ***Ejemplos de consumo***

***Carga del IBAN Registry (curl)***

*curl \-X 'POST' \\*  
  *'https://open-iban-registry.onrender.com/registry/upload' \\*  
  *\-H 'accept: application/json' \\*  
  *\-H 'Content-Type: multipart/form-data' \\*  
  *\-F 'file=@iban-registry.txt;type=text/plain'*

*Eh dejado una copia del archivo para poder hacer pruebas en la siguiente liga*   
[*https://github.com/juanrenatonoh/open-iban-registry/blob/main/docs/iban-registry.txt*](https://www.blogger.com/blog/post/edit/6135588547422670371/400410571138615857#)

***Consulta del registry***

*curl \-X 'GET' \\*  
  *'https://open-iban-registry.onrender.com/registry/' \\*  
  *\-H 'accept: application/json'*

### ***Código y contenedores***

***Repositorio:***  
[*https://github.com/juanrenatonoh/open-iban-registry*](https://www.blogger.com/blog/post/edit/6135588547422670371/400410571138615857#)

***Imagen Docker (GHCR):***  
[*https://github.com/juanrenatonoh/open-iban-registry/pkgs/container/open-iban-registry*](https://www.blogger.com/blog/post/edit/6135588547422670371/400410571138615857#)

### ***Conclusión***

El objetivo de este proyecto era tener las reglas para poder validar una cuenta IBAN sin embargo igual existen proyectos los cuales ya implementan dichas reglas por ejemplo : 

* [org.apache.commons.validator.routines.IBANValidator](https://commons.apache.org/proper/commons-validator/apidocs/org/apache/commons/validator/routines/IBANValidator.html)  
* [Iban4J](https://iban4j.org/)

*Ahora si a tu organización le interesa tener la gobernanza o tener el control de dichas reglas esta puede ser una forma de integrarlo a su solución .* 