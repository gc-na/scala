<!--
Meta Description: # A palavra-chave "private" em Scala: Controle de Acesso a Membros de Classe ## Sinopse A palavra-chave "private" em Scala é utilizada para restringir...
Meta Keywords: private, classe, que, membros, scala
-->

# A palavra-chave "private" em Scala: Controle de Acesso a Membros de Classe

## Sinopse
A palavra-chave "private" em Scala é utilizada para restringir o acesso a membros de uma classe, garantindo que apenas a própria classe e suas subclasses possam acessá-los. Essa funcionalidade é essencial para a encapsulação, um dos pilares da programação orientada a objetos.

## Documentação
Em Scala, a palavra-chave "private" é um modificador de acesso que pode ser aplicado a variáveis, métodos e classes. Quando um membro é declarado como "private", ele não pode ser acessado fora do escopo da sua classe ou do seu objeto. Isso é fundamental para proteger a integridade dos dados e implementar o princípio de encapsulamento.

### Uso
A declaração de um membro privado é feita da seguinte maneira:

```scala
class MinhaClasse {
  private var meuDado: Int = 0

  private def meuMetodo(): Unit = {
    println("Método privado chamado.")
  }
}
```

No exemplo acima, `meuDado` e `meuMetodo` são acessíveis apenas dentro da classe `MinhaClasse`.

### Detalhes
- **Escopo**: Membros privados não podem ser acessados a partir de instâncias da classe fora do seu escopo. 
- **Subclasses**: Membros privados não são acessíveis em subclasses, a menos que sejam definidos como `private[this]`, que limita ainda mais o acesso.
- **Alternativas**: Para permitir acesso a subclasses, pode-se usar `protected`, que fornece um nível de acessibilidade maior.

## Exemplos
Aqui estão alguns exemplos práticos do uso da palavra-chave "private":

### Exemplo 1: Membro privado
```scala
class Conta {
  private var saldo: Double = 0.0

  def depositar(valor: Double): Unit = {
    saldo += valor
  }

  def obterSaldo(): Double = {
    saldo
  }
}

val conta = new Conta()
conta.depositar(100.0)
println(conta.obterSaldo()) // Saída: 100.0
// println(conta.saldo) // Erro: 'saldo' não é acessível
```

### Exemplo 2: Método privado
```scala
class Calculadora {
  private def somar(a: Int, b: Int): Int = a + b

  def calcularSoma(a: Int, b: Int): Int = {
    somar(a, b)
  }
}

val calc = new Calculadora()
println(calc.calcularSoma(5, 10)) // Saída: 15
// println(calc.somar(5, 10)) // Erro: 'somar' não é acessível
```

## Explicação
Um dos erros comuns ao trabalhar com membros privados é tentar acessá-los de fora da classe, o que resultará em um erro de compilação. Além disso, é importante notar que o uso excessivo de membros privados pode dificultar a testabilidade de uma classe. Uma abordagem equilibrada entre membros públicos e privados é recomendada para manter a flexibilidade do código.

Outro ponto a ser considerado é o uso de `private[this]`, que limita ainda mais o escopo, permitindo que apenas a instância atual da classe acesse o membro. Isso pode ser útil em implementações de segurança mais rigorosas.

## Resumo em Uma Linha
A palavra-chave "private" em Scala é utilizada para restringir o acesso a membros de classe, promovendo o encapsulamento e a proteção dos dados.