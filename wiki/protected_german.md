<!--
Meta Description: # Scala "protected": Zugriffsmodifizierer für sichere Vererbung ## Synopsis In Scala dient das Schlüsselwort "protected" als Zugriffsmodifizierer, um ...
Meta Keywords: protected, der, klasse, die, und
-->

# Scala "protected": Zugriffsmodifizierer für sichere Vererbung

## Synopsis
In Scala dient das Schlüsselwort "protected" als Zugriffsmodifizierer, um den Zugriff auf Klassenmitglieder innerhalb einer Klasse und ihrer Unterklassen zu steuern. Es ermöglicht eine kontrollierte Sichtbarkeit und fördert die Kapselung in objektorientierten Anwendungen.

## Documentation
Das Schlüsselwort "protected" wird verwendet, um Variablen, Methoden oder Konstruktoren in einer Klasse zu deklarieren, sodass sie nur innerhalb der Klasse selbst und in abgeleiteten Klassen zugänglich sind. Dies ist besonders nützlich in Szenarien, in denen Sie möchten, dass bestimmte Elemente nur in einer Erbebeziehung sichtbar sind, aber nicht von außerhalb der Klasse oder ihrer Hierarchie.

### Verwendung
Die Verwendung des "protected"-Modifizierers erfolgt ähnlich wie bei "private" und "public". Hier ist die grundlegende Syntax:

```scala
class Parent {
  protected def protectedMethod(): Unit = {
    println("Protected method in Parent")
  }
}

class Child extends Parent {
  def callProtectedMethod(): Unit = {
    protectedMethod() // Zugriff auf die geschützte Methode
  }
}
```

In diesem Beispiel kann die Methode `protectedMethod` in der Kindklasse `Child` aufgerufen werden, jedoch nicht von Instanzen der Klasse `Parent` oder von außerhalb der Klassenhierarchie.

### Details
- **Zugriffsbereich:** "protected" gewährt Zugang nur innerhalb der definierten Klasse und deren Unterklassen.
- **Konstruktoren:** Konstruktoren einer Klasse können ebenfalls als "protected" markiert werden, was die Instanziierung der Klasse von außerhalb der Hierarchie einschränkt.
- **Kombination mit anderen Modifizierern:** Es ist möglich, "protected" mit anderen Modifizierern wie "override" zu kombinieren, um die Sichtbarkeit bei der Überschreibung von Methoden zu steuern.

## Examples
Hier sind einige einfache Beispiele für die Verwendung von "protected":

### Beispiel 1: Geschützte Methode
```scala
class Animal {
  protected def makeSound(): Unit = {
    println("Animal sound")
  }
}

class Dog extends Animal {
  def bark(): Unit = {
    makeSound() // Aufruf der geschützten Methode
    println("Woof")
  }
}

val dog = new Dog()
dog.bark() // Gibt "Animal sound" und "Woof" aus
```

### Beispiel 2: Geschützter Konstruktor
```scala
class Vehicle protected (val name: String)

class Car(name: String) extends Vehicle(name)

val car = new Car("Toyota") // Gültig
// val vehicle = new Vehicle("Bike") // Fehler: Konstruktor ist geschützt
```

## Explanation
Ein häufiger Stolperstein bei der Verwendung von "protected" ist das Missverständnis über den Sichtbarkeitsbereich. Viele Entwickler nehmen fälschlicherweise an, dass "protected" auch den Zugriff von Instanzen anderer Klassen innerhalb des gleichen Pakets erlaubt, was nicht der Fall ist. "Protected" ist ausschließlich für die Klasse selbst und deren Unterklassen zugänglich.

Ein weiterer Punkt ist, dass "protected" Methoden nicht aus Instanzen der Klasse aufgerufen werden können, die nicht Teil der Vererbungshierarchie sind. Entwickler sollten sich bewusst sein, dass "protected" nicht dasselbe ist wie "private", da "private" den Zugriff auf die Klasse selbst beschränkt.

## One Line Summary
Das Schlüsselwort "protected" in Scala ermöglicht den Zugriff auf Klassenmitglieder innerhalb der Klasse und ihrer Unterklassen und fördert die Kapselung in objektorientierten Designs.