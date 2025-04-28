<!--
Meta Description: # Das Schlüsselwort "super" in Scala: Verwendung und Bedeutung ## Synopsis Das Schlüsselwort „super“ in Scala ermöglicht den Zugriff auf Methoden und ...
Meta Keywords: der, super, und, von, das
-->

# Das Schlüsselwort "super" in Scala: Verwendung und Bedeutung

## Synopsis
Das Schlüsselwort „super“ in Scala ermöglicht den Zugriff auf Methoden und Mitglieder von übergeordneten Klassen und ist ein zentrales Element der Vererbung.

## Dokumentation
In Scala wird das Schlüsselwort „super“ verwendet, um auf Mitglieder (Methoden oder Variablen) der übergeordneten Klasse zuzugreifen. Dies ist besonders nützlich, wenn eine abgeleitete Klasse Methoden oder Variablen mit demselben Namen wie ihre Elternklasse definiert. Hierbei können Sie mit „super“ explizit die Implementierung der Elternklasse ansprechen.

### Zweck
- Zugriff auf übergeordnete Klassenmitglieder.
- Aufruf von Methoden der Elternklasse, auch wenn diese in der abgeleiteten Klasse überschrieben werden.

### Verwendung
Das Schlüsselwort „super“ kann in Methoden und Konstruktoren verwendet werden. Es wird normalerweise in der Methode verwendet, die überschrieben wird, um die Implementierung der Elternklasse zu referenzieren.

### Details
- „super“ kann nur innerhalb einer Instanzmethode oder eines Konstruktors verwendet werden.
- In einer Mehrfachvererbungskonstellation kann „super“ verwendet werden, um anzugeben, welche der mehreren Elternklassen verwendet werden soll.

## Beispiele
### Beispiel 1: Einfacher Zugriff auf die Elternklasse
```scala
class Eltern {
  def begruessung(): String = "Hallo von der Elternklasse!"
}

class Kind extends Eltern {
  override def begruessung(): String = {
    super.begruessung() + " Und hallo von der Kindklasse!"
  }
}

val kind = new Kind()
println(kind.begruessung()) // Ausgabe: "Hallo von der Elternklasse! Und hallo von der Kindklasse!"
```

### Beispiel 2: Verwendung in einem Konstruktor
```scala
class Tier(val name: String) {
  def geraeusch(): String = "Das Tier macht ein Geräusch"
}

class Hund(name: String) extends Tier(name) {
  override def geraeusch(): String = {
    super.geraeusch() + ": Wuff!"
  }
}

val hund = new Hund("Bello")
println(hund.geraeusch()) // Ausgabe: "Das Tier macht ein Geräusch: Wuff!"
```

## Erklärung
Ein häufiger Stolperstein ist die Verwechslung zwischen dem Aufruf von „super“ und der Verwendung des Namens der Klasse. Wenn Sie eine Methode in einer abgeleiteten Klasse überschreiben, wird „super“ verwendet, um sicherzustellen, dass Sie die Elternmethoden korrekt aufrufen. Ein weiterer wichtiger Punkt ist die Anwendung von „super“ in Mehrfachvererbungsszenarien. Hier sollten Sie klar angeben, welche übergeordnete Klasse Sie ansprechen möchten, um Verwirrung zu vermeiden.

## Ein-Satz-Zusammenfassung
Das Schlüsselwort „super“ in Scala ist entscheidend für den Zugriff auf Methoden und Mitglieder der übergeordneten Klassen und ermöglicht eine saubere Handhabung der Vererbung.