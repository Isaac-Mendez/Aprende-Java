
#   

## 1. Objetos

Todo en Java es un objeto.

Más exactamente, hay muy pocas cosas en Java que no sean objetos. Por ejemplo, tipos primitivos. Pero esta es una excepción bastante rara a la regla.

Entonces, ¿qué es un objeto?

Un objeto es **una entidad que agrupa datos junto con métodos que procesan los datos** . Cuando decimos "datos", nos referimos a variables, por supuesto.

Las variables de un objeto se denominan "datos" o "estado".

Se dice que los métodos de un objeto son su "comportamiento". Es costumbre cambiar el estado de un objeto (variables) solo usando los métodos de ese objeto. Cambiar las variables de un objeto directamente (sin usar sus métodos) se considera de mala educación.

**Cada objeto** , así como cada variable, **tiene un tipo** . Este tipo se determina una vez cuando se crea el objeto y no se puede cambiar en el futuro. **El tipo de un objeto es su clase.**

Cada objeto tiene su propia copia de variables de instancia (campos). Si se declara una variable int a no estática en una clase y su programa crea 10 objetos de esa clase, entonces cada objeto tendrá su propia variable int a.

**Interactuando con un objeto**

La forma más conveniente de trabajar con un objeto es almacenar una referencia a él en una variable y luego llamar a métodos en esa variable. Esto te resultará familiar:

```java
variable.method()
```

Where `variable`es una variable que almacena una referencia a un objeto y `method`es un método de esa clase.

Si desea hacer referencia a un campo (variable) de un objeto, también debe usar el operador de punto :

```java
variable.field
```

Donde `variable`es una variable que almacena una referencia a un objeto y `field`es una variable de instancia (campo).



---

## 2. `new`operador

Para crear un objeto de cierta clase, debe usar el `new`operador. En general, esto es lo que parece crear un objeto:

```java
Class variable = new Class(arguments);
```

Donde `Class`está el nombre de la clase de la `variable`variable así como el nombre de la clase del objeto a crear. Y `variable` es una variable que almacena una referencia al objeto creado. Y `arguments`es un marcador de posición para una lista de argumentos separados por comas pasados ​​al constructor.

La lista específica de argumentos que se pueden pasar la deciden los programadores que escriben la clase.

Ha creado objetos antes e incluso ha utilizado esta construcción en particular. No lo has olvidado, espero.

```java
Scanner console = new Scanner(System.in);
int x = console.nextInt();
```

`Scanner console`— esto crea una `console`variable cuyo tipo es `Scanner`. — esto crea un nuevo objeto. Y el operador de asignación establece la variable igual a una referencia al objeto recién creado.`new Scanner(System.in)``Scanner``console`

En la segunda línea, llamamos al `nextInt()`método en el `Scanner`objeto, utilizando la `console`variable, que almacena una referencia al `Scanner`objeto.

Ejemplos de creación de objetos:

|Código|Descripción|
|---|---|
|```java<br>String s = new String("Hello");<br>```|Crear un `String`objeto|
|```java<br>Scanner console = new Scanner("");<br>```|Crear un `Scanner`objeto|
|```java<br>int[] data = new int[10];<br>```|Crear un `int[]`: un contenedor de `10` `int`elementos|

Los objetos creados se denominan objetos de la clase o instancias de la clase , mientras que la clase se denomina clase del objeto . Por ejemplo, la `s`variable almacena una referencia a una instancia de la `String`clase.

---

---

## 3. Introducción a las clases

Creo que ya has visto lo conveniente que es usar clases escritas por otros programadores. Pero, ¿qué hay de escribir tus propias clases?

¿Cómo sabes cuándo y dónde necesitas tu propia clase y cómo hacer una?

Los programadores suelen crear sus propias clases cuando quieren incorporar una nueva entidad al programa. ¿Suena confuso? Luego trataré de explicar, pero voy a empezar desde muy lejos.

**grupo de datos**

Simplificando un poco, podemos decir que un objeto en Java es un bloque de memoria que contiene las variables declaradas en una clase (campos de instancia). O, en otras palabras, variables combinadas en un grupo.

