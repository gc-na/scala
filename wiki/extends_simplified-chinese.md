<!--
Meta Description: # 在Scala中使用“extends”关键字的详细指南 ## 摘要 “extends”是Scala中的一个关键字，用于表示类的继承关系。它允许一个类扩展另一个类，从而继承父类的属性和方法，促进代码重用和多态性。 ## 文档 在Scala中，`extends`关键字用于定义类之间的继承关系。当一个类...
Meta Keywords: extends, override, animal, class, makesound
-->

# 在Scala中使用“extends”关键字的详细指南

## 摘要
“extends”是Scala中的一个关键字，用于表示类的继承关系。它允许一个类扩展另一个类，从而继承父类的属性和方法，促进代码重用和多态性。

## 文档
在Scala中，`extends`关键字用于定义类之间的继承关系。当一个类使用`extends`关键字时，它会继承其父类的所有成员（属性和方法）。这使得子类可以重用父类的实现，并可以选择重写父类的方法，以提供特定的实现。Scala支持单继承，即一个类只能直接继承一个父类，但可以通过特质（traits）实现多重继承的效果。

### 用法
一个基本的类继承语法如下：
```scala
class 子类名 extends 父类名 {
  // 子类的属性和方法
}
```
在类定义中，`extends`后面跟的是父类的名称。如果需要重写父类的方法，可以使用`override`关键字。

### 详细信息
- **构造函数**：在子类的构造函数中，可以调用父类的构造函数，以确保父类的属性被正确初始化。
- **方法重写**：使用`override`关键字重写父类的方法时，方法签名必须与父类中的方法完全一致。
- **访问修饰符**：父类的成员可以是`public`、`protected`或`private`，访问权限会影响子类的访问能力。

## 示例
以下是Scala中使用`extends`的基本示例：

```scala
// 定义一个父类 Animal
class Animal {
  def makeSound(): Unit = {
    println("动物发出声音")
  }
}

// 定义一个子类 Dog，继承自 Animal
class Dog extends Animal {
  override def makeSound(): Unit = {
    println("汪汪")
  }
}

// 使用示例
val myDog = new Dog()
myDog.makeSound()  // 输出: 汪汪
```

## 说明
- **常见陷阱**：在子类中未使用`override`关键字重写父类的方法，编译器会报错，提示方法未被重写。
- **父类的访问修饰符**：如果父类的某个成员是`private`，则子类无法访问该成员，即使它是继承自父类的。
- **构造函数的调用顺序**：当创建子类对象时，父类的构造函数会先被调用，然后才是子类的构造函数。

## 一句话总结
`extends`关键字在Scala中用于定义类的继承关系，使得子类可以重用和重写父类的属性和方法。