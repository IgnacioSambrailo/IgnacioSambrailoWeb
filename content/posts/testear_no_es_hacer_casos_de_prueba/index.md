---
date: 2024-06-13
title: Testear no es hacer casos de prueba
description: Nuestra industria tiene una clara obsesión con los “casos de prueba”, pero no solo eso, sino que estos casos de prueba están concebidos como el resultado de nuestro trabajo y esto se ve reflejado tanto en las expectativas de nuestros clientes como de supervisores, compañeros y gente iniciante.
summary: Nuestra industria tiene una clara obsesión con los “casos de prueba”, pero no solo eso, sino que estos casos de prueba están concebidos como el resultado de nuestro trabajo y esto se ve reflejado tanto en las expectativas de nuestros clientes como de supervisores, compañeros y gente iniciante.
---

El otro día paseaba un rato por Linkedin cuando me encontré con un post al que no voy a hacer referencia directa para evitar desviar la importancia de lo que realmente quiero exponer.

El posteo incluía una captura de pantalla de Excel que contenía una serie de casos de prueba (estos que incluyen un paso a paso de acción a realizar y resultado esperado, junto con un campo de “estado” referenciando al resultado de la prueba). Estos casos de prueba eran dirigidos a realizar un Login dentro de lo que asumo era una página web.

Inmediatamente me vinieron recuerdos relacionados a mis creencias previas a comenzar una carrera en Testing, creencias basadas en mi poco conocimiento de la profesión, sumado a la desinformación, que lejos de ser poca, abunda. Desinformación que no sólo es impartida por desconocedores del rubro, si no que también es transmitida por los mismos Testers.

¿A qué voy con todo esto? Bueno, esta persona que realizaba el posteo parecía orgullosa de haber creado un Excel en donde se describe cómo realizar un Login exitoso y uno fallido con ciertos datos de prueba, exclamando que esos eran sus primeros pasos en Testing.

No dejó de hacerme ruido y no es un ruido nuevo, para algunos puede que esto sea normal, y piensen verdaderamente que lo que está expresado en ese Excel es el resultado del trabajo del Tester y por consiguiente, pensaron que apoyar el progreso de esta persona era lo indicado.

Bueno, para bien o para mal no estoy dentro de este grupo de gente, no me malentiendan, todo aprendizaje es valorado, pero es hora de romper algunos mitos de nuestra profesión que parecen haber calado en lo más profundo de nuestra esencia.

El post en cuestión exclamaba “Diseñar casos de prueba es parte del día a día de un Tester” y creo que es una creencia común que tienen todas las personas que se inician en el sector, así como también muchas de las que ya ejercen el trabajo.

Nuestra industria tiene una clara obsesión con los “casos de prueba”, pero no solo eso, sino que estos casos de prueba están concebidos como el resultado de nuestro trabajo y esto se ve reflejado tanto en las expectativas de nuestros clientes como de supervisores, compañeros y gente iniciante.

Cuando escuchamos las razones por las cuales hay que basar nuestro trabajo en casos de prueba, todo nos lleva a la conclusión de que “es una buena práctica”, nos convencemos de que es lo correcto, entonces, partiendo de una buena intención, terminamos cediendo ante la concepción común, pero ¿Es realmente este el resultado de nuestro trabajo?

Es común pensar que sea el resultado de nuestro trabajo, después de todo, el resultado del trabajo de un programador es código ¿Verdad? Entonces el resultado del trabajo de un Tester han de ser los casos de prueba.

Hay situaciones en la que es útil tener un paso a paso de chequeos en pruebas, como por ejemplo, para luego poder automatizar dichos chequeos, de esta forma le delegamos la tarea a una máquina. O quizás deseamos realizar una prueba en la que este formato nos facilita el labor.

Después de todo, el problema no son los casos de prueba… Así como en posteos anteriores mencioné que no existe el Testing Automatizado, tampoco existe el Testing Manual cuyo trabajo parecería consistir en codificar pruebas en un idioma no programático.

Tanto automatizar, cómo diseñar casos de prueba, son herramientas disponibles a la hora de desempeñar nuestro trabajo de la mejor forma posible, el problema, como mencioné anteriormente, radica en la obsesión.

Así como automatizar no es igual a Testear, diseñar y ejecutar casos de prueba tampoco lo es.

En esta forma de percibir el Testing, hay poco de aprender, desafiar, criticar y “jugar” con el producto. ¿A qué se debe esta obsesión entonces? 

El primer motivo y el más común: la falta de confianza, los casos de prueba están estrictamente relacionados a la “evidencia”, que es una forma de “protegernos” por si algo de lo que probamos falla en un futuro, y necesitemos comprobar que las pruebas hayan cubierto el escenario. 

