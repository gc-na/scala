<!--
Meta Description: # Clases en Scala: Guía Completa para Entender y Usar ## Sinopsis Las clases en Scala son plantillas para crear objetos que encapsulan datos y comport...
Meta Keywords: scala, una, clase, string, clases
-->

# Clases en Scala: Guía Completa para Entender y Usar

## Sinopsis
Las clases en Scala son plantillas para crear objetos que encapsulan datos y comportamientos, siguiendo el paradigma de programación orientada a objetos. Proporcionan una estructura que permite la reutilización de código y la organización de programas complejos.

## Documentación
En Scala, una clase es una construcción fundamental que permite definir un tipo de dato. Las clases pueden contener atributos (variables) y métodos (funciones) que actúan sobre esos atributos. La sintaxis para definir una clase es simple y directa.

### Propósito
Las clases se utilizan para modelar entidades del mundo real y sus interacciones. Permiten agrupar datos y comportamientos relacionados, facilitando la manipulación y el acceso a los mismos.

### Uso
La definición de una clase se realiza con la palabra clave `class`, seguida del nombre de la clase y, opcionalmente, una lista de parámetros. Por ejemplo:

```scala
class Persona(nombre: String, edad: Int) {
  def saludar(): String = {
    s"Hola, mi nombre es $nombre y tengo $edad años."
  }
}
```

### Detalles
- **Parámetros de Clase**: Los parámetros pueden ser de tipo `val` (inmutables) o `var` (mutables).
- **Constructores**: Scala soporta constructores primarios y secundarios. El constructor primario se define directamente en la declaración de la clase, mientras que los constructores secundarios se definen como métodos dentro de la clase.
- **Herencia**: Las clases en Scala pueden heredar de otras clases utilizando la sintaxis `extends`. Esto permite reutilizar código y crear jerarquías de clases.
- **Traits**: Los traits son similares a las interfaces en Java, pero pueden contener implementación. Se pueden mezclar múltiples traits en una clase.

## Ejemplos
### Definición de una Clase Simple

```scala
class Coche(marca: String, modelo: String) {
  def info(): String = {
    s"Marca: $marca, Modelo: $modelo"
  }
}

val miCoche = new Coche("Toyota", "Corolla")
println(miCoche.info())  // Salida: Marca: Toyota, Modelo: Corolla
```

### Herencia

```scala
class Vehiculo(tipo: String) {
  def descripcion(): String = s"Tipo de vehiculo: $tipo"
}

class Moto(marca: String, modelo: String) extends Vehiculo("Moto") {
  def info(): String = s"Marca: $marca, Modelo: $modelo, ${descripcion()}"
}

val miMoto = new Moto("Honda", "CBR")
println(miMoto.info())  // Salida: Marca: Honda, Modelo: CBR, Tipo de vehiculo: Moto
```

## Explicación
Al trabajar con clases en Scala, es importante considerar lo siguiente:

- **Inmutabilidad**: Es una buena práctica usar `val` para los atributos de clase, lo que promueve un diseño más seguro y predecible.
- **Sobrecarga de Métodos**: Scala permite la sobrecarga de métodos, lo que significa que puedes tener múltiples métodos con el mismo nombre pero diferentes parámetros.
- **Encapsulamiento**: Utiliza modificadores de acceso (`private`, `protected`, `public`) para controlar la visibilidad de los atributos y métodos.

### Errores Comunes
- Olvidar inicializar un atributo: Si un atributo se define sin un valor inicial y no se le asigna en el constructor, puede resultar en un error de compilación.
- No utilizar `new`: En Scala, al instanciar una clase, es necesario usar la palabra clave `new`.

## Resumen en Una Línea
Las clases en Scala son estructuras que permiten definir tipos de datos personalizados, encapsulando atributos y comportamientos relacionados, y son esenciales para la programación orientada a objetos.