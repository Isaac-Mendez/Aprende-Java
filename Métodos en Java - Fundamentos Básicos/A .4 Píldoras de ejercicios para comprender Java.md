## 1. Introducción a los principios de la programación orientada a objetos

Hoy descubrirás un mundo nuevo e interesante. El mundo de la Programación Orientada a Objetos ( **POO** ). Previamente aprendiste sobre clases y objetos. Hoy aprenderás más sobre ellos, mucho más.

OOP surgió como una respuesta a la creciente complejidad de los programas. Cuando las variables y los métodos en los programas comenzaron a contarse por decenas de miles, quedó claro que había que hacer algo. Una solución fue combinar datos y métodos asociados en objetos separados.

Ahora los programadores tenían que describir por separado cómo interactúan los objetos externamente y cómo se comportan internamente. Esto hizo mucho más fácil entender y escribir programas. Sin embargo, quedaba una pregunta: ¿qué métodos deberían ser internos para un objeto y cuáles deberían estar disponibles para otros objetos?

Se intentaron muchos enfoques. Y en base a las mejores prácticas descubiertas, surgieron 4 principios de programación orientada a objetos . Son abstracción, encapsulación, herencia y polimorfismo . Anteriormente, solo había tres, pero luego los expertos decidieron agregar también la abstracción.

---

## 2. Abstracción

La gente en Internet todavía discute sobre la definición de abstracción en programación orientada a objetos . El problema no es que todos estén equivocados. Es que todos tienen razón . Cuanto más pequeño es un programa, más abstracción está ligada al lenguaje Java. Cuanto más grande es un programa, más abstracción está ligada al modelado/simplificación de objetos del mundo real.



Pero las mejores mentes parecen estar de acuerdo en que:

La abstracción es el uso de solo aquellas características de un objeto que lo representan con suficiente precisión en un programa. La idea principal es representar el objeto con el conjunto más pequeño de campos y métodos que simultáneamente permitan que sus tareas se resuelvan con suficiente precisión .

En Java, la abstracción se logra a través de clases e interfaces abstractas.

**Abstracción en la vida real**

Un buen ejemplo de abstracción en la vida real son las descripciones de puestos en una empresa u organización. El título de un puesto es una cosa, pero las responsabilidades específicas asignadas a un puesto son un asunto completamente diferente.

Imagina que estás diseñando la estructura organizativa de tu futura empresa. Puede dividir las responsabilidades de la secretaría, distribuyéndolas en varios puestos diferentes. Puede dividir el puesto de CEO en varios puestos separados: CFO, CTO, CMO, HR Director. O, por ejemplo, puede combinar los puestos de gerente de oficina y reclutador en uno.

Usted piensa en títulos de trabajo y luego divide las responsabilidades de estos puestos. La abstracción es romper con el objeto como un todo y seleccionar las propiedades y componentes esenciales que necesitamos.

![Introducción a los principios de la programación orientada a objetos.  Abstracción](https://cdn.codegym.cc/images/article/509b2235-856c-4ab5-b35a-53a61a0c0dec/1024.webp)

Desde el punto de vista de la programación, la abstracción es **la correcta división de un programa en objetos** . Por lo general, hay docenas de formas de representar cualquier programa grande como objetos que interactúan. La abstracción le permite seleccionar las características esenciales e ignorar las no esenciales.

---

## 3. Encapsulación

El objetivo de la encapsulación es mejorar las interacciones simplificando los objetos.

![](https://cdn.codegym.cc/images/article/b932b444-6d08-49fd-910a-c774b8f9ff8a/1080.webp)

Y la mejor manera de simplificar algo es esconder cualquier cosa complicada de miradas indiscretas. Por ejemplo, si lo colocan en la cabina de un avión jumbo de Boeing, no comprenderá de inmediato cómo operarlo:

![](https://cdn.codegym.cc/images/article/3d320793-a7e3-4eee-a7d5-9397257798d3/1024.webp)

Pero para los pasajeros del avión todo es más sencillo: compras un billete y te subes al avión, que despega y luego aterriza. Puede volar fácilmente de un continente a otro con solo la capacidad de "comprar un boleto" y "subirse a un avión". Toda la complejidad de preparar la aeronave para el vuelo, despegue, aterrizaje y diversas situaciones de emergencia está oculta para usted. Por no hablar de los centros de navegación por satélite, piloto automático y control de tráfico aéreo. Y esto nos simplifica la vida.

Desde el punto de vista de la programación, la encapsulación es "ocultar la implementación". Me gusta esta definición. Nuestra clase puede contener cientos de métodos e implementar comportamientos muy complejos en diversas situaciones. Pero podemos ocultar todos sus métodos de miradas indiscretas (marcándolos con el modificador privado), y dejar solo dos o tres métodos para interactuar con otras clases (marcándolos con el modificador público). Entonces, todas las demás clases de nuestro programa solo verán los tres métodos públicos y los llamarán pero no a otros. Y toda la complejidad estará oculta dentro de la clase, al igual que la cabina está oculta para los felices pasajeros.

---

## 4. Herencia

Hay dos lados a la herencia . Herencia en programación y herencia en la vida real. En programación, la herencia es una relación especial entre dos clases . Pero la herencia en la vida real es mucho más interesante.

Si necesitamos crear algo en la vida real, tenemos dos opciones:

1. Crear lo que necesitamos desde cero, dedicando mucho tiempo y esfuerzo.
2. Crear lo que necesitamos en base a algo que ya existe.

La estrategia óptima es esta: tomar una buena solución existente, modificarla un poco, ajustarla para que se ajuste a nuestras necesidades y luego usarla.

Si rastreamos la historia humana hasta sus inicios, descubrimos que han pasado miles de millones de años desde que comenzó la vida en el planeta. Pero si consideramos que el punto de partida de los humanos son nuestros ancestros primates (es decir, los humanos están "basados ​​en" ancestros primates), entonces solo han pasado un par de millones de años. Construir desde cero lleva más tiempo. Mucho mas largo.

En programación, puedes hacer algo similar creando una clase basada en otra. La nueva clase desciende (hereda) de la clase existente. Esto es muy beneficioso cuando una clase existente tiene entre el 80 y el 90 % de los datos y métodos que necesitamos. Simplemente declaramos la clase apropiada como padre de nuestra nueva clase, y todos los datos y métodos de la clase padre aparecen automáticamente en la nueva clase. Conveniente, ¿verdad?

---

## 5. Polimorfismo

El polimorfismo es un concepto de programación. Describe una situación en la que diferentes implementaciones están ocultas detrás de una sola interfaz. Mirando a la vida real en busca de una contraparte, encontramos que operar un vehículo es una buena opción.

Si alguien puede conducir un camión, también puede ponerse al volante de una ambulancia o al volante de un automóvil deportivo. Una persona puede manejar un automóvil, independientemente del tipo de automóvil, porque todos los automóviles tienen la misma interfaz de control: volante, pedales y palanca de cambios. Las partes internas de los autos son diferentes, pero todos tienen la misma interfaz de control.

Volviendo al mundo de la programación, el polimorfismo permite acceder de la misma forma a objetos de diferentes clases (que suelen tener un ancestro común), una propiedad cuyo valor difícilmente se puede exagerar. Su valor aumenta a medida que el programa crece.

OOP significa principios. leyes internas. Cada uno de ellos nos **limita** de alguna manera, pero brinda grandes beneficios a cambio cuando el programa se hace grande. Los cuatro principios de la programación orientada a objetos son como las cuatro patas de una mesa. Quita uno y todo el sistema se vuelve inestable.