---
date: 2025-11-10
title: No solo ejecutes pruebas
description: A la hora de resolver problemas, a veces nos vemos tentados a buscar soluciones rápidamente, si bien esto puede ser útil para algunas situaciones cotidianas, no siempre lo es cuando se trabaja sobre el diseño de un programa, **dado que podemos estar resolviendo el problema incorrecto, o hasta un problema que no existe**.
summary: A la hora de resolver problemas, a veces nos vemos tentados a buscar soluciones rápidamente, si bien esto puede ser útil para algunas situaciones cotidianas, no siempre lo es cuando se trabaja sobre el diseño de un programa, **dado que podemos estar resolviendo el problema incorrecto, o hasta un problema que no existe**.
aliases:
- /no-solo-ejecutes-pruebas/
---

# Introducción

A la hora de resolver problemas, a veces nos vemos tentados a buscar soluciones rápidamente, si bien esto puede ser útil para algunas situaciones cotidianas, no siempre lo es cuando se trabaja sobre el diseño de un programa, **dado que podemos estar resolviendo el problema incorrecto, o hasta un problema que no existe**.

Como Testers, debemos aportar nuestro conocimiento en distintas fases del desarrollo de software, participando en etapas tempranas cuando sea posible. ¿Por qué querríamos probar algo que aún no existe?

Porque distinto a lo que algunos puedan pensar, Testing no se trata únicamente de ejecutar pruebas, sino también de **evitar que los errores sucedan**, y para evitar que los errores sucedan, debemos estar presentes desde un inicio, en una etapa muy lejana a la ejecución. Cabe aclarar, que **estos errores pueden ser hallados en distintos lugares**, como en definiciones, diseños, o implementaciones.

Por otro lado, algo que distingue a un principiante de alguien que tiene mayor experiencia, es su **escepticismo a la hora de encarar un nuevo desarrollo**. Mientras que el principiante tiende a hacer exactamente lo que le piden sin cuestionar nada, la persona experimentada tiende a querer entender el por qué. Y aquí es donde "probamos" aquello que aún no existe.

Poner a prueba las ideas o peticiones que llegan a un proyecto **es un acto de consciencia y responsabilidad que aumentan las posibilidades de que el mismo tenga futuro**. No debemos dar la sensación de que cuestionamos por el sólo hecho de cuestionar, esta puede ser una tarea desafiante por momentos.

## ¿Qué es "probar lo que aún no existe"?

*"Probar aquello que aún no existe"* es una forma bonita de decir *"analizar"*. **La etapa de análisis en software es el pilar del resto de etapas**, sin un buen análisis es más difícil que un proyecto tenga buenas bases para un posterior desarrollo y testeo.

Sin importar si te encontrás en un proyecto nuevo o avanzado, siempre aparecerá la necesidad de desarrollar/mejorar funcionalidades o resolver problemas. Una vez que una solicitud llega a nuestra puerta, es momento de probar aquello que aún no existe.


## ¿Cómo lo probamos?

Si bien todos hacemos análisis en menor o mayor medida, a veces conscientemente y otras no tanto... **Existen formas de guiar nuestros esfuerzos en pos de una mayor efectividad**.

A la hora de explorar un nuevo desarrollo, me gusta basar mis esfuerzos en la siguiente heurística.

La idea es **despejar la mayor cantidad de incertidumbre existente en lo que se va a desarrollar**, atacando primeramente cuestiones más abarcativas y luego más específicas.

Imaginemos entonces un círculo gigante denominado nivel 1, que contiene a su vez a un círculo menor, nivel 2, y otro círculo aún menor, nivel 3. *Podría también ser visto como las capas de una cebolla.*

<figure>
  <img class= thumbnailshadow src=img/niveles.png alt="Gherkin pre cambio"/>
  <figcaption><b>Niveles</b> de exploración<figcaption>
</figure>

Si hiciéramos el camino inverso y fuéramos de la menor incertidumbre (nivel 3) a la mayor (nivel 1), **podríamos haber desperdiciado nuestro tiempo** dado que las preguntas más abarcativas son las que más confianza aportan en saber que estamos yendo por el camino correcto.

### Nivel 1

En este nivel buscamos hacer preguntas que nos ayuden a entender si **un desarrollo tiene sentido alguno de existir, y en caso de que lo tenga, entender su urgencia e importancia**. Más precisamente, responder cuestiones como:

1. ¿Es la funcionalidad realmente necesaria?
2. ¿Estamos resolviendo o atacando el problema correcto?
3. ¿Lo estamos resolviendo de la forma adecuada?
4. ¿Qué otros problemas pueden surgir a partir de este desarrollo?
5. ¿Es el momento adecuado para este desarrollo?
6. ¿Qué tan importante es que lo desarrollemos?
7. ¿Cuánto tiempo nos podría tomar desarrollarlo/probarlo?
8. Pensar en equipos/programas externos que se puedan ver afectados por el desarrollo.

Cabe aclarar que **la intención no es hacer exactamente estas preguntas directamente a alguien**, dado que lejos de obtener respuestas útiles, vamos a causar un revuelo innecesario y poco productivo. Estas son las preguntas que nosotros debemos poder respondernos a nosotros mismos para estar más seguros de que lo que se va a desarrollar tenga sentido y bases sólidas. 

