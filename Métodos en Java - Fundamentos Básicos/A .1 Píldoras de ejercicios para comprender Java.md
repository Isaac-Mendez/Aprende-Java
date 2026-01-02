Utilizar this. para modificar objeto de la misma clase.

En este caso, lo que hacemos es utilizar this. para modificar el valor de un atributo que está en un objeto mediante un método.

Ejemplo 

`public class Solution {
    public String name = "Amigo";
    public  String position = "Java developer";
    public  int salary = 10_000;

    public  void setPosition(String positionCambio) {
        this.position = positionCambio;
    }

    public void setSalary(int salaryCambio) {
        this.salary = salaryCambio;
    }
}`

Aquí utilizamos this. que lo que hace es modificar el atributo de un objeto. Un ejemplo es que aquí empleamos this. para cambiar el valor del atributo dentro de los métodos.

Aquí se modifica el atributo this.salary asignándole el valor del parámetro salaryCambio
