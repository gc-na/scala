<!--
Meta Description: # Enum em Scala: Compreendendo Tipos Enumerados na Linguagem ## Sinopse O `enum` em Scala é um recurso que permite a definição de tipos enumerados de ...
Meta Keywords: enum, cor, scala, case, uma
-->

# Enum em Scala: Compreendendo Tipos Enumerados na Linguagem

## Sinopse
O `enum` em Scala é um recurso que permite a definição de tipos enumerados de maneira clara e concisa, facilitando a representação de um conjunto fixo de constantes.

## Documentação
O `enum` foi introduzido no Scala 3 como uma maneira de criar tipos enumerados. Ele permite que os desenvolvedores definam uma coleção de constantes associadas a um tipo, melhorando a legibilidade e segurança do código. Os enums em Scala podem incluir métodos e campos, oferecendo uma estrutura poderosa e flexível.

### Propósito
O objetivo principal do `enum` é representar um conjunto limitado de opções, como os dias da semana, estados de um processo, entre outros. Essa representação ajuda a evitar erros comuns relacionados a strings ou números mágicos.

### Uso
Para definir um `enum`, utiliza-se a palavra-chave `enum`, seguida pelo nome do tipo e suas instâncias. Aqui está a estrutura básica:

```scala
enum NomeDoEnum:
  case Valor1, Valor2, Valor3
```

## Exemplos

### Exemplo Básico
Aqui está um exemplo simples que define um enum para os dias da semana:

```scala
enum DiaDaSemana:
  case Segunda, Terça, Quarta, Quinta, Sexta, Sábado, Domingo

def saudacao(dia: DiaDaSemana): String = dia match
  case DiaDaSemana.Segunda => "Começo da semana!"
  case DiaDaSemana.Sábado | DiaDaSemana.Domingo => "Fim de semana!"
  case _ => "Dia de trabalho!"

println(saudacao(DiaDaSemana.Segunda)) // Saída: Começo da semana!
println(saudacao(DiaDaSemana.Sábado))  // Saída: Fim de semana!
```

### Exemplo com Métodos
Os enums também podem ter métodos:

```scala
enum Cor(val codigoHex: String):
  case Vermelho extends Cor("#FF0000")
  case Verde extends Cor("#00FF00")
  case Azul extends Cor("#0000FF")

def imprimirCor(cor: Cor): Unit =
  println(s"A cor ${cor} tem o código ${cor.codigoHex}")

imprimirCor(Cor.Vermelho) // Saída: A cor Vermelho tem o código #FF0000
```

## Explicação
Embora o uso de enums seja bastante intuitivo, existem algumas armadilhas a serem evitadas:

1. **Comparação com Strings**: Evite usar strings para representar estados ou opções. Use enums para garantir segurança de tipo.
2. **Extensibilidade**: Os enums em Scala não são extensíveis. Uma vez definidos, não é possível adicionar novos casos fora do escopo do enum.
3. **Padrões de Combinação**: Ao utilizar o `match`, é importante cobrir todos os casos possíveis, uma vez que a omissão de um deles pode resultar em um erro em tempo de execução.

## Resumo em Uma Linha
O `enum` em Scala é uma maneira poderosa e segura de definir tipos enumerados, permitindo a representação de conjuntos fixos de constantes com métodos e campos associados.