<!--
Meta Description: # Trait em Scala: Entenda como Funciona e como Utilizá-lo ## Sinopse Um trait em Scala é uma estrutura que permite a reutilização de código, podendo s...
Meta Keywords: trait, que, scala, classes, uma
-->

# Trait em Scala: Entenda como Funciona e como Utilizá-lo

## Sinopse
Um trait em Scala é uma estrutura que permite a reutilização de código, podendo ser considerado como uma combinação entre interfaces e classes. Ele permite que você defina métodos e comportamentos que podem ser compartilhados entre diferentes classes.

## Documentação
Os traits são uma parte fundamental da programação orientada a objetos em Scala e são usados para encapsular métodos e atributos que podem ser compartilhados entre várias classes. Ao contrário das classes, um trait não pode ser instanciado diretamente. Em vez disso, ele é "misturado" em classes concretas, permitindo que essas classes herdem o comportamento definido no trait.

### Propósito
O principal objetivo dos traits é promover a reutilização de código e a composição de comportamentos em vez da herança única. Isso possibilita que diferentes classes compartilhem funcionalidades sem a necessidade de uma hierarquia de classes complexa.

### Uso
Para definir um trait, você usa a palavra-chave `trait`, seguida pelo nome do trait e seu corpo:

```scala
trait Comportamento {
  def metodo(): Unit
}
```

Uma classe pode estender um trait utilizando a palavra-chave `extends`:

```scala
class MinhaClasse extends Comportamento {
  def metodo(): Unit = {
    println("Método implementado!")
  }
}
```

Além disso, um trait pode também ter implementações de métodos:

```scala
trait Comportamento {
  def metodo(): Unit = {
    println("Implementação padrão do método.")
  }
}
```

## Exemplos
### Exemplo 1: Trait simples
```scala
trait Animal {
  def som(): String
}

class Cachorro extends Animal {
  def som(): String = "Au Au"
}

class Gato extends Animal {
  def som(): String = "Miau"
}

val cachorro = new Cachorro()
println(cachorro.som()) // Saída: Au Au

val gato = new Gato()
println(gato.som()) // Saída: Miau
```

### Exemplo 2: Trait com implementação
```scala
trait Saudacao {
  def ola(): String = "Olá, bem-vindo!"
}

class Visitante extends Saudacao

val visitante = new Visitante()
println(visitante.ola()) // Saída: Olá, bem-vindo!
```

## Explicação
Um dos erros comuns ao trabalhar com traits é esquecer que eles não podem ser instanciados diretamente. Além disso, é importante entender que um trait pode estender outro trait, permitindo uma composição mais rica de comportamentos. Ao misturar múltiplos traits em uma única classe, deve-se ter cuidado com o "diamond problem" (problema do diamante), onde um método pode ser herdado de múltiplas fontes. Scala resolve isso através da ordem de prioridade na qual os traits são misturados.

Outro ponto a considerar é que os traits podem ter construtores, o que permite a passagem de parâmetros durante a extensão de classes, aumentando sua flexibilidade.

## Resumo em uma linha
Traits em Scala são estruturas que permitem a reutilização de código, combinando características de classes e interfaces para promover a composição de comportamentos.