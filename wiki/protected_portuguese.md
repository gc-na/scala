<!--
Meta Description: # A Profundidade da Palavra-Chave "protected" em Scala: Entendendo o Acesso em Classes ## Sinopse A palavra-chave `protected` em Scala é um modificado...
Meta Keywords: que, protected, classe, subclasses, não
-->

# A Profundidade da Palavra-Chave "protected" em Scala: Entendendo o Acesso em Classes

## Sinopse
A palavra-chave `protected` em Scala é um modificador de acesso que permite que membros de uma classe sejam acessíveis apenas dentro da própria classe e em suas subclasses, promovendo a encapsulação e a segurança dos dados.

## Documentação
A palavra-chave `protected` é utilizada para definir a visibilidade de variáveis e métodos dentro de classes e traits em Scala. Ao utilizar `protected`, você garante que um membro (atributo ou método) não possa ser acessado diretamente fora da classe que o define, exceto em classes filhas que herdam dessa classe base.

### Propósito
O propósito de `protected` é fornecer um nível de proteção que é menos restritivo que `private`, permitindo que subclasses tenham acesso a membros que não são visíveis para o restante do mundo.

### Uso
- **Definição de Membros**: Quando um membro é declarado como `protected`, ele pode ser acessado por subclasses, mas não por instâncias da classe ou de outras classes que não herdam dela.
- **Construção de Hierarquias**: É frequentemente utilizado em hierarquias de classes para permitir que subclasses acessem e modifiquem o estado da classe base, mantendo a integridade dos dados.

### Detalhes
- Membros `protected` podem ser acessados em qualquer classe que herde da classe que os define.
- O `protected` não se aplica a membros que são acessados através de instâncias de uma classe; apenas membros de subclasses têm acesso.

## Exemplos

### Exemplo 1: Uso Básico do `protected`
```scala
class Animal {
  protected def sound(): String = "Som do animal"
}

class Dog extends Animal {
  def bark(): String = sound() + " - O cachorro late!"
}

val dog = new Dog
println(dog.bark())  // Saída: Som do animal - O cachorro late!
```

### Exemplo 2: Acesso Restrito
```scala
class Vehicle {
  protected var speed: Int = 0
}

class Car extends Vehicle {
  def setSpeed(s: Int): Unit = {
    speed = s
  }
}

val car = new Car
car.setSpeed(100)
// println(car.speed)  // Erro: speed não é acessível aqui
```

## Explicação
Um dos pontos a se ter em mente ao usar `protected` é que, embora ele permita o acesso em subclasses, ele não deve ser confundido com `public`. Membros `protected` não são acessíveis a partir de instâncias de classes que não são subclasses. Além disso, se você não tiver cuidado, pode acabar expondo mais do que pretendia através de subclasses, o que pode levar a um acoplamento indesejado entre a classe base e suas subclasses.

## Resumo em Uma Linha
A palavra-chave `protected` em Scala permite o acesso a membros de uma classe apenas dentro da própria classe e suas subclasses, promovendo a segurança e a encapsulação dos dados.