---
date: 2024-05-20
title: ¿Existe el Testing Automatizado?
description: Si bien un script puede ejecutar flujos de forma automática, esto no es ni de cerca el trabajo que realiza un Tester. Los resultados de dichas automatizaciones pueden servir en parte para aumentar el nivel de confianza en un sistema, pero incluso si los resultados dieran OK ¿Podríamos estar seguros que no existen errores dentro de nuestro sistema? No, ya que es imposible automatizar cada aspecto de nuestro trabajo.
summary: Si bien un script puede ejecutar flujos de forma automática, esto no es ni de cerca el trabajo que realiza un Tester. Los resultados de dichas automatizaciones pueden servir en parte para aumentar el nivel de confianza en un sistema, pero incluso si los resultados dieran OK ¿Podríamos estar seguros que no existen errores dentro de nuestro sistema? No, ya que es imposible automatizar cada aspecto de nuestro trabajo.
---

Seamos sinceros, tal como lo dice el título ¿Existe la posibilidad de automatizar el proceso de Testing?

La primera pregunta que me hago es ¿A qué llamamos Testing? Ya que dependiendo del concepto que cada uno tenga, la respuesta puede ser una u otra.

Hay varias definiciones, es cosa buscar y quedarse con la que uno cree que mejor representa su trabajo. En mi caso me quedo con una definición combinada: “Testing es aprender del producto en nombre de otras personas, para evitar que les ocurran problemas a ellos y a las personas que le importan, a su vez, su resultado debe ser poder comunicar el estado del producto a demanda”.

Ahora ¿Puedo aprender de forma automatizada por otras personas? No, si bien hoy en día cada vez más escuchamos acerca de la “inteligencia artificial”, actualmente los seres humanos somos los únicos capaces de relacionar y contextualizar diversos tópicos de los cuales se compone un proyecto para aprender de diversas fuentes de forma efectiva.

Y qué hay de ¿Comunicar el estado del producto a demanda? Acá está el problema, si bien un script puede ejecutar flujos de forma automática, esto no es ni de cerca el trabajo que realiza un Tester. Los resultados de dichas automatizaciones pueden servir en parte para aumentar el nivel de confianza en un sistema, pero incluso si los resultados dieran OK ¿Podríamos estar seguros que no existen errores dentro de nuestro sistema? No, ya que es imposible automatizar cada aspecto de nuestro trabajo.

Nosotros, como Testers sabemos que nuestras automatizaciones no cubren todo el sistema e incluso si lo hiciera, corremos el riesgo de haber cometido errores en nuestro código, es una paradoja, escribimos código que pruebe otro código para chequear el correcto funcionamiento del mismo, pero ningún código chequea el comportamiento de nuestro código, es un problema sin fin.

De todos modos alguien podría decir algo como… “se están apretando cosas automáticamente y chequeando sus resultados, eso es lo que haría un tester, por eso se le llama Testing automatizado”. (Es uno de los muchos ejemplos de automatizaciones)

¿Es esto cierto? Según mi definición, eso no es Testing, no estoy aprendiendo nada del producto ni estoy seguro de poder comunicar el estado del mismo basándose única y exclusivamente en el resultado de dichas automatizaciones. 

Pero debo reconocer que para mucha gente hacer Testing no es más que chequear outputs de un sistema, en esa concepción podría llegar a tener sentido, pero incluso así, recordemos el punto anterior, ningún código chequea el comportamiento de nuestro código, por lo tanto podemos tener errores automatizados.

Ahora, si un script realiza chequeos automáticos por nosotros ¿Es eso Testing Automatizado incluso bajo una concepción errónea de nuestro trabajo? Yo creo que no, ya que aún cuando un Tester decide automatizar un proceso, no es algo tan simple como “me gustaría chequear flujos de forma automática” y pum aparece un script milagrosamente.

Se necesita hacer un análisis del sistema a ser “automatizado”, analizando no solo el tiempo que te ahorraría la automatización, sino también los riesgos que esta conlleva, elección de un framework, análisis de la solución, documentación de la misma, su mantenimiento, su escalabilidad, su viabilidad, relación tiempo de desarrollo vs valor generado, entender si es el momento adecuado para el desarrollo de la misma, disponibilidad para su desarrollo, entre las que se me ocurren ahora mismo.

La resolución de todas las tareas anteriormente mencionadas serían realizadas por el Tester a cargo del área en un proyecto. Suponiendo que finalmente se crearon las automatizaciones deseadas ¿Significa entonces que prescindimos del Tester ya que su trabajo ya está automatizado? No…

Incluso cuando se hagan chequeos automáticos, hay que saber interpretar y analizar los resultados, los sistemas cambian, por lo tanto habría que realizar cambios en el código, si el sistema no cambiase no haría falta automatizar nada ya que el sistema sería una constante y no tendría sentido automatizar chequeos sobre algo estático.

¿Estoy admitiendo entonces que eso es Testing automatizado? Como habrás notado a lo largo de mi descargo, siempre me referí al resultado de la automatización como “chequeos” es decir, corroboraciones que hace un script automáticamente, como lo pueden ser “X cosa es igual a Y cosa”, o “X cosa es mayor que Y cosa”.

Eso es todo, chequeos, y son muy útiles, realizar chequeos automáticamente que de otra forma nos demandarían mucho tiempo, es genial ¿Por qué? Porque nos libera tiempo para poder centrarnos en cosas más profundas o importantes que van más allá de verificar outputs como máquinas.

Volvamos al eje de la discusión una vez más, esta vez con una analogía, supongamos que un jardinero corta el pasto con una máquina de cortar pasto ¿Está esta persona realizando jardinería automatizada? O mejor pensemos en un desarrollador el cual recibe asistencia de una herramienta para mejorar o crear su código ¿Es esto desarrollo automatizado? Creo que ven cual es el punto.

Que una herramienta te ayude en parte de tu trabajo, no significa que te reemplace ni que haga el trabajo por vos, simplemente son eso, herramientas que te facilitan trabajos, ni más ni menos. El trabajo que automatizan no es el Testing per se, es un aspecto del Testing.

Como conclusión quiero que te lleves que el Testing no es automatizable en mi opinión, generar conocimiento y relevar el estado de un producto a demanda no es algo que pueda hacer una máquina hoy en día, sin embargo, creo que existe un gran valor en la creación de  herramientas que nos pueden servir a los Testers para hacer nuestro trabajo más eficiente o eficaz.

Si bien solamente les hablé de automatizaciones para chequeos, las automatizaciones existen para muchas más cosas, así como lo pueden ser la generación de datos y la obtención de los mismo, tema que puede que trate en otro post.

Hay que revalorizar nuestro trabajo, sin venderlo como algo reemplazable por una máquina, sino como algo que se apoya en máquinas para realizar un trabajo más completo.

El valor siempre va a estar en la capacidad que tenga un Tester de usar su cerebro para ser crítico con un sistema, encontrar esos huecos funcionales, esos detalles que a uno le generan un ruido interno, esas intuiciones que lo llevan a descubrir errores, esa experiencia que lo ayuda a evitar tropezar con rocas del pasado. No dejemos que nuestro trabajo sea visto como un mero chequeo automatizado.

Abrazo grande y buen Testing!