Nadie revisa la evidencia cuando “todo sale bien”, otro gran problema. Personalmente no veo el beneficio en evidencias de cada cosa que hacemos, ningún problema es resuelto, la evidencia no dirá quién ocasionó el problema y tampoco ayudará a arreglarlo, y aunque el escenario no hubiese sido cubierto, la calidad no es responsabilidad pura y exclusivamente del Tester.

Otro de los aparentes motivos de este enfoque; en palabras de James Bach y Aaron Hodder (“Test cases are not Testing”):

“Uno de los supuestos beneficios del enfoque basado en casos de prueba es que la consistencia y repetibilidad están asegurados”

Más tarde en el mismo artículo, Aaron muestra un experimento realizado en una clase de Testing, en dónde 6 alumnos fueron provistos de la misma serie de casos de prueba e indicaciones. Lejos de lo esperado, luego de que los alumnos ejecutaran los casos, se vió cómo todos habían obtenido resultados distintos, desmintiendo la anterior afirmación.

¿Por qué pasa esto? Según los autores, porque cada tester tiene su propio juicio y heurísticas. Es decir, incluso aunque un colega pueda entender los casos que creamos, no significa que vaya a obtener los mismos resultados, no da igual quien pruebe.

Obtener métricas es otra de las excusas, management quiere saber de X cantidad de casos de prueba, cuántos “pasaron” vs cuántos fallaron, pero aunque un reporte indique que fallaron 2/100 y otro que fallaron 14/100 ¿Cómo podemos saber en base a números qué tan importantes son los casos que fallaron? ¿Qué clase de accionable o conclusión surge de dichos números? 

Incluso cuando no se hubieran encontrado bugs ¿Podríamos estar tranquilos? ¿Acaso esto significa que nuestro producto es de gran calidad? 

Todo nos lleva a que Testing es una performance, los Testers tienen como objetivo principal encontrar bugs, pero no podemos asegurar que hayamos encontrado todos los bugs, por lo tanto, las conclusiones que un Tester pueda obtener a partir de un producto se relacionan fuertemente a su experiencia, capacidad y conocimientos.

Entonces, si el Testing depende de quién lo realiza, todo depende de la credibilidad del realizador, del Tester. No es algo tan sencillo como escribir casos de prueba ya que al final del día importa mucho más quién es el que prueba, que la prueba en sí misma.

Así como mencionan los autores previamente citados, el Testing no puede ser codificado, no podemos trasladar todo nuestro conocimiento e ideas sobre el producto a un texto explicativo. Incluso si pudiésemos, la información sería tanta que terminaría por ser inservible.

Podemos entender entonces, que un caso de prueba o test es simplemente una porción de lo que hacemos. Ya que Testing ocupa desde las etapas más iniciales del desarrollo hasta la exploración e interacción con el producto, ya sea para verificar un flujo complejo o la simple respuesta de una función.

La mayor cantidad de ejecuciones de “casos de prueba” surgen cuando un Tester está interactuando con el producto, reflexionando, probando, dudando, observando. Los problemas no están únicamente en los caminos que definimos en dichos “casos de prueba”, de hecho, si así fuera, los Testers no existiríamos en equipos cuyos desarrolladores sean tan buenos que cumplan con todos los requerimientos a la hora de entregar un desarrollo.

Aún así, nos condenamos nosotros mismos a utilizar las mismas herramientas una y otra vez sin importar el contexto. 

Si encontramos un bug en donde la secuencia de acciones que realizamos no está descrita por un caso de prueba ¿Significa que no fui tan buen Tester para redactar dicho caso? ¿O significa que estoy haciendo lo que tengo que hacer realmente pero codificar o escribir todo lo que pienso probar está entorpeciendo mi verdadero trabajo?

Mis ideas no son nuevas, el artículo que cité (“Test cases are not Testing”) es de Febrero de 2014 y aún hoy en día, esta particularidad de nuestra profesión no es desafiada o llevada a juicio, no al menos en la mayor parte de la comunidad.

En conclusión, ni los casos de prueba son malos, ni el Testing es igual a escribir y ejecutar casos de prueba. Podemos hacer un seguimiento de nuestras pruebas e ideas sin necesidad de hacer de todo una explicación, podemos Testear sin escribir un caso de prueba de cada pequeña acción que realizamos.

El miedo de no poder controlar, documentar o mostrar el resultado de cada pequeña acción que realizamos sobre un producto es entendible. La mayoría de la gente pareciera asumir que el Testing se basa en eso, si seguimos vendiendo la ilusión que los casos de prueba son Testing y no parte de Testing, entonces estamos condenados a tener que basar nuestra profesión en ellos, y que en lugar de ser una herramienta, sean nuestro trabajo:

Ejecutar, evidenciar y reportar lo que nuestros limitados casos de prueba nos dicten.