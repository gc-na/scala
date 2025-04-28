<!--
Meta Description: # extends in Scala: Vererbung und Typen ## Synopsis Der Befehl `extends` in Scala wird verwendet, um Klassen und Traits zu vererben, wodurch eine Hier...
Meta Keywords: von, scala, die, und, der
-->

# extends in Scala: Vererbung und Typen

## Synopsis
Der Befehl `extends` in Scala wird verwendet, um Klassen und Traits zu vererben, wodurch eine Hierarchie von Typen entsteht. Dies ermöglicht die Wiederverwendbarkeit von Code und die Implementierung polymorpher Verhaltensweisen.

## Documentation
In Scala ist `extends` ein Schlüsselwort, das dazu dient, eine Klasse oder ein Trait von einer anderen Klasse oder einem Trait abzuleiten. Es ermöglicht die Schaffung von Unterklassen, die die Eigenschaften und Methoden der übergeordneten Klasse oder des Traits erben. Vererbung ist ein zentrales Konzept der objektorientierten Programmierung und hilft Entwicklern dabei, den Code modular und wartbar zu gestalten.

### Verwendung
```scala
class Tier {
  def lautGeben(): String = "Ein Geräusch"
}

class Hund extends Tier {
  override def lautGeben(): String = "Wuff!"
}
```
In diesem Beispiel erbt die Klasse `Hund` von der Klasse `Tier`. Der Hund überschreibt die Methode `lautGeben`, um ein spezifisches Verhalten zu implementieren.

### Details
- **Einfachvererbung**: Scala unterstützt einfaches Vererben, was bedeutet, dass eine Klasse nur von einer anderen Klasse erben kann. 
- **Traits**: Scala bietet die Möglichkeit, Traits zu definieren, die ähnlich wie Interfaces in anderen Programmiersprachen funktionieren. Sie können auch Methoden implementieren und von Mehrfachvererbung profitieren.
- **Kombination von Traits**: In Scala können Klassen mehrere Traits „mixen“, um verschiedene Funktionalitäten zu kombinieren.

## Examples
### Beispiel 1: Einfache Vererbung
```scala
class Fahrzeug {
  def fahren(): String = "Das Fahrzeug fährt."
}

class Auto extends Fahrzeug {
  override def fahren(): String = "Das Auto fährt schnell."
}

val meinAuto = new Auto()
println(meinAuto.fahren()) // Ausgabe: Das Auto fährt schnell.
```

### Beispiel 2: Vererbung mit Traits
```scala
trait Fliegendes {
  def fliegen(): String = "Ich fliege!"
}

class Vogel extends Tier with Fliegendes {
  override def lautGeben(): String = "Zwitscher!"
}

val meinVogel = new Vogel()
println(meinVogel.fliegen()) // Ausgabe: Ich fliege!
```

## Explanation
Ein häufiger Stolperstein bei der Verwendung von `extends` ist das Missverständnis bezüglich der Vererbungshierarchie. Wenn eine Klasse von einer anderen erbt, kann sie nur auf öffentliche und geschützte Mitglieder der übergeordneten Klasse zugreifen. Private Mitglieder sind nicht zugänglich. 

Ein weiterer Punkt ist das Überschreiben von Methoden. Wenn eine Methode in der Basisklasse nicht als `virtual` markiert ist (was in Scala der Standard ist), kann sie nicht überschrieben werden. Dies kann zu Laufzeitfehlern führen, wenn nicht korrekt implementiert.

## One Line Summary
Das Schlüsselwort `extends` in Scala ermöglicht die Vererbung von Klassen und Traits, was die Wiederverwendbarkeit und Modularität des Codes fördert.