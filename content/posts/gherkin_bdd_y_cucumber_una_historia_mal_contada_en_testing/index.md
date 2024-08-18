---
date: 2024-01-16
title: Gherkin, BDD y Cucumber, una historia mal contada en Testing
description: Poco después de haber dado mis primeros pasos en el mundo de las pruebas automatizadas escuché nombrar estos tres términos en conjunto por primera vez, mi acercamiento inicial me llevó a la misma
---

Poco después de haber dado mis primeros pasos en el mundo de las pruebas automatizadas escuché nombrar estos tres términos en conjunto por primera vez, mi acercamiento inicial me llevó a la misma conclusión que todos parecían tener, “**Gherkin, BDD y Cucumber tienen algo que ver con Testing**”, que debo decir, suena bastante convincente si tenemos en cuenta que al googlear obtenemos resultados de personas explicando como construir pruebas automatizadas, logrando así que nadie se cuestione el origen de dichos términos.

Pasaron los meses y el tema quedó allí, hasta que un día surgió ante mí la gran oportunidad de dar una presentación para mis colegas, no era una presentación cualquiera, era nada más y nada menos que una introducción a Gherkin, aquel lenguaje que hasta entonces creía conocer. Y he de decir que poco tiempo pasó antes de que cambie por completo el rumbo de mis creencias.

Si es la primera vez que oís nombrar estos términos, no hay problema, aprenderás algo nuevo y de paso tendrás con qué desafiar las creencias de tus compañeros. Por otra parte, si ya los conoces y hasta has trabajado con ellos en Testing, puede que no te vaya a gustar lo que te voy a contar.

## ¿Qué es Gherkin?

<img class= thumbnailshadow src=gherkin_syntax.png alt ="Gherkin Syntax"/>

Gherkin o Pepinillo en su traducción al español, es en si un DSL, Lenguaje Específico de Dominio, esto significa que es un lenguaje que se creó específicamente para resolver un problema en particular proveyéndonos también de una técnica que nos permite solucionar dicho problema.

¿Cuál es nuestro problema? La comunicación efectiva.

La comunicación entre las partes de un equipo siempre va a ser un problema, más específicamente la comunicación entre lo que se denominó posteriormente “The Three Amigos” es decir, el Product Owner (PO), el desarrollador y el tester. Ahora ¿Cómo nos ayuda este lenguaje a mejorar la comunicación entre dichas partes?

Podría hacer un artículo entero sobre Gherkin, así que para simplificar las cosas solo haré uso de los elementos esenciales del lenguaje para que entendamos cómo se utiliza el mismo.

**Gherkin** nos provee 6 palabras clave:

* **Feature** (Característica, Funcionalidad): Funcionalidad del sistema.
* **Background** (Antecedentes): Precondiciones del escenario.
* **Scenario** (Escenario): Situación general.
* **Given** (Dado): Contexto de la situación.
* **When** (Cuando): Acción.
* **Then** (Entonces): Resultado esperado.
Supongamos que el PO cita a los desarrolladores y a nosotros, testers, para presentarnos una nueva funcionalidad del sistema, la funcionalidad consiste en las posibilidades que tiene un usuario de publicar blogs en una página. Todos acordamos en utilizar Gherkin para describir los criterios de aceptación de nuestra funcionalidad para mejorar nuestra comunicación, por lo tanto luego de unos minutos de charla sobre lo presentado por el PO llegamos a un documento como el siguiente:

(Voy a emplear **Gherkin** en español para facilitar la lectura)

<img class= thumbnailshadow src=gherkin_code.png alt="Cucumber code"/>

Como podemos observar, los escenarios no son más que situaciones o ejemplos que pueden darse en nuestra funcionalidad, y las palabras: Dado, Cuando, Entonces (Given, Then, When) nos ayudan a describir claramente lo que debería de suceder en cada una de estos casos.

**¿Quién lo redacta?** Es indiferente, la idea es que todos los participantes, los “Three Amigos” tengan una charla fluida en la cual se presenten los criterios de aceptación iniciales y a partir de ahí puedan surgir más ideas y escenarios que se puedan evaluar en ese momento o que el PO se los lleve para rever con el cliente. Por dar un ejemplo, en este caso alguno de los integrantes podría preguntarse:

>¿Puede el administrador “Pepe” editar un artículo ya publicado por un usuario? o ¿Puede el administrador “Pepe” publicar en un blog de otro administrador?