Digamos que su programa necesita almacenar las coordenadas de `100`los puntos y necesita un método para mostrarlos en la pantalla. Esto se puede hacer usando arreglos. Por ejemplo, así:

```java
class Solution
{
   public static void printPoints(int[] x, int[] y, int[] color)
   {
     for (int i = 0; i < x.length; i++)
       System.out.println("Color of (" + x[i] + ", " + y[i] + ") = " + color[i]);
   }

   public static void main(String[] args)
   {
     int[] x = new int[100];
     int[] y = new int[100];
     int[] color = new int[100];
     printPoints(x, y, color);
   }
}
```

Sería mucho más conveniente si tuviéramos un solo tipo para almacenar toda la información sobre un punto: `x`, `y`, `color`. Si tal tipo no existe en Java, puede crearlo usted mismo.

Para hacer esto, escribiremos código para una `Point`clase:

```java
public class Point
{
   public int x;
   public int y;
   public int color;
}
```

Ahora el código anterior se puede reescribir como:

```java
class Solution
{
   public static void printPoints(Point[] points)
   {
     for (int i = 0; i < points.length; i++)
       System.out.println("Color of (" + points[i].x + ", " + point[i].y + ") = " + points[i].color);
   }

   public static void main(String[] args)
   {
     Point[] data = new Point[100];
     for (int i = 0; i < data.length; i++)
       data[i] = new Point();
     printPoints(data);
   }
}
```

Ahora agreguemos un método a la `Point`clase que mostrará información sobre el objeto:

```java
public class Point
{
   public int x;
   public int y;
   public int color;
   public void print()
   {
     System.out.println("Color of (" + x + ", " + y + ") = " + color);
   }
}
```

Ahora la `Solution`clase se ve así:

```java
class Solution
{
   public static void printPoints(Point[] points)
   {
     for (int i = 0; i < points.length; i++)
       points[i].print();
   }

   public static void main(String[] args)
   {
     Point[] data = new Point[100];
     for (int i = 0; i < data.length; i++)
       data[i] = new Point();
     printPoints(data);
   }
}
```

Ocultamos hábilmente las coordenadas del punto y la información de color dentro de la `Point`clase junto con el método que muestra el estado del punto.

Las clases son una forma de gestionar la complejidad del programa. Un programa grande se vuelve menos complejo cuando se divide en muchas clases pequeñas.

---

## 4. Objetos mutables vs inmutables

Érase una vez, estudiamos constantes en Java y llegamos a una conclusión que no es muy reconfortante. Las constantes le permiten proteger las variables para que no se cambien, pero no pueden evitar cambios en los objetos a los que se refieren.

Para resolver este problema, a Java se le ocurrieron objetos constantes. O, como se les llama con más frecuencia, objetos inmutables.

Por cierto, ya conoces esa clase, cuyos objetos no se pueden cambiar: `String`. Un `String`objeto permanece para siempre sin cambios después de que se crea. ¿Y cómo lograron esto los creadores de Java?

Primero, todas las variables de la `String`clase están ocultas, es decir, declaradas `private`.

En segundo lugar, no puede heredar la `String`clase: su declaración de clase incluye el `final`modificador.

En tercer lugar, y lo más interesante, todos los métodos de la `String`clase, que, en teoría, esperaría cambiar el objeto existente, en realidad no lo cambian, sino que devuelven uno nuevo.

Por ejemplo, el `toUpperCase()`método convierte todas las letras de la cadena en mayúsculas. Pero en lugar de cambiar el objeto sobre el que se llama al método, devuelve un nuevo `String`objeto que consta de letras mayúsculas:

```java
String text = "This is a very important message";
String message = text.toUpperCase();
```

Esto es lo que quedará en la memoria después de ejecutar este código:

![Objetos mutables vs inmutables](https://cdn.codegym.cc/images/article/e238e9d6-08a0-4311-97db-312fa0976ff0/1024.webp)

Así que siéntete libre de pasar tus cadenas a cualquier método: nadie las cambiará.