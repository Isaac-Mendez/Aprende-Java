## 1. Variables de referencia

En el lenguaje Java, hay dos tipos de variables: variables primitivas y todo lo demás. Da la casualidad de que ahora vamos a hablar de "todo lo demás".

De hecho, sería más correcto decir que existen **variables primitivas** y **variables de referencia** . Entonces, ¿cuáles son estas variables de referencia?

A diferencia de los tipos primitivos, cuyas variables almacenan valores directamente, las variables de referencia almacenan **referencias a objetos.** Es decir, hay un objeto en algún lugar de la memoria y la variable de referencia simplemente almacena la dirección de este objeto en la memoria (una referencia al objeto).

Solo los tipos primitivos almacenan valores directamente dentro de las variables. **Todos** los demás tipos almacenan sólo una referencia de objeto . Por cierto, ya ha encontrado dos tipos de variables de este tipo: `String`variables y variables de matriz .

Tanto una matriz como una cadena son objetos almacenados en algún lugar de la memoria. `String`Las variables y las variables de matriz almacenan solo referencias a objetos.

![Variables de referencia en Java](https://cdn.codegym.cc/images/article/338bbad0-f664-49c6-9646-f1a69a556d07/1024.webp)

`int a, int b and double d`son variables primitivas que almacenan sus valores dentro de sí mismas.

Una `String str`variable es una referencia y almacena la dirección (referencia) a un `String`objeto en la memoria.

Al asignar un valor primitivo a una variable de tipo primitivo, se copia (duplica) su valor. Al asignar una variable de referencia, solo se copia la dirección del objeto ; el objeto en sí no se copia .

---

## 2. ¿De qué se tratan las referencias?

¿Cuál es la diferencia fundamental entre las variables de referencia y las variables primitivas?

Una variable primitiva es como una caja: puede almacenar algún valor en ella. Una variable de referencia es más como una hoja de papel con un número de teléfono.

[![Java webinar](https://codegym.cc/assets/images/site/featured-content/webinar/es.png)](https://codegym.cc/s/cgu_es_webinar)

**Un auto vs llaves del auto**

Imagina que decides regalarle un coche a tu amigo por su cumpleaños. No lo envolverás en una caja y lo llevarás contigo: el coche es demasiado grande para eso.

Es mucho más conveniente presentar solo las llaves del auto en una caja lo suficientemente grande como para contenerlas. Tu amigo entenderá todo cuando saque las llaves de la caja. No hay necesidad de llevar todo el coche con usted cuando simplemente puede entregar las llaves.

**Una persona vs su número de teléfono**

O aquí hay otra comparación: una persona y su número de teléfono. Un número de teléfono no es la persona, pero se puede usar para llamarla, pedirle información o darle instrucciones.

De manera similar, una referencia se usa para interactuar con un objeto. Todos los objetos interactúan entre sí mediante referencias. En lugar de "intercambiar personas", simplemente intercambiamos números de teléfono.

Al asignar un valor a una variable primitiva, su valor se copia (duplica). Al asignar un valor a una variable de referencia, solo se copia la dirección (número de teléfono) del objeto; el objeto en sí no se copia.

Una referencia ofrece una ventaja más: puede pasar una referencia de objeto a algún método, y el método podrá modificar (cambiar) el objeto usando la referencia a él, llamando a sus métodos y accediendo a los datos dentro del objeto.

---

## 3. Asignación de referencias

Al asignar variables de referencia, solo se asigna la dirección del objeto en la memoria. Los objetos en sí mismos no aparecen ni desaparecen.

Este enfoque evita copiar grandes cantidades de memoria. Si necesita pasar un objeto muy grande a un método, simplemente pasamos la referencia del objeto y eso es todo. La referencia ocupa mucho menos espacio.

![Asignación de referencias](https://cdn.codegym.cc/images/article/2f86b0d4-a386-4925-8ac1-7b90a171f2b6/1024.webp)

El tamaño de todas las variables de referencia (independientemente de su tipo) es el mismo: 4 bytes (como un int). ¡Pero! Si su aplicación se ejecuta en una máquina Java de 64 bits, todas las referencias tendrán un tamaño de 8 bytes (64 bits).

Además, las referencias solo se pueden asignar entre sí. No puede cambiar las referencias ni asignar valores arbitrarios a las variables de referencia:

|Código|Descripción|
|---|---|
|```java<br>String hello = "Hello";<br>String s = hello;<br>```|esto está permitido|
|```java<br>String hello = "Hello";<br>hello++;<br>```|Pero esto no está permitido.|
|```java<br>String hello = 0x1234;<br>```|Y esto no está permitido|

---

## 4. Una `null`referencia

¿Y qué almacena una variable de referencia si todavía no se le ha asignado nada?

Almacena una referencia nula . `null`es una palabra clave especial de Java que significa la ausencia de una referencia (una referencia vacía). El `null`valor se puede asignar a cualquier variable de referencia.

Todas las variables de referencia lo son `null`a menos que se les haya asignado algún tipo de referencia.

Ejemplos:

|Código|Descripción|
|---|---|
|```java<br>class Person<br>{<br>   public static String name;<br>   public static int age;<br>}<br>```|La `String name`variable tiene un valor predeterminado: `null`.  <br>La `int age`variable tiene un valor predeterminado: `0`.|

Las variables locales a las que no se les ha asignado un valor se consideran no inicializadas tanto para los tipos primitivos como para los de referencia.

Si una variable almacena una referencia a algún objeto y desea borrar el valor de la variable, simplemente asígnele una referencia nula.

|Código|Descripción|
|---|---|
|```java<br>String s = null;<br>s = "Hello";<br>s = null;<br>```|`s`tiendas `null`_  <br>`s`almacena una referencia a un objeto de cadena  <br>`s`almacena `null`.|

---

## 5. Pasar referencias a métodos

Si un método tiene parámetros que son tipos de referencia , los valores se pasan al método de la misma manera que cuando se trabaja con variables que no son de referencia. Al parámetro simplemente se le asigna el valor de la otra variable.

Ejemplo:

|Código|Descripción|
|---|---|
|```java<br>class Solution<br>{<br>   public static void fill(String[] array, String value)<br>   {<br>      for (int i = 0; i < array.length; i++)<br>        array[i] = value;<br>   }<br><br>   public static void main(String[] args)<br>   {<br>     String[] data = new String[10];<br>     fill(data, "Hello");<br>   }<br>}<br>```|El `fill`llena la matriz pasada ( `array`) con el valor pasado ( `value`).|

Cuando `fill`se llama al método, al `array`parámetro se le asigna una referencia a la `data`matriz. A la `value`variable se le asigna una referencia al objeto de cadena ("Hola").

Así es como se ve la memoria **antes de llamar al** `fill` método:

![Pasar referencias a métodos](https://cdn.codegym.cc/images/article/e0055e14-3c20-4206-80ab-c5e6d3573d1d/1024.webp)

Así es como se ve la memoria **cuando el** `fill` **método se está ejecutando** :

![Pasar referencias a los métodos 2](https://cdn.codegym.cc/images/article/d166f66d-bde1-44c6-99de-d075bfca89d0/1024.webp)

Las variables `data`y `array`se refieren a (almacenan referencias a) el mismo contenedor en la memoria.

La `value`variable almacena una referencia al objeto de cadena ( `"Hello"`).

Las celdas de la matriz también solo almacenan referencias al `"Hello"`objeto.

De hecho, no se duplican objetos, solo se copian las referencias.

---

---

## 6. Comparación con el lenguaje C/C++

En las entrevistas, a veces se pregunta a los programadores de Java cómo se pasan los datos a los métodos en Java. Y a veces la pregunta es si los datos se pasan por referencia o por valor.

Esta pregunta proviene de C++, pero no es muy significativa en Java . En Java, a los parámetros siempre se les asignan simplemente los valores de los argumentos. Entonces la respuesta correcta sería " por valor ".

Pero esté preparado para **explicar su posición** , ya que puede escuchar inmediatamente la réplica: "los tipos primitivos se pasan por valor y los tipos de referencia se pasan por referencia".

Este origen de este problema proviene del hecho de que muchos programadores de Java fueron programadores de C++ en el pasado. En ese lenguaje de programación, la cuestión de cómo se pasan los parámetros a los métodos era muy importante.

En Java, todo es inequívoco: los tipos primitivos almacenan valores y los tipos de referencia también almacenan un valor: una referencia. Es una cuestión de si una variable se considera un **valor** .

En C++, una variable podría almacenar tanto una referencia a un objeto como el propio objeto. Lo mismo ocurría con los tipos primitivos: una variable primitiva podía almacenar un valor o declarar la variable como una referencia a un archivo `int`. Entonces, para evitar confusiones, los programadores de C++ siempre se refieren al objeto a una referencia como una referencia , y al objeto en sí mismo, como un valor.

En C++, fácilmente podría tener la situación en la que una variable contiene un objeto, pero la otra contiene una referencia a ese objeto. En consecuencia, la cuestión de qué almacena una variable, el objeto en sí o simplemente una referencia a él, era muy importante. Cuando se pasaba un objeto a un método, se copiaba (si se pasaba por valor) y no se copiaba (si se pasaba por referencia).

En Java, esta dualidad no existe, por lo que la respuesta correcta es: **los argumentos se pasan a los métodos de Java por valor** . Es solo que cuando hablamos de variables de referencia, este valor es una referencia.