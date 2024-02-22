# Polimorfismo

* Etimologicamnete muchas formas
* Hay dos tipos: run-tinme y compile time

## Run-time 

* Cuando una clase hija sobrecarga(override)un metodo public/protected der la clase padre.Cuando el codigo cliente llama el metodo en la clase hija, elmetodo  se "resuelve" en ese mmomento invocando el metodo sobre cargo.

class Padre {
    public voidd foo(){
        sys.out("Algo");
    }
}

class Hija{
    public void foo(){
        super.foo(); //opcional
        sys.out("Algo mas")
    }
}

* Polimorfismo permite tratar la clase hija como si fuera la padre.

Padre p = new Hija();
p.foo() -> se resuelve en un run-time e invoca Hija.foo

* Cualquier metodo visible de la clase Padre se puede acceder a traves de la Hija.

Hija h= new Hija;
   _____ 
h.|     | -> Aparece todo lo visible del Padre
  |     |
  |_____|

* Al reves no. A traves de la Padre, solo lo que es visible de la hija que es comun con la del Padre se puede acceder.

Padre p = new Hija;
   _____ 
p.|     | -> Aparece solo lo ccmun delPpadre e Hija
  |     |
  |_____|

* Algunos Lenguajes permiten crear claes abstractas que son utles para polimorfismos

//no se puede instanciar

abstract class Animal{ 
    void respirar(){
        sys.out("Respirando")
    }
    abstract void(); //no tiene cuerpo
}

//Obliga a pverride los metodos abstract

class Perro{
    void comer(){  
    }
}

* Las clases tambien permiten crear interfases. Las interfases proveen polimorfismos sin formar parte de una jerarquia.

interface Alimentable{
    void alimentar();
}

class Persona implements Alimentable{
    void alimentar();
}

## Compile-time

* La habilidad para sobre cargar(ovrerride) metodos, esdecir crear varios metodos con el mimismo nombre pero diferentes parametros.
 
 class test{
    void foo(){
    }
    void foo(int x){
    }
    void foo(strin s, int x){
    }
 }

 # Abstraccion

 * Algo propio de POO>
 * Permite modelar el problema em terminos de odjetos(odjetos de alto nivel que ocultan detalles de su implementacion).
 * Uno no interactua  con variables, procedimientos o instrcciones.

 # Punteros

 * Un puntero es una variable que almacena la direccion de memoria

 1. int()
 2. clear()
 3. long()
 + -> Estos son algunos ejemplos de "value type", son copias

 * Sin embargo los String() no son value type, es un reference type.

![Definicion de un puntero con una imagen de  referencia haciendo ilusion a la memoria](https://image.slidesharecdn.com/punteros-120105064722-phpapp01/95/punteros-2-1024.jpg?cb=1325746331)

* Ejemplo de puntero en Java

public class Persona {
    private String nombre;
    public Persona(String nombre) {
        this.nombre = nombre;
    }
    public String getNombre() {
        return nombre;
    }
    public void setNombre(String nombre) {
        this.nombre = nombre;
    }
    public static void main(String[] args) {
        // Creamos una instancia de Persona
        Persona persona1 = new Persona("Juan");
        // Creamos otra referencia a la misma instancia
        Persona persona2 = persona1;
        // Modificamos el nombre a través de la referencia persona2
        persona2.setNombre("Pedro");
        // Imprimimos el nombre desde ambas referencias
        System.out.println("Nombre de persona1: " + persona1.getNombre());
        System.out.println("Nombre de persona2: " + persona2.getNombre());
    }
}

* En este ejemplo:

1. Creamos una instancia de Persona llamada persona1.
2. Luego, creamos otra referencia llamada persona2 que apunta a la misma instancia.
3. Al modificar el nombre a través de persona2, también afectamos a persona1.
4. Ambas referencias apuntan al mismo objeto en memoria.