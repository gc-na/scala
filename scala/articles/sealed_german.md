<!--
Meta Description: # Sealed in Scala: Eine umfassende Anleitung zu versiegelten Klassen und Traits ## Synopsis In Scala ermöglicht das Schlüsselwort „sealed“ eine kontro...
Meta Keywords: sealed, und, die, case, der
-->

# Sealed in Scala: Eine umfassende Anleitung zu versiegelten Klassen und Traits

## Synopsis
In Scala ermöglicht das Schlüsselwort „sealed“ eine kontrollierte Vererbung, indem es die Hierarchie von Klassen und Traits einschränkt. Dies sorgt für mehr Sicherheit und Vorhersehbarkeit im Code.

## Dokumentation
Das Schlüsselwort `sealed` wird verwendet, um eine Klasse oder ein Trait zu deklarieren, die/der nicht außerhalb ihrer eigenen Datei erweitert werden kann. Diese Einschränkung fördert eine klare und geschlossene Vererbungshierarchie, die besonders nützlich ist, wenn man mit Mustervergleichen arbeitet. Es stellt sicher, dass alle Unterklassen in der gleichen Datei definiert sind, was es einfacher macht, die möglichen Typen zu überblicken.

### Zweck
Das Hauptziel von `sealed` ist die Verbesserung der Typensicherheit und der Codeverwendbarkeit. Wenn eine Klasse oder ein Trait als versiegelt deklariert ist, kann der Entwickler sicherstellen, dass alle möglichen Untertypen bekannt sind und verwaltet werden können.

### Verwendung
Um eine Klasse oder ein Trait als versiegelt zu deklarieren, fügen Sie einfach das Schlüsselwort `sealed` vor der Deklaration hinzu. Hier ist ein Beispiel:

```scala
sealed trait Fahrzeug
case class Auto(mark: String, model: String) extends Fahrzeug
case class Fahrrad(mark: String, typ: String) extends Fahrzeug
```

In diesem Beispiel wird das Trait `Fahrzeug` als versiegelt deklariert. Die beiden Klassen `Auto` und `Bicycle` sind die einzigen erlaubten Untertypen.

## Beispiele
Hier sind einige grundlegende Beispiele für die Verwendung von `sealed` in Scala:

### Beispiel 1: Versiegeltes Trait
```scala
sealed trait Tier
case class Hund(name: String) extends Tier
case class Katze(name: String) extends Tier

def beschreibeTier(tier: Tier): String = tier match {
  case Hund(name) => s"Ein Hund namens $name."
  case Katze(name) => s"Eine Katze namens $name."
}
```

### Beispiel 2: Versiegelte Klassen
```scala
sealed class Form
case class Kreis(radius: Double) extends Form
case class Rechteck(breite: Double, hoehe: Double) extends Form

def flaeche(form: Form): Double = form match {
  case Kreis(radius) => Math.PI * radius * radius
  case Rechteck(breite, hoehe) => breite * hoehe
}
```

## Erklärung
Ein häufiger Stolperstein bei der Verwendung von `sealed` ist das Missverständnis, dass versiegelte Klassen und Traits auch privat sind. `sealed` beschränkt lediglich die Vererbung auf die aktuelle Datei, bedeutet jedoch nicht, dass die Klasse oder das Trait privat ist. Außerdem können Sie keine neuen Untertypen in anderen Dateien definieren, was bei der Organisation von Code und der Modularität berücksichtigt werden sollte.

Ein weiteres wichtiges Detail ist, dass `sealed` in Kombination mit `case classes` häufig verwendet wird, um Mustervergleiche effizient und sicher zu gestalten. Dies ist besonders nützlich, wenn Sie sicherstellen möchten, dass alle möglichen Fälle behandelt werden.

## Ein Satz Zusammenfassung
Das `sealed`-Schlüsselwort in Scala ermöglicht eine kontrollierte Vererbung und verbessert somit die Typensicherheit und Vorhersehbarkeit im Code.