La idea es intentar cubrir todos los casos que se nos vengan a la mente para que todos estemos de acuerdo en cómo debe comportarse nuestro sistema. ¿De qué nos ayuda tenerlo escrito de esta forma? Es un lenguaje natural y estructurado y fácil de entender por una persona técnica así como no técnica, es un estándar. Cualquier cliente podría entender los requerimientos sin ser un experto, digamos que hace que las especificaciones funcionales sean digeribles. Y la frutilla del postre, ayuda a que luego dichas frases puedan ser utilizadas como la base de automatizaciones, pero llegaremos allí luego.

## ¿Qué origen tiene Gherkin? (Nacimiento de BDD)

<figure>
  <img class= thumbnailshadow src=daniel_north.png alt="Daniel Terhost-North"/>
  <figcaption>Daniel Terhost-North</figcaption>
</figure>

Había una vez un desarollador con más de 20 años de experiencia en el rubro, este desarrollador lleva el nombre de **Daniel Terhost-North**. Dan formaba parte de un equipo el cual desarrollaba bajo la modalidad de [TDD](https://www.inesdi.com/blog/que-es-TDD-test-driven-development/?ref=ignaciosambrailo.com) (Test Driven Development) (Desarrollo Guiado por Pruebas).

**TDD** en pocas palabras busca basar nuestro desarrollo en pruebas que escribimos antes de escribir el código de nuestro sistema, por más confuso que suene, tiene sentido, supongamos que estamos diseñando una aplicación que tiene como funcionalidad la suma de dos numeros enteros:

```
// Test de mi Sistema
Operaciones_Suma_SumaDeEnterosExitosa:
resultado = sumar(2,2)
assert resultado == 4
```

```
// Funcionalidad de mi sistema
Operaciones_Suma_SumaDeEnterosExitosa(numero_1,numero_2):
return numero_1+numero_2
```

Entonces primero creariamos la función “**Operaciones_Suma_SumaDeEnterosExitosa**” y en base al comportamiento que debería seguir dicha funcionalidad, programaríamos la función de la cual hace uso “**sumar**”.

(Se que es un ejemplo muy vago, pero mientras entiendas la idea me sobra)

El problema según la palabra de Dan radicaba en que seguía encontrándose con las mismas confusiones una y otra vez bajo este modelo: Por dónde empezar, qué testear y qué no testear, cuánto testear en un mismo test, cómo nombrar dichos tests, cómo entender por qué un test falla.

(Cabe resaltar que TDD hace referencia a la etapa de desarrollo, es decir, **tests escritos por los desarrolladores**)

Todo esto en resumidas cuentas lo impulsó a dar nacimiento a una nueva metodología “**BDD**” publicando su primer artículo al respecto “[Introducing BDD](https://dannorth.net/introducing-bdd/?ref=ignaciosambrailo.com)” (Behaviour Driven Development) (Desarrollo Guiado por Comportamiento).

Si en TDD los desarrolladores creaban scripts de pruebas que su código debía superar para así cercenarse de que su trabajo cumplía con la consigna, en **BDD** se creaban scripts de pruebas que el código debía superar de igual forma pero bajo la perspectiva del comportamiento del usuario. Si bien puede sonar algo confuso, lo vamos a entender cuando conectemos **BDD** con **Gherkin**.

Cabe aclarar que **BDD** no tiene relación en su nacimiento con Gherkin, si no que años después de nacer **BDD**, Daniel North junto con Chris Matts y Liz Keogh toman un template de requerimientos y lo convierten en un documento que hace uso de palabras claves en inglés así como vimos anteriormente, llevándonos así al nacimiento del primer template de **Gherkin**.

### ¿Qué relación tiene Gherkin con BDD?

Como vimos anteriormente, **Gherkin** es sólo una forma de escribir requerimientos de un sistema y **BDD** es una metodología de desarrollo que consiste en escribir los tests basados en el comportamiento del usuario antes siquiera de escribir el código del sistema.

¿Qué tiene que ver un documento funcional (**Gherkin**) con los tests que programen los desarrolladores para luego verificar su código (**BDD**)?

Allí es donde entra **Cucumber**.

## ¿Qué es Cucumber?

<figure>
  <img class= thumbnailshadow src=cucumber.png alt="Cucumber logo"/>
  <figcaption>Cucumber logo</figcaption>
</figure>

**Cucumber** o Pepino en su traducción al español (sí, le pusieron así para hacer el juego entre **Gherkin** y **Cucumber**, ahora puede que entiendas por qué el artículo tiene una foto de pepinos…) es una herramienta creada por **Aslak Hellesøy** que ayuda a los desarrolladores a programar bajo la metodología **BDD** en distintos lenguajes, haciendo uso de tests redactados en **Gherkin**, lo sé, todo muy confuso quizás, veamos a qué me refiero con esto.

Como vimos en nuestro ejemplo sobre la funcionalidad de blogs en **Gherkin**, podemos decir que al final del día estamos describiendo el comportamiento del usuario en ciertos escenarios, es decir, que cada uno de esos ejemplos sería un posible camino o situación experimentada por un usuario, teniendo entonces estrecha relación con el “comportamiento” mencionado por **BDD** (Desarrollo Guiado por Comportamiento). Pero ¿Cómo conectan los desarrolladores ese comportamiento descrito en **Gherkin** con tests que les ayuden a probar el sistema?

Con **Cucumber**!

Veamos un ejemplo con pseudocódigo para que se hagan una idea:
<figure>
  <img class= thumbnailshadow src=cucumber_aplicado_a_gherkin.png alt="Cucumber aplicado a Gherkin"/>
  <figcaption>Cucumber aplicado a Gherkin</figcaption>
</figure>

Gracias a **Cucumber** todos los escenarios que redactamos en nuestro Gherkin ahora serán plantillas para disparar tests automatizados, convirtiendo cada oración de nuestro escenario en algo llamado “Step” o paso y asignandole a este paso se una secuencia de acciones/funciones llamadas “Sub Steps” o sub pasos que por detrás ejecutan código.

Ahora los desarrolladores podrán convertir los escenarios de Gherkin en disparadores de tests que corroboren que cada oración (Step) se cumpla, es decir, cuando se corra el test asociado al escenario “**Pepe publica en el blog de un usuario**” y se ejecute la oración o step “**Dado que estoy logueado como Pepe**” se esperá que el script corra un cierto código haciendo uso del sistema que implique **loguear exitosamente a un usuario administrador**, sí el script falla, el step falla y la condición no se cumple, haciendo así que falle el escenario y por consecuencia, falla el test.

En el caso de que todos los Steps (Dado, Cuando, Entonces) se ejecuten exitosamente, entonces el desarrollador habría logrado cumplir con el requerimiento expresado en dicho escenario.

## Uniendo Gherkin + BDD + Cucumber
<figure>
  <img class= thumbnailshadow src=bdd_flow.png alt="BDD Flow"/>
  <figcaption>Flujo BDD</figcaption>
</figure>

Entendido entonces todo lo anterior, comprendemos que el flujo de desarrollo en un paradigma de BDD sería el que se enseña en la imagen.

1: **Se describe el comportamiento**: Etapa en donde se realizaría la reunión de los tres amigos para discutir la funcionalidad del sistema ejemplificando con escenarios que resulten en la redacción de un documento redactado en Gherkin. (Tarea llevada a cabo por el PO, desarrolladores y testers)
2: **Se escriben las definiciones de los Steps**: es decir el contenido de scripts que va a asegurar que nuestro sistema esté haciendo lo que debería hacer teniendo en cuenta el comportamiento del usuario (Tarea llevada a cabo por desarrolladores)
3: **Estos tests automatizados son corridos por los desarrolladores** y van a fallar porque todavía no se escribió el código que logre que estas pruebas pasen.
4: **Los desarrolladores escriben el código hasta lograr crear la nueva funcionalidad** que cumple con los requisitos expresados en Gherkin.
5: **Se corren los tests nuevamente y ahora los tests que fallaban al comienzo se ejecutan exitosamente** al haberse logrado la funcionalidad deseada.
¿En que nos ayuda este paradigma o modelo?

Dependiendo de si empleabas algo como **TDD** o no, podías guiar tu desarrollo a partir de pruebas, pero la realidad es que aunque guíes tu desarrollo a partir de pruebas, no podes estar seguro de estar creando el sistema correcto, ya que tus pruebas solo están verificando que tu código funcione acorde a lo que vos entendiste de los requerimientos. A partir de emplear **BDD**, tus pruebas tienen un sentido y es conseguir que el usuario logre realizar ciertos steps o pasos y logre ciertos resultados en consecuencia, centrando el desarrollo en el usuario.

Pero todo lo que aprendemos en la teoría, luego puede cambiar en la práctica…

## ¡Cambio de paradigma!
<figure>
  <img class= thumbnailshadow src=cambio_de_paradigma.png alt="Cambio de paradigma"/>
</figure>

Si llegaste hasta acá y no te estás preguntando ¿Cuando va a hablar de los frameworks de Selenium con Gherkin y Cucumber BDD, etc? Vas por el camino correcto, de lo contrario puede que seas parte del paradigma actual, déjame explicarme.

BDD no se trata de automatizar nada luego de la construcción de un sistema, todo lo contrario, se trata de automatizar las pruebas ANTES de la construcción del mismo.

Hasta este punto del artículo no hemos mencionado ninguna inferencia del tester en cuanto a programación o automatización…

¿Se hacen pruebas automatizadas? Si

¿Se busca verificar el correcto funcionamiento del sistema en cuanto a los requerimientos expresados en **Gherkin**? Por supuesto!

Pero son todas tareas que lleva adelante el desarrollador para verificar que el código que va escribiendo está cumpliendo con las condiciones expresadas en la definición del **Gherkin** creado por el equipo. No hay testers involucrados en la escritura de scripts hasta ese entonces, es una guía que ayuda al desarrollador a saber si está llevando adelante la correcta implementación del sistema que debe de crear.

Entonces ¿Por qué hoy en día vemos tanta cantidad de videos que hacen referencia a **Gherkin + Cucumber + BDD** en Testing? Por el cambio de paradigma…

Los testers nos apropiamos de estas palabras que pueden sonar “cool” para darle un uso distinto a algo que como vimos, ya tenía su uso. ¿Está mal? No, cualquiera puede usar las herramientas de la forma que desee, pero al menos entendamos el origen de todo este lío para saber la realidad detrás de todo esto.

¿Recuerdan a Aslak? ¿El creador de Cucumber? Él más que nadie quiso vincular su producto con **Gherkin** para que los equipos de desarrollo adopten su framework para guiar las pruebas en **BDD**.
<img class= thumbnailshadow src=semaphore_uncut_aslak_podcast.png alt="Episodio numero 55 del podcast Semaphore Uncut"/>

En el [episodio numero 55](https://semaphoreci.com/blog/aslak-hellesoy-cucumber?ref=ignaciosambrailo.com) del podcast [Semaphore Uncut](https://semaphoreci.com/?ref=ignaciosambrailo.com) hace mención a este cambio:

>BDD y TDD no se trata de probar el código existente, se trata de diseñar un código que aún no se ha escrito. Eso es realmente difícil de entender para mucha gente, especialmente para no desarrolladores, porque tenés que ser programador para entender estos conceptos

Si bien puede sonar fuerte, es verdad que entender cómo funciona algo como BDD y TDD es difícil para las personas que no programan, al no terminar de poder experimentar los conceptos en la práctica, pero no quedó allí, también mencionó:

>La gente que lo adoptó en aquel entonces, eran testers. Gente que tradicionalmente había estado haciendo Testing manual ahora estaba adoptando **Cucumber** como una forma de automatizar sus tests. Y allí fue cuando comenzamos a ver el primer **cambio de paradigma**, ya que como dije antes **TDD** y **BDD** no se trata de Testing. Y al mismo tiempo, la gente empezó a usar Cucumber con herramientas de automatización de navegadores como **Selenium** webdriver.

Podemos entender la frustración de Aslak viendo como un producto creado con el propósito de ser empleado en **BDD** se desvirtuó completamente, y por si no queda claro a qué se refiere Aslak, allí vamos!

## La realidad de BDD en el Testing
Es conceptualmente imposible aplicar **BDD** en Testing, al menos de la forma en la que se lo implementa, si “creamos las pruebas que guían el desarrollo” luego de haber desarrollado ya no estaríamos guiando el desarrollo, estaríamos simplemente probando.

Volviendo al flujo de BDD tendríamos algo como esto:
<figure>
  <img class= thumbnailshadow src=flujo_bdd_testing.png alt="Versión de BDD en Testing"/>
  <figcaption>Versión de BDD en Testing</figcaption>
</figure>

1: La aplicación es construida por los desarrolladores bajo alguna metodología.
2: El tester describe el comportamiento de la aplicación basándose en el **comportamiento ya existente** o en los requisitos de los cuales se basó el desarrollador.
3: El tester programa los steps de las definiciones de **Gherkin** para probar el código **ya existente** a través de la utilización de la herramienta Cucumber.
4: El tester ejecuta los escenarios programados previamente y los tests pasan.
Esto no es lo único que se altera…

## La realidad de Gherkin en Testing

<figure>
  <img class= thumbnailshadow src=tres_amigos.png alt="Versión de BDD en Testing"/>
  <figcaption>No más reuniones de “The Three Amigos”</figcaption>
</figure>

Así como gracias a **Gherkin** planteábamos la reunión de los tres amigos, consiguiendo que todos estemos de acuerdo en los requerimientos de las funcionalidades, bueno, eso ya no es así, el desarrollo ya fue llevado a cabo y si bien podemos redactar los requerimientos en **Gherkin** para luego utilizarlo como esqueleto de nuestras pruebas automatizadas ¿Qué sentido tiene si no va a ayudar a un desarrollo de mejor calidad en base a una colaboración temprana de las 3 partes (PO, Dev, Tester)?

Lamentablemente no nos ahorraremos entonces el mal gusto cuando nos damos cuenta que el sistema no fue diseñado en base a los requerimientos adecuadamente, recién puede que nos demos cuenta cuando estemos escribiendo la documentación en **Gherkin** por nuestra cuenta que la implementación resultó en un producto distinto a lo que planteaban los requerimientos.

Podrías pensar que al menos usando **Gherkin** las pruebas quedan redactadas de forma amigable para el cliente, logrando que el mismo entienda lo que se está probando… ¿Estamos seguros?

Luego del cambio de paradigma, nuestros escenarios de **Gherkin** dejaron de verse así:
<figure>
  <img class= thumbnailshadow src=gherkin_pre_cambio.png alt="Gherkin pre cambio"/>
  <figcaption><b>Gherkin</b> antes del cambio de paradigma</figcaption>
</figure>

Para verse algo parecido a esto:
<figure>
  <img class= thumbnailshadow src=gherkin_post_cambio.png alt="Gherkin post cambio"/>
  <figcaption><b>Gherkin</b> luego del cambio de paradigma</figcaption>
</figure>

**Gherkin** luego del cambio de paradigma
¿Qué podemos notar?

1. Espanglish, y sí, no lo hice a propósito, es con lo que se van a encontrar cuando vean scripts en **Cucumber** y no, no hace falta que estén escritos en inglés, pero lo están, incluso cuando **Cucumber** soporta muchísimos idiomas, entre ellos el español.
2. Se hace énfasis en la UI (Interfaz de Usuario) en lugar de al comportamiento del usuario como se hacía en el primer ejemplo.
3. Se hace uso de tecnicismos al estar asociado a eventos que van a ocurrir dentro de una interfaz y qué están relacionados estrechamente al cómo y no al qué.
4. Se extiende el tamaño del escenario, al querer explicar todo lo que hace nuestra prueba, cómo si ese fuese el propósito de **Gherkin**, construyendo algo similar a un caso de prueba. Se peca de sobrescribir cada pequeño paso que se realiza, pudiendo este ser parte de un sub paso.
5. La cantidad de repetición aumenta, más oraciones van a ser reescritas y con ello la dificultad de mantenimiento a la hora de modificar un caso debido a un cambio en la implementación del sistema.
Entendemos entonces que no es sólo un tema de preferencias y de utilizar las herramientas para lo que fueron creadas, sino que realmente trae puntos negativos a algo tan sensible como la creación de un proceso de pruebas automatizadas.

## ¿Por qué no cambiamos nuevamente?
De por sí es complicado entender cómo llegamos acá en un principio, habría que analizar cuáles son las causas por las que estamos acá en un inicio y en mi opinión son las siguientes:

Reportería: La reportería juega un gran rol en Testing, demostrar qué hacemos en nuestro trabajo es un punto de dolor que como testers tenemos que solventar, para así justificar el tiempo invertido en las tareas que realizamos. **Cucumber** nos ayuda a generar reportería, por si solo o complementado con otras herramientas, lo cual ayuda a mostrar tanto el trabajo cómo un análisis de forma natural.
Desconocimiento: Nadie nace sabiendo, y nadie aplica “**Gherkin + Cucumber + BDD**” habiendo investigado su origen, por lo tanto atribuyo parte del problema a la falta de investigación de los equipos antes de sumergirse en una solución que puede no ser lo que creían. La mayoría de los testers aprendemos de alguien más, y si ese alguien más tampoco conoce la imagen completa, estaremos destinados a seguir su camino.
Darnos a entender: En Testing sucede algo parecido a lo que sucede en desarrollo, cuando un tester se va o cuando un nuevo tester ingresa, queremos que el ingresante o reemplazante sepa con más claridad que es lo que están haciendo nuestras pruebas, pero no por eso el desarrollador pone un comentario por cada línea y no por eso debería el tester explicar cada clic que realiza sobre una UI en un Gherkin.
## Para concluir…
Existen formas en las cuáles podemos utilizar Gherkin y **Cucumber** para crear un framework de Testing automatizado que tenga sentido, aunque esto podría ser abordado en otro artículo dependiendo de qué tan bien recibido sea el actual.

Me encantaría que dejen un comentario con su mirada, crítica o consejo acerca del tema y juntos sigamos construyendo una mejor comunidad de Testing cada día.

Un abrazo grande, Nacho.