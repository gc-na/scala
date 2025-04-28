<!--
Meta Description: # Uso de "extends" en Scala: Herencia y Composición ## Sinopsis El comando `extends` en Scala se utiliza para establecer la herencia entre clases y la...
Meta Keywords: extends, scala, clases, traits, clase
-->

# Uso de "extends" en Scala: Herencia y Composición

## Sinopsis
El comando `extends` en Scala se utiliza para establecer la herencia entre clases y la implementación de traits, permitiendo la reutilización del código y la creación de jerarquías de clases.

## Documentación
En Scala, `extends` es una palabra clave esencial que se utiliza para definir que una clase hereda de otra clase o que un trait se implementa en una clase. Esto permite a los desarrolladores aprovechar el código existente y crear nuevos comportamientos basados en él.

### Propósito
El propósito de `extends` es fomentar la reutilización y la organización del código, permitiendo a las clases hijas heredar atributos y métodos de las clases base. Esto también facilita la implementación de interfaces a través de traits.

### Uso
La sintaxis básica para utilizar `extends` en Scala es la siguiente:

```scala
class ClaseHija extends ClasePadre {
  // Implementación específica de ClaseHija
}
```

También se puede utilizar para implementar traits:

```scala
trait UnTrait {
  def metodo(): Unit
}

class ClaseConTrait extends UnTrait {
  def metodo(): Unit = {
    println("Método implementado")
  }
}
```

## Ejemplos

### Ejemplo 1: Herencia de Clases

```scala
class Animal {
  def sonido(): String = "Algun sonido"
}

class Perro extends Animal {
  override def sonido(): String = "Guau"
}

val miPerro = new Perro()
println(miPerro.sonido()) // Salida: Guau
```

### Ejemplo 2: Implementación de Traits

```scala
trait Volador {
  def volar(): Unit
}

class Pajaro extends Volador {
  def volar(): Unit = {
    println("El pájaro vuela")
  }
}

val miPajaro = new Pajaro()
miPajaro.volar() // Salida: El pájaro vuela
```

## Explicación
Al usar `extends`, es importante tener en cuenta lo siguiente:

- **Solo una clase base**: En Scala, las clases pueden heredar de una sola clase base, pero pueden implementar múltiples traits.
- **Uso de `override`**: Cuando se modifican métodos de la clase base en la clase derivada, es necesario utilizar la palabra clave `override`.
- **Constructores**: Al heredar, la clase hija debe llamar al constructor de la clase padre, especialmente si el constructor padre tiene parámetros.

### Errores Comunes
- **No usar `override`**: Olvidar usar `override` al redefinir un método puede causar errores de compilación.
- **Confusión con traits**: No diferenciar entre clases y traits puede llevar a implementaciones incorrectas. Recuerda que los traits pueden ser mezclados en múltiples clases, permitiendo una mayor flexibilidad.

## Resumen en Una Línea
La palabra clave `extends` en Scala es fundamental para la herencia de clases y la implementación de traits, permitiendo la reutilización efectiva del código.