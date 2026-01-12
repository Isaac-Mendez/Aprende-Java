
## 1. Historia de la empresa

Quiero contarles una historia que demuestra cómo la programación orientada a objetos ayuda a combatir la complejidad de los grandes sistemas. Esto es necesario para que comprenda el propósito de la programación orientada a objetos .

Érase una vez una pequeña empresa que brindaba servicios de transporte intergaláctico...

Llamémoslo Galaxy Rush. Daba empleo a 5 personas. Uno trabajaba en finanzas, el segundo trabajaba en un almacén, el tercero hacía las entregas, el cuarto manejaba la publicidad y el quinto administraba toda la empresa.

Eran muy trabajadores y tenían éxito en todo. La empresa tenía una buena reputación y ganaba mucho dinero. Pero cada año había más y más pedidos, por lo que el jefe tuvo que contratar empleados adicionales. Varios más para el almacén, varios más para entregas, uno más para finanzas y un experto en publicidad adicional para ampliar la participación de mercado de la empresa.

Y fue entonces cuando empezaron los problemas. Había **más gente** , y **empezaron a estorbarse unos a otros.**

El comercializador gasta drenajes de la cuenta bancaria en una nueva campaña publicitaria, por lo que no hay dinero para comprar productos que necesitan ser enviados con urgencia.

El almacén tiene 10 hiperunidades nuevas que se envían a un cliente una vez al mes. Un mensajero voló y se llevó una hiperunidad para un cliente diferente, lo que provocó que el pedido normal de 10 hiperunidades se retrasara un mes. El primer mensajero simplemente no sabía que el segundo mensajero estaba llenando el otro pedido.

El nuevo asistente del gerente envía un mensajero en una nave espacial para comprar más bienes. Mientras tanto, todos los demás esperan a que aparezca una nave espacial disponible. Hay toneladas de entregas urgentes, pero esta asistente solo supervisa las compras y **está tratando de hacer bien su trabajo.** Cuanto mejor realiza un empleado sus deberes, más interfiere con el trabajo de los demás.


Al analizar la situación, el jefe se da cuenta de que recursos importantes como la nave espacial, el efectivo y los productos no se están utilizando de manera óptima. En cambio, están sujetos a la regla "si duermes, pierdes". Cualquier empleado podría tomar un recurso que todos los demás necesitan para su trabajo, poniendo así en peligro a los demás empleados y a la empresa en su conjunto.

Había que hacer algo, por lo que el jefe decidió dividir la empresa monolítica en unos pocos departamentos. Creó un departamento de envíos, un departamento de marketing, un departamento de adquisiciones, un departamento de finanzas y un departamento de inventario. Ya nadie podía simplemente tomar la nave espacial. El jefe del departamento de envíos recibió toda la información sobre las entregas y entregó el barco al mensajero con el pedido más rentable. Además, el almacén no permitía que los mensajeros simplemente tomaran los bienes que quisieran. En cambio, recoger productos del almacén se convirtió en un proceso controlado. El departamento de finanzas no liberaría fondos para una campaña de marketing si supiera que pronto habrá una compra. Cada departamento tenía una cara pública: el jefe de departamento.La estructura interna de cada departamento era su propio negocio. Si un mensajero quería obtener productos, iba al gerente del almacén, no al almacén. Si llegaba un nuevo pedido, lo recibía el jefe del departamento de envíos ( `public-facing representative`) y no un mensajero ( `someone not authorized to interact with the other departments`).

En otras palabras, el jefe consolidó los recursos y las acciones que involucran recursos en grupos (departamentos) , y también prohibió que otros interfirieran con las estructuras internas de los departamentos. Las interacciones interdepartamentales tenían que pasar por una persona específica.

Desde el punto de vista de la programación orientada a objetos , esto no es más que dividir el programa en objetos. Un programa monolítico de métodos y variables se convierte en un programa compuesto por objetos. Y los objetos tienen variables y métodos.

El problema era que cualquier empleado podía trabajar con cualquier recurso y dar órdenes a cualquier otro empleado, todo sin supervisión ni controles. Impusimos una pequeña restricción, pero logramos más orden. Y también pudimos controlar mejor todo.

