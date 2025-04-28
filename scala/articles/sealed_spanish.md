<!--
Meta Description: # Uso de "sealed" en Scala: Todo lo que Necesitas Saber ## Sinopsis El modificador "sealed" en Scala permite restringir la herencia de una clase o tra...
Meta Keywords: sealed, una, patrones, que, case
-->

# Uso de "sealed" en Scala: Todo lo que Necesitas Saber

## Sinopsis
El modificador "sealed" en Scala permite restringir la herencia de una clase o trait a un conjunto específico de subtipos definidos en el mismo archivo. Esto mejora la seguridad del tipo y facilita el manejo de patrones.

## Documentación
El modificador "sealed" se utiliza para declarar clases y traits en Scala. Al marcar una clase como "sealed", se indica que todas las subclases deben estar definidas en el mismo archivo. Esto es especialmente útil en el contexto de la programación funcional y el uso de patrones, ya que permite al compilador verificar exhaustivamente los casos en las estructuras de control.

### Propósito
El propósito principal de "sealed" es habilitar un control más preciso sobre la jerarquía de clases, lo que ayuda a evitar errores en el tiempo de ejecución y a mejorar la mantenibilidad del código.

### Uso
Para utilizar "sealed", simplemente se coloca el modificador antes de la declaración de una clase o trait. A continuación, se presentan las características clave:

- **Restricción de herencia**: Solo las subclases definidas en el mismo archivo pueden extender una clase sellada.
- **Seguridad de tipo**: Permite patrones exhaustivos en la verificación de tipos.
- **Compatibilidad con patrones**: Facilita el uso de patrones con las subclases, ya que el compilador puede asegurarse de que se han manejado todos los casos.

### Detalles
- Las clases selladas no pueden ser instanciadas directamente.
- Las subclases de una clase sellada pueden ser tanto clases como traits.
- Es recomendable utilizar clases selladas en combinación con patrones de coincidencia (`match`) para mejorar la claridad y la seguridad del código.

## Ejemplos

### Ejemplo básico
```scala
sealed trait Animal
case class Perro(nombre: String) extends Animal
case class Gato(nombre: String) extends Animal

def hacerSonido(animal: Animal): String = animal match {
  case Perro(nombre) => s"$nombre dice: Guau!"
  case Gato(nombre) => s"$nombre dice: Miau!"
}
```

### Ejemplo con múltiples subclases
```scala
sealed trait Vehiculo
case class Coche(marca: String) extends Vehiculo
case class Moto(marca: String) extends Vehiculo

def mostrarVehiculo(vehiculo: Vehiculo): String = vehiculo match {
  case Coche(marca) => s"Es un coche de la marca: $marca"
  case Moto(marca) => s"Es una moto de la marca: $marca"
}
```

## Explicación
Al utilizar "sealed", es importante recordar que:

- **No se puede extender fuera del archivo**: Cualquier intento de declarar una subclase de una clase sellada en otro archivo resultará en un error de compilación.
- **Patrones exhaustivos**: Si no se manejan todos los casos posibles en un `match`, el compilador advertirá sobre la falta de patrones, lo que puede ayudar a evitar errores lógicos.
- **Mejora la mantenibilidad**: Al tener un conjunto limitado de subclases, se facilita la comprensión de la jerarquía de tipos y se reduce la complejidad.

## Resumen en una línea
El modificador "sealed" en Scala restringe la herencia de clases y traits a un conjunto específico definido en el mismo archivo, mejorando la seguridad del tipo y facilitando el manejo de patrones.