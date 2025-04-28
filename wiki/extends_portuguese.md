<!--
Meta Description: # Extends em Scala: Compreendendo Herança e Polimorfismo ## Sinopse O comando `extends` em Scala é fundamental para a herança de classes e traits, per...
Meta Keywords: classe, extends, uma, scala, para
-->

# Extends em Scala: Compreendendo Herança e Polimorfismo

## Sinopse
O comando `extends` em Scala é fundamental para a herança de classes e traits, permitindo que uma classe herde comportamentos e características de outra classe ou trait. Essa funcionalidade é essencial para promover a reutilização de código e a implementação de hierarquias de classes.

## Documentação
O `extends` é utilizado em Scala para indicar que uma classe ou trait herda de outra classe ou trait. Quando uma classe estende outra, ela herda todos os membros (métodos e variáveis) da classe base, podendo também sobrescrever métodos e adicionar novos comportamentos.

### Propósito
O objetivo do `extends` é facilitar a construção de sistemas orientados a objetos, onde podemos criar uma nova classe baseada em uma classe existente, reutilizando e estendendo suas funcionalidades.

### Uso
Para utilizar o `extends`, você deve declarar uma nova classe ou trait e especificar a classe ou trait que está sendo estendida. A sintaxe básica é:

```scala
class NomeDaClasse extends NomeDaClasseBase {
  // corpo da nova classe
}
```

### Detalhes
- Uma classe pode herdar de apenas uma classe (herança única), mas pode implementar múltiplos traits.
- Traits são semelhantes a interfaces em outras linguagens, mas podem conter implementações de métodos.
- A ordem de inicialização das classes base é da esquerda para a direita.

## Exemplos
### Exemplo 1: Herança Simples
```scala
class Animal {
  def fazerSom(): String = "Som genérico"
}

class Cachorro extends Animal {
  override def fazerSom(): String = "Au Au"
}

val meuCachorro = new Cachorro()
println(meuCachorro.fazerSom()) // Saída: Au Au
```

### Exemplo 2: Uso de Traits
```scala
trait PodeCorrer {
  def correr(): String = "Correndo"
}

class Gato extends Animal with PodeCorrer {
  override def fazerSom(): String = "Miau"
}

val meuGato = new Gato()
println(meuGato.fazerSom()) // Saída: Miau
println(meuGato.correr())   // Saída: Correndo
```

## Explicação
Ao utilizar `extends`, é importante ter em mente algumas considerações:

- **Sobrescrita de Métodos**: Ao sobrescrever métodos, use a palavra-chave `override` para tornar a intenção clara.
- **Construtores**: Se a classe base possui um construtor, a classe derivada deve chamá-lo explicitamente.
- **Limitações**: Como Scala não suporta herança múltipla de classes, você deve usar traits para compartilhar comportamentos entre diferentes classes.

## Resumo em Uma Linha
O comando `extends` em Scala permite a criação de classes que herdam comportamentos de classes ou traits, promovendo a reutilização de código e a organização hierárquica.