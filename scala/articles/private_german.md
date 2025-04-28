<!--
Meta Description: # Private in Scala: Zugriffsmodifikator für Klassen und Mitglieder ## Synopsis In Scala ist `private` ein Zugriffsmodifikator, der den Zugriff auf Kla...
Meta Keywords: private, die, der, und, ist
-->

# Private in Scala: Zugriffsmodifikator für Klassen und Mitglieder

## Synopsis
In Scala ist `private` ein Zugriffsmodifikator, der den Zugriff auf Klassenmitglieder und Methoden einschränkt. Er ermöglicht es Entwicklern, die Sichtbarkeit von Variablen und Funktionen innerhalb einer Klasse zu steuern und fördert damit die Kapselung von Daten.

## Documentation
Der Zugriffsmodifikator `private` wird verwendet, um den Zugriff auf Klassenmitglieder (Felder und Methoden) auf die Klasse selbst zu beschränken. Dies bedeutet, dass nur die Instanzen der Klasse und die darin enthaltenen Methoden auf private Mitglieder zugreifen können. `private` ist ein wesentlicher Bestandteil der objektorientierten Programmierung, da es hilft, die Integrität der Daten zu schützen und die Modularität des Codes zu verbessern.

### Verwendung
Um ein Mitglied als `private` zu deklarieren, wird das Schlüsselwort `private` vor der Variablen- oder Methodendeklaration verwendet. Hier ein einfaches Beispiel:

```scala
class Beispiel {
  private var geheim: String = "Dies ist privat"

  private def zeigeGeheimnis(): String = geheim
}
```

In diesem Beispiel ist die Variable `geheim` und die Methode `zeigeGeheimnis` private, was bedeutet, dass sie nur innerhalb der Klasse `Beispiel` zugänglich sind.

## Examples
### Beispiel 1: Private Variable
```scala
class Konto {
  private var kontostand: Double = 0.0

  def einzahlen(betrag: Double): Unit = {
    kontostand += betrag
  }

  def abheben(betrag: Double): Unit = {
    if (kontostand >= betrag) {
      kontostand -= betrag
    } else {
      println("Nicht genügend Guthaben.")
    }
  }

  def zeigeKontostand(): Double = kontostand
}

val meinKonto = new Konto
meinKonto.einzahlen(100)
println(meinKonto.zeigeKontostand()) // Ausgabe: 100.0
```

### Beispiel 2: Private Methode
```scala
class Rechner {
  private def addiere(a: Int, b: Int): Int = a + b

  def addiereUndZeige(a: Int, b: Int): Unit = {
    val ergebnis = addiere(a, b)
    println(s"Das Ergebnis ist: $ergebnis")
  }
}

val meinRechner = new Rechner
meinRechner.addiereUndZeige(5, 10) // Ausgabe: Das Ergebnis ist: 15
```

## Explanation
Ein häufiger Fehler beim Arbeiten mit `private` ist der Versuch, auf private Mitglieder von außerhalb der Klasse zuzugreifen, was zu einem Kompilierungsfehler führt. Entwickler müssen sicherstellen, dass sie die Sichtbarkeit von Variablen und Methoden korrekt verwalten, um unerwartete Fehler zu vermeiden. Es ist auch wichtig zu beachten, dass `private` Mitglieder nicht von Unterklassen (Subklassen) erben können.

Ein weiterer Punkt ist, dass Scala auch `private[this]` unterstützt, was den Zugriff auf die Mitglieder weiter einschränkt, sodass nur die aktuelle Instanz der Klasse auf das Mitglied zugreifen kann. Dies kann nützlich sein, um Konflikte zwischen verschiedenen Instanzen zu vermeiden.

## One Line Summary
`private` in Scala ist ein Zugriffsmodifikator, der den Zugriff auf Klassenmitglieder auf die Klasse selbst beschränkt und somit die Kapselung von Daten fördert.