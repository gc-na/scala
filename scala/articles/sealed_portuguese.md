<!--
Meta Description: # Sealed Classes e Traits em Scala: Entenda o Conceito e a Utilização ## Sinopse As classes e traits selados (sealed) em Scala proporcionam segurança ...
Meta Keywords: que, sealed, subclasses, scala, trait
-->

# Sealed Classes e Traits em Scala: Entenda o Conceito e a Utilização

## Sinopse
As classes e traits selados (sealed) em Scala proporcionam segurança e controle sobre a hierarquia de herança, permitindo que todas as subclasses sejam definidas em um único arquivo, o que facilita o gerenciamento e a manutenção do código.

## Documentação
Em Scala, a palavra-chave `sealed` é utilizada para definir classes e traits que limitam a extensão a um conjunto restrito de subclasses. Isso significa que todas as subclasses de uma classe ou trait selado devem ser declaradas no mesmo arquivo onde a classe ou trait foi definida. Essa abordagem é especialmente útil quando se trabalha com padrões de correspondência (pattern matching), pois o compilador pode garantir que todas as possibilidades foram consideradas, evitando erros em tempo de execução.

### Propósito
O principal propósito de usar `sealed` é oferecer um controle mais rigoroso sobre a herança e garantir que todas as subclasses estejam documentadas em um único local. Isso aumenta a legibilidade e a segurança do código, facilitando a manutenção e a evolução do sistema.

### Uso
Para utilizar a palavra-chave `sealed`, basta declarar uma classe ou trait com a palavra `sealed` antes de sua definição. As subclasses podem ser definidas como classes regulares ou traits, mas devem estar no mesmo arquivo.

```scala
sealed trait Forma
case class Circulo(raio: Double) extends Forma
case class Retangulo(base: Double, altura: Double) extends Forma
```

## Exemplos
Aqui estão alguns exemplos simples que ilustram o uso de `sealed` em Scala:

### Exemplo 1: Definindo um Trait Selado
```scala
sealed trait Animal
case class Cachorro(nome: String) extends Animal
case class Gato(nome: String) extends Animal
```

### Exemplo 2: Usando Padrões de Correspondência
```scala
def fazerBarulho(animal: Animal): String = animal match {
  case Cachorro(nome) => s"$nome diz: Au Au!"
  case Gato(nome) => s"$nome diz: Miau!"
}
```

### Exemplo 3: Adicionando uma Nova Subclasse
```scala
case class Pássaro(nome: String) extends Animal
```

## Explicação
Um dos principais benefícios de usar `sealed` é a segurança proporcionada pelo compilador. Ao realizar correspondência de padrões, o compilador sabe que todas as subclasses possíveis foram definidas, permitindo que ele emita um aviso caso algum caso não seja tratado. No entanto, é importante lembrar que as subclasses devem sempre ser definidas no mesmo arquivo, o que pode ser um limitador em projetos maiores.

Outro ponto a ser observado é que `sealed` não impede que subclasses sejam criadas em outros arquivos, mas elas não serão reconhecidas como subclasses da classe ou trait selada. Isso pode gerar confusão e erros difíceis de identificar.

## Resumo em Uma Frase
Classes e traits selados em Scala oferecem um controle rigoroso sobre a herança, permitindo que todas as subclasses sejam definidas em um único arquivo, o que melhora a segurança e a manutenção do código.