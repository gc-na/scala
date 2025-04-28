<!--
Meta Description: # Scala `def`: Funktionen und Methoden definieren ## Synopsis In Scala wird das Schlüsselwort `def` verwendet, um Funktionen und Methoden zu definiere...
Meta Keywords: scala, def, und, wird, funktion
-->

# Scala `def`: Funktionen und Methoden definieren

## Synopsis
In Scala wird das Schlüsselwort `def` verwendet, um Funktionen und Methoden zu definieren. Es ist ein zentrales Element der Sprache, das sowohl einfache als auch komplexe Operationen kapseln kann.

## Dokumentation
Das Schlüsselwort `def` in Scala dient zur Definition von Funktionen und Methoden. Eine Funktion ist ein Block von Code, der ausgeführt wird, wenn er aufgerufen wird, und kann Parameter akzeptieren sowie Werte zurückgeben. Die Grundstruktur einer Funktion sieht wie folgt aus:

```scala
def funktionsName(parameterTyp: ParameterName): Rückgabetyp = {
  // Funktionskörper
}
```

### Zweck
`def` ermöglicht es Entwicklern, wiederverwendbare Codeblöcke zu erstellen, die in verschiedenen Teilen des Programms aufgerufen werden können. Dies fördert die Modularität und Lesbarkeit des Codes.

### Nutzung
Um eine Funktion zu definieren, geben Sie `def` gefolgt vom Namen der Funktion, den Parametern und dem Rückgabetyp an. Der Funktionskörper wird in geschweifte Klammern `{}` eingeschlossen. Hier ist ein Beispiel:

```scala
def addiere(a: Int, b: Int): Int = {
  a + b
}
```

In diesem Beispiel wird eine Funktion `addiere` definiert, die zwei Ganzzahlen addiert und das Ergebnis zurückgibt.

## Beispiele
### Einfaches Beispiel
```scala
def begruessung(name: String): String = {
  "Hallo, " + name + "!"
}
```
Aufruf:
```scala
println(begruessung("Max"))  // Ausgabe: Hallo, Max!
```

### Funktion mit mehreren Parametern
```scala
def multipliziere(a: Double, b: Double): Double = {
  a * b
}
```
Aufruf:
```scala
println(multipliziere(2.5, 4.0))  // Ausgabe: 10.0
```

### Funktion ohne Rückgabewert (Unit)
```scala
def druckeNachricht(nachricht: String): Unit = {
  println(nachricht)
}
```
Aufruf:
```scala
druckeNachricht("Dies ist eine Nachricht.")  // Ausgabe: Dies ist eine Nachricht.
```

## Erklärung
Einige häufige Fallstricke beim Arbeiten mit `def` in Scala sind:

- **Typinferenz:** Scala kann oft den Rückgabetyp einer Funktion ableiten, wenn dieser nicht explizit angegeben wird. Dies kann jedoch zu Verwirrung führen, wenn die Funktion nicht wie erwartet funktioniert. Es ist eine gute Praxis, den Rückgabetyp klar zu definieren.
  
- **Parameter mit Standardwerten:** In Scala können Parameter Standardwerte haben, was die Verwendung von `def` flexibler macht. Beispiel:
  ```scala
  def begruessung(name: String = "Gast"): String = {
    "Hallo, " + name + "!"
  }
  ```

- **Methoden in Klassen:** Wenn `def` innerhalb einer Klasse verwendet wird, wird es zu einer Methode dieser Klasse. Die Sichtbarkeit von Methoden (public, private, protected) sollte ebenfalls berücksichtigt werden.

## Ein-Satz-Zusammenfassung
Das Schlüsselwort `def` in Scala wird verwendet, um Funktionen und Methoden zu definieren, die modularen und wiederverwendbaren Code ermöglichen.