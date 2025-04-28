<!--
Meta Description: # Rückgabe in Scala: Verwendung des "return"-Schlüsselworts ## Synopsis In Scala wird das Schlüsselwort "return" verwendet, um einen Wert aus einer Fu...
Meta Keywords: return, scala, int, der, funktion
-->

# Rückgabe in Scala: Verwendung des "return"-Schlüsselworts

## Synopsis
In Scala wird das Schlüsselwort "return" verwendet, um einen Wert aus einer Funktion oder Methode zurückzugeben. Es spielt eine entscheidende Rolle in der Kontrolle des Programmflusses und der Resultatübermittlung.

## Dokumentation
Das "return"-Schlüsselwort in Scala ermöglicht es Entwicklern, den Rückgabewert einer Funktion explizit zu definieren. Obwohl Scala Funktionen und Methoden in der Regel den letzten Ausdruck als Rückgabewert verwenden, kann "return" eingesetzt werden, um die Lesbarkeit zu verbessern oder um den Rückgabewert an einer bestimmten Stelle zu definieren.

### Verwendung
- **Rückgabe eines Wertes:** Das Hauptziel von "return" ist es, einen Wert aus einer Methode zurückzugeben.
- **Verwendung in anonymen Funktionen:** In anonymen Funktionen kann "return" verwendet werden, um einen Wert aus der Funktion zurückzugeben, jedoch ist dies oft nicht notwendig, da Scala den letzten Ausdruck automatisch zurückgibt.
  
Ein typisches Beispiel für die Verwendung von "return" sieht wie folgt aus:

```scala
def addiere(a: Int, b: Int): Int = {
  return a + b
}
```

In diesem Fall gibt die Methode `addiere` die Summe von `a` und `b` zurück.

## Beispiele
Hier sind einige grundlegende Beispiele zur Verwendung von "return" in Scala:

### Beispiel 1: Einfache Rückgabe
```scala
def multipliziere(x: Int, y: Int): Int = {
  return x * y
}

// Aufruf der Funktion
val ergebnis = multipliziere(3, 4) // ergebnis ist 12
```

### Beispiel 2: Rückgabe in einer Schleife
```scala
def findeErstesGeradeZahl(zahlen: List[Int]): Int = {
  for (zahl <- zahlen) {
    if (zahl % 2 == 0) {
      return zahl // gibt die erste gefundene gerade Zahl zurück
    }
  }
  return -1 // Rückgabe -1, wenn keine gerade Zahl gefunden wurde
}

// Aufruf der Funktion
val ersteGerade = findeErstesGeradeZahl(List(1, 3, 5, 8, 9)) // ersteGerade ist 8
```

### Beispiel 3: Verwendung ohne return
```scala
def addiereOhneReturn(a: Int, b: Int): Int = {
  a + b // Letzter Ausdruck wird automatisch zurückgegeben
}

// Aufruf der Funktion
val summe = addiereOhneReturn(2, 5) // summe ist 7
```

## Erklärung
Obwohl "return" in Scala verwendet werden kann, um Werte zurückzugeben, gibt es einige wichtige Überlegungen:

1. **Vermeidung von "return":** Es ist oft besser, "return" zu vermeiden, da Scala den letzten Ausdruck einer Funktion automatisch als Rückgabewert behandelt. Dies macht den Code oft klarer und idiomatischer.

2. **Verhalten in Verschachtelungen:** Das "return"-Schlüsselwort kann dazu führen, dass die Kontrolle sofort aus der Methode zurückgegeben wird, was zu unerwartetem Verhalten führen kann, wenn es innerhalb von benannten Funktionsausdrücken oder Closures verwendet wird.

3. **Typensicherheit:** Der Rückgabewert muss mit dem deklarierten Rückgabetyp der Funktion übereinstimmen. Andernfalls wird ein Kompilierungsfehler angezeigt.

## Einzeiliger Zusammenfassung
Das "return"-Schlüsselwort in Scala dient dazu, explizit Werte aus Funktionen zurückzugeben, obwohl es oft besser ist, den letzten Ausdruck direkt zurückzugeben.