Esto es divide y vencerás en su forma más pura.

---

## 2. Cómo se crean los programas

Quiero referirme a un punto más importante que revela otra ventaja de la programación orientada a objetos . ¿Ves que los programas se parecen más a animales que a edificios? **No están construidos. Están crecidos.** El desarrollo es un cambio constante. En la construcción, puedes tener un buen plan y seguirlo con precisión. Este no es el caso con el desarrollo de software.

Muy a menudo, en la programación, no puede hacer algo de la manera que originalmente pretendía y debe volver a trabajar mucho. Los requisitos de los clientes cambian aún más a menudo.

Pero, ¿y si el cliente proporciona una especificación muy precisa? Eso empeora aún más las cosas. Eche un vistazo a lo que sucede con el producto a lo largo del tiempo.

El éxito del producto llevará al cliente a querer sacar una nueva versión, y luego otra y otra. Y, por supuesto, todo lo que necesita hacer es agregar "pequeños cambios" al producto existente. Como puede ver, el desarrollo de productos es una secuencia de cambios constantes. Sólo la escala de tiempo es diferente. Se puede lanzar una nueva versión una vez a la semana, una vez al mes o una vez cada seis meses.

¿Y qué conclusión podemos sacar de todo esto? La estructura interna del producto debe mantenerse de manera que permita realizar cambios significativos (y menores) con una mínima reelaboración.

**Cohesión de objetos**

Pero hacer eso es más difícil que decidir hacerlo. Ya dijimos que un programa consta de objetos que interactúan entre sí. Dibujemos todos los objetos de nuestro programa en la pizarra, representándolos por puntos. Y dibujemos flechas desde cada objeto (punto) a todos los demás objetos (puntos) con los que interactúa.

Ahora combinaremos los objetos (puntos) en grupos. Los puntos deben agruparse si las conexiones entre ellos son mucho más intensas que las que tienen con otros puntos. Si la mayoría de las flechas de un punto van a otros puntos de su mismo grupo, entonces los grupos se formaron correctamente. Decimos que los puntos dentro de un grupo tienen **alta cohesión** mientras que los puntos en diferentes grupos tienen menor cohesión.

**Principio de acoplamiento flojo**

Hay un "principio de acoplamiento débil". Un programa se divide en varias partes, que a menudo son capas. La lógica de estas capas/partes está fuertemente acoplada a su estructura interna y muy débilmente acoplada a otras capas/partes. Las interacciones entre capas suelen estar muy reguladas. Una capa puede hacer referencia a la segunda capa y usar solo un pequeño subconjunto de sus clases. Este es el principio de "dividir la empresa en departamentos" que vimos antes, pero a mayor escala.

El resultado es que podemos reorganizar un departamento según sea necesario para aumentar su eficacia y podemos contratar aún más personas para el departamento, y mientras no cambiemos el protocolo de interacción con nuestros otros departamentos, entonces todos los cambios realizados sigue siendo local. Nadie tiene que volver a aprender nada. No es necesario volver a trabajar en todo el sistema. Cada departamento puede hacer este tipo de optimización interna si se eligen bien los mecanismos para la interacción interdepartamental.

Bien elegido. Pero, ¿y si no se eligen bien? Entonces la **capacidad de cambio** se agota rápidamente y tendrás que rehacer todo el sistema. Esto tiene que hacerse de vez en cuando. No puede predecir el futuro, pero puede mantener el número de rehaceres al mínimo.

**Principio de abstracción**

Elegir cómo se estructuran los departamentos y cómo interactúan es el " **principio de abstracción** ". En programación, se utiliza para determinar la mejor manera de dividir un programa en partes constituyentes y cómo deben interactuar esas partes. Podemos volver a aplicar el principio, dividiendo las partes resultantes en partes, hasta que hayamos dividido el programa en clases individuales.

Ocultar la estructura interna de estas partes y limitar estrictamente las interacciones con otras partes es **encapsulación** . La encapsulación y la abstracción son las piedras angulares de OOP . Un buen programa debe seguir estos dos principios. En el futuro, veremos el resto de los principios y exploraremos qué beneficios brindan.