Por ejemplo lugar de hacer la pregunta número 1, podrías pensar acerca del contexto del proyecto y entender cosas como:
* Si la funcionalidad no está siendo cubierta por otra parte del programa actualmente.
* Si el problema o oportunidad que este desarrollo busca cubrir existe o es meramente una creencia infundada.
* Si es responsabilidad de este proyecto incorporar esta funcionalidad o no le corresponde.

Si alguna de estas cuestiones te genera dudas... Voilà, ya tenés algo realmente valioso para preguntar!

Cabe aclarar que para ser eficaz en este nivel es útil (no excluyente) tener un nivel de contexto, conocimiento del negocio y producto. Mientras más investigues y aprendas, más podrás aportar.

## Nivel 2

Una vez que ya nos respondimos las cuestiones del primer nivel, podemos sentirnos con más confianza y pasar a hacernos preguntas más específicas sobre el desarrollo planteado. En esta etapa buscamos:

1. Cuestionar cada una de las afirmaciones/requerimientos descritas en lo que se está solicitando (implícitas o explícitas). En caso de que no exista una buena descripción de lo que se busca desarrollar, redactarla.
2. Analizar mentalmente o mediante el uso de diagramas de flujo qué implica este desarrollo en búsqueda de entender el alcance y descubrir situaciones no contempladas.
3. Ponerse en lugar del usuario de nuestra aplicación, ya sea una persona u otro programa, ¿Cómo utilizarían esto? ¿Tienen todo lo necesario para que esto les sea de utilidad o hay algo que esté faltando?
4. Simular mentalmente o escritamente flujos que contemplen lo desarrollado, pensar en variables que puedan afectar a nuestro programa, como lo puede ser el tiempo (horario, demora) o cuestiones intrínsecas al mismo, relacionadas a su funcionamiento o negocio. ¿Qué nuevos flujos se realizan dentro de la aplicación dada esta incorporación?
5. Pensar en nuevos riesgos que surjan a partir de este desarrollo y cómo esto puede llegar a afectar a todos los involucrados (desarrollo, usuario, testing, etc).
6. Evaluar si estamos asumiendo el comportamiento de partes o funciones "nuevas", evacuando dudas y posibles problemas.
7. ¿Qué errores serán contemplados y manejados dentro de este desarrollo?
8. Tratar el diseño e implementación a alto nivel en búsqueda de consenso.

La idea es **detectar distintos errores que pudieran darse debido a información que se omite, información que no se contempla o información errónea**. 

Estos puntos debieran darnos el puntapié para hacer consultas fundadas en las respuestas que obtuvimos del primer nivel, develando ambigüedades y cuestiones que habrían sido obviadas. Siendo esta una gran oportunidad para proponer mejoras o darle solución a los "casos borde" que se presenten.

## Nivel 3

En esta instancia buscamos velar por todo aquello que debiera ser cubierto una vez que la funcionalidad esté desarrollada, no necesariamente se toca el tema a ser desarrollado en sí mismo, sino también aquellas cosas que lo rodean. Puede que el área de negocio no tenga la mayor participación.

1. Asegurarnos de estar comprendiendo el comportamiento esperado de la aplicación para evitar problemas de interpretación y discusiones futuras.
2. Abogar por la testeabilidad del producto. Por ejemplo, especificaciones claras de lo que se desarrollará, límites del desarrollo, formas de facilitar la ejecución de flujos y formas de revisión del comportamiento de la aplicación.
3. ¿Existen escenarios que no vamos a poder probar? ¿Estamos conformes con esto?
4. ¿Qué necesitaremos para poder llevar adelante nuestras pruebas? Precondiciones, ambientes, datos, configuraciones, accesos, asistencia, etc.
5. Pensar en un set de pruebas que haríamos contemplando los distintos flujos principales, involucrando cuestiones como: usabilidad, integración, gestión de errores, performance.

Este **es el momento de levantar cuestiones que pudieran interferir en nuestra misión como Testers**. Puede que también salgan a la luz cuestiones que creíamos resueltas de niveles anteriores. Al final del día, esto es práctica y experiencia, es mejor enterarnos de algo en el tercer nivel que no enterarnos.

## Finalmente

Incluso explorando los tres niveles, **es muy difícil contemplar todas las variables y estar igual de atento a todo, todo el tiempo**. Vas a encontrarte con errores que podrían haber sido evitados en cada uno de ellos. Cada proyecto tiene sus cuestiones, al final del día, todo es un problema "de personas", no de "máquinas". Lo importante es que entiendas por qué sucedió, e incorporar esa cuestión en tu próxima exploración de niveles.

Cabe aclarar que hay libros enteros dedicados al análisis en el desarrollo de software, **esto es simplemente una primer idea para que puedas empezar a desempeñarte conscientemente en la exploración de requerimientos**. La mayoría de proyectos no requieren expertos, sino personas interesadas, muchos de nosotros estamos lejos de hacer ***rocket science***.

