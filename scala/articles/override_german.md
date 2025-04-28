<!--
Meta Description: # Override in Scala: Eine umfassende Anleitung ## Synopsis In Scala ermöglicht das Schlüsselwort `override` das Überschreiben von Methoden und Variabl...
Meta Keywords: die, der, override, methode, eine
-->

# Override in Scala: Eine umfassende Anleitung

## Synopsis
In Scala ermöglicht das Schlüsselwort `override` das Überschreiben von Methoden und Variablen in abgeleiteten Klassen, die zuvor in einer Basisklasse definiert wurden. Es ist ein essenzielles Konzept für die objektorientierte Programmierung und unterstützt die Implementierung von Polymorphismus.

## Dokumentation
Das Schlüsselwort `override` wird in Scala verwendet, um eine Methode oder eine Variable in einer Unterklasse zu definieren, die bereits in der Oberklasse deklariert wurde. Es ist notwendig, `override` zu verwenden, um klarzustellen, dass die Methode oder Variable absichtlich überschrieben wird. Dies hilft, Fehler zu vermeiden und die Lesbarkeit des Codes zu verbessern.

### Verwendung
Um `override` zu verwenden, deklarieren Sie eine Methode oder Variable in einer Unterklasse mit dem Schlüsselwort `override`, gefolgt von der Methode oder Variablen, die Sie überschreiben möchten. Die Signatur der Methode in der Unterklasse muss der der Methode in der Oberklasse entsprechen.

### Details
- **Notwendigkeit**: Das Schlüsselwort `override` ist nicht optional. Wenn Sie versuchen, eine Methode ohne `override` zu überschreiben, wird der Compiler einen Fehler ausgeben.
- **Zugriffsmodifizierer**: Die Zugriffsmodifizierer (wie `public`, `private`, `protected`) können in der Unterklasse unterschiedlich sein, müssen jedoch die Sichtbarkeit der Basisklasse nicht verschärfen.
- **Vererbung**: `override` ist ein grundlegendes Konzept in der Vererbungshierarchie, das es ermöglicht, die Funktionalität von Basisklassen zu erweitern oder zu modifizieren.

## Beispiele

### Beispiel 1: Überschreiben einer Methode
```scala
class Tier {
  def geräusch(): String = "Geräusch eines Tieres"
}

class Hund extends Tier {
  override def geräusch(): String = "Wuff"
}

val meinHund = new Hund()
println(meinHund.geräusch())  // Ausgabe: Wuff
```

### Beispiel 2: Überschreiben einer Variablen
```scala
class Fahrzeug {
  val anzahlRäder: Int = 4
}

class Motorrad extends Fahrzeug {
  override val anzahlRäder: Int = 2
}

val meinMotorrad = new Motorrad()
println(meinMotorrad.anzahlRäder)  // Ausgabe: 2
```

## Erklärung
Ein häufiger Fehler ist, das `override`-Schlüsselwort zu vergessen, wenn eine Methode in einer Unterklasse überschrieben wird. In solchen Fällen gibt der Compiler eine Fehlermeldung aus, die darauf hinweist, dass die Methode nicht gefunden wurde. Ein weiteres Missverständnis ist, dass die Sichtbarkeit von Methoden in der Unterklasse nicht geringer sein darf als in der Oberklasse. Wenn die Basisklasse eine Methode als `protected` definiert, kann die Unterklasse diese nicht als `private` deklarieren.

## Ein-Satz-Zusammenfassung
Das `override`-Schlüsselwort in Scala ist essentiell, um Methoden und Variablen in abgeleiteten Klassen zu überschreiben, was die Implementierung von Polymorphismus und die Erweiterung von Basisklassen ermöglicht.