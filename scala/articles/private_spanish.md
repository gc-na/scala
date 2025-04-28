<!--
Meta Description: # Uso de la palabra clave "private" en Scala: Control de acceso a miembros de clases ## Sinopsis La palabra clave `private` en Scala se utiliza para r...
Meta Keywords: private, que, miembros, contador, scala
-->

# Uso de la palabra clave "private" en Scala: Control de acceso a miembros de clases

## Sinopsis
La palabra clave `private` en Scala se utiliza para restringir el acceso a miembros de clases, como variables y métodos, asegurando que solo sean accesibles dentro de la propia clase o su compañero.

## Documentación
La palabra clave `private` es un modificador de acceso que permite controlar la visibilidad de los miembros de una clase. En Scala, los miembros declarados como `private` no son accesibles desde fuera de la clase, lo que ayuda a encapsular la lógica y proteger los datos sensibles.

### Propósito
El propósito principal de `private` es implementar la encapsulación, un principio fundamental de la programación orientada a objetos. Al hacer que ciertos miembros sean `private`, se evita que el código externo modifique el estado interno del objeto de manera no controlada.

### Uso
La declaración de un miembro como `private` se realiza de la siguiente manera:

```scala
class MiClase {
  private var variablePrivada: Int = 0

  private def metodoPrivado(): Unit = {
    println("Este es un método privado.")
  }
}
```

En este ejemplo, tanto `variablePrivada` como `metodoPrivado` son miembros privados y solo pueden ser accedidos dentro de la clase `MiClase`.

### Detalles
- Los miembros `private` son accesibles dentro de la misma clase.
- Los miembros `private` no se pueden acceder desde instancias de la clase o desde subclases.
- En Scala, se puede utilizar `private[this]` para restringir aún más el acceso, permitiendo que solo el objeto actual acceda al miembro.

## Ejemplos

### Ejemplo 1: Uso básico de `private`
```scala
class Contador {
  private var cuenta: Int = 0

  def incrementar(): Unit = {
    cuenta += 1
  }

  def obtenerCuenta(): Int = cuenta
}

val contador = new Contador()
contador.incrementar()
println(contador.obtenerCuenta()) // Salida: 1
// contador.cuenta // Esto generará un error de compilación
```

### Ejemplo 2: Uso de `private[this]`
```scala
class Ejemplo {
  private[this] var contador: Int = 0

  def incrementar(): Unit = {
    contador += 1
  }

  def obtenerContador(): Int = contador
}

val ejemplo1 = new Ejemplo()
val ejemplo2 = new Ejemplo()

ejemplo1.incrementar()
ejemplo2.incrementar()

println(ejemplo1.obtenerContador()) // Salida: 1
println(ejemplo2.obtenerContador()) // Salida: 0
```

## Explicación
Al utilizar `private`, es importante tener en cuenta que los miembros no serán accesibles desde instancias externas de la clase, lo que puede ser confuso para los nuevos programadores. Además, `private[this]` limita aún más el acceso, lo que puede ser útil en situaciones donde se desea evitar que otros objetos de la misma clase accedan a ciertos datos.

Es fundamental recordar que el uso excesivo de miembros privados puede llevar a complicaciones en el diseño del código, por lo que se debe medir el uso de la encapsulación en función de la necesidad de proteger los datos.

## Resumen en una línea
La palabra clave `private` en Scala se utiliza para restringir el acceso a miembros de clases, garantizando la encapsulación y la protección de datos internos.