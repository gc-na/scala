<!--
Meta Description: # Uso de "protected" en Scala: Acceso a Miembros de Clases ## Sinopsis El modificador de acceso "protected" en Scala permite que los miembros de una c...
Meta Keywords: protected, clase, acceso, miembros, que
-->

# Uso de "protected" en Scala: Acceso a Miembros de Clases

## Sinopsis
El modificador de acceso "protected" en Scala permite que los miembros de una clase (variables y métodos) sean accesibles en la misma clase y en subclases, pero no desde instancias de otras clases. Esto es útil para la encapsulación y la herencia, permitiendo un control más fino sobre la accesibilidad de los miembros.

## Documentación
El modificador "protected" se utiliza para definir el nivel de acceso de los miembros de una clase. En Scala, hay tres niveles de acceso: `public`, `protected` y `private`. Mientras que los miembros `public` son accesibles desde cualquier parte del programa y los `private` solo desde la misma clase, los miembros `protected` son accesibles dentro de la clase que los define y en cualquier clase que herede de ella.

### Propósito
El propósito principal de "protected" es permitir que las subclases accedan a ciertos miembros de la clase padre sin hacerlos completamente públicos. Esto fomenta la encapsulación y asegura que solo las subclases tengan acceso a esos miembros, lo que puede ser esencial para implementar patrones de diseño.

### Uso
Para declarar un miembro como "protected", simplemente se antepone la palabra clave `protected` en su declaración. Por ejemplo:

```scala
class Base {
  protected var x: Int = 0
}
```

Luego, cualquier subclase de `Base` podrá acceder al miembro `x`.

## Ejemplos

### Ejemplo 1: Uso básico de "protected"

```scala
class Animal {
  protected def makeSound(): String = "Sonido del animal"
}

class Dog extends Animal {
  def bark(): String = makeSound() + " - Guau!"
}

val dog = new Dog
println(dog.bark()) // Salida: Sonido del animal - Guau!
```

### Ejemplo 2: Acceso en subclases

```scala
class Vehicle {
  protected val wheels: Int = 4
}

class Car extends Vehicle {
  def numberOfWheels(): Int = wheels
}

val car = new Car
println(car.numberOfWheels()) // Salida: 4
```

### Ejemplo 3: Acceso limitado fuera de la jerarquía de clases

```scala
class Person {
  protected var name: String = "John"
}

class Employee extends Person {
  def getName(): String = name
}

// No se puede acceder a 'name' desde aquí
// val person = new Person
// println(person.name) // Error de compilación
```

## Explicación
Uno de los errores comunes al usar "protected" es pensar que permite el acceso desde cualquier instancia de la clase. Sin embargo, "protected" limita el acceso a la misma clase y a sus subclases, no a instancias de la clase padre. Otro punto a considerar es que, a diferencia de `private`, "protected" no restringe el acceso a nivel de paquete; las subclases en otros paquetes también pueden acceder a los miembros protegidos.

Además, es importante recordar que "protected" no se puede usar en miembros de objetos singleton.

## Resumen en una línea
El modificador "protected" en Scala permite el acceso a miembros de clase en la misma clase y en subclases, promoviendo la encapsulación y la herencia.