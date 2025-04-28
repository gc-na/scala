<!--
Meta Description: # Override em Scala: Compreendendo a Sobrescrita de Métodos ## Sinopse O comando `override` em Scala é utilizado para sobrescrever métodos ou atributo...
Meta Keywords: override, método, que, superclasse, scala
-->

# Override em Scala: Compreendendo a Sobrescrita de Métodos

## Sinopse
O comando `override` em Scala é utilizado para sobrescrever métodos ou atributos em classes que herdam de uma superclasse. Esta palavra-chave é essencial para garantir que a implementação de um método na subclasse substitua a versão da superclasse.

## Documentação
Em Scala, a palavra-chave `override` é utilizada para indicar que um método ou atributo está sendo sobrescrito de uma superclasse. Isso é importante para a clareza do código e para evitar erros, pois garante que a intenção do programador de substituir um comportamento existente seja explícita.

### Propósito
O propósito principal do `override` é permitir que subclasses forneçam implementações específicas de métodos que já foram definidos em suas superclasses. Isso é uma parte fundamental do polimorfismo em programação orientada a objetos.

### Uso
Para usar `override`, você deve primeiro ter um método ou atributo na superclasse que está sendo sobrescrito. Ao declarar o método na subclasse, você deve precedê-lo com a palavra-chave `override`.

### Detalhes
- Um método deve ser declarado como `override` se for uma reimplementação de um método da superclasse.
- Se um método não for marcado como `override`, o compilador gerará um erro se ele tentar sobrescrever um método que não existe ou se não coincidir com a assinatura do método da superclasse.
- O `override` é obrigatório em Scala, ao contrário de outras linguagens que permitem a sobrescrita implícita.

## Exemplos

### Exemplo Básico de Sobrescrita
```scala
class Animal {
  def som(): String = "Som genérico"
}

class Cachorro extends Animal {
  override def som(): String = "Au Au"
}

val meuCachorro = new Cachorro()
println(meuCachorro.som()) // Saída: Au Au
```

### Exemplo com Atributos
```scala
class Pessoa {
  def nome: String = "Nome Genérico"
}

class Estudante extends Pessoa {
  override def nome: String = "Nome do Estudante"
}

val estudante = new Estudante()
println(estudante.nome) // Saída: Nome do Estudante
```

## Explicação
Um dos erros comuns ao trabalhar com `override` é não manter a assinatura do método da superclasse. O método sobrescrito deve ter a mesma lista de parâmetros e o mesmo tipo de retorno do método original. Além disso, é importante lembrar que, se a superclasse usar `final` em um método, ele não pode ser sobrescrito na subclasse.

Outro ponto a ser considerado é o uso de `override` em campos. Embora a sobrescrita de métodos seja bastante comum, é menos comum sobrescrever campos diretamente, e isso pode causar confusão se não for feito corretamente.

## Resumo em Uma Linha
A palavra-chave `override` em Scala é utilizada para sobrescrever métodos ou atributos de uma superclasse, garantindo que a implementação na subclasse seja clara e correta.