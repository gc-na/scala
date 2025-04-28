<!--
Meta Description: # Từ Khóa "protected" trong Scala: Cách Sử Dụng và Ý Nghĩa ## Tóm Tắt Từ khóa "protected" trong Scala được sử dụng để xác định quyền truy cập cho các ...
Meta Keywords: protected, lớp, các, truy, cập
-->

# Từ Khóa "protected" trong Scala: Cách Sử Dụng và Ý Nghĩa

## Tóm Tắt
Từ khóa "protected" trong Scala được sử dụng để xác định quyền truy cập cho các thành viên (biến, phương thức) của lớp, cho phép chúng chỉ có thể được truy cập trong lớp đó và các lớp con của nó.

## Tài Liệu
### Mục Đích
Từ khóa "protected" giúp kiểm soát quyền truy cập của các thành viên trong lớp, tạo ra tính bảo mật và khả năng mở rộng cho các lớp con. Nó cho phép các lớp con có thể truy cập và sử dụng các thành viên "protected" mà không cần phải công khai chúng ra ngoài.

### Cách Sử Dụng
Khi bạn khai báo một thành viên trong lớp bằng từ khóa "protected", nó sẽ chỉ có thể được truy cập bởi chính lớp đó và các lớp con của nó. Dưới đây là cú pháp cơ bản:

```scala
class SuperClass {
  protected var protectedVariable: Int = 0
  
  protected def protectedMethod(): Unit = {
    println("This is a protected method.")
  }
}

class SubClass extends SuperClass {
  def accessProtectedMembers(): Unit = {
    protectedVariable = 10 // Truy cập biến protected
    protectedMethod()       // Gọi phương thức protected
  }
}
```

### Chi Tiết
- Biến và phương thức được khai báo là "protected" không thể được truy cập từ bên ngoài lớp hoặc lớp con.
- Từ khóa "protected" có thể được sử dụng cho biến, phương thức, và các khối mã khác trong lớp.
- Khi một lớp con kế thừa từ lớp cha, nó có quyền truy cập trực tiếp đến các thành viên "protected".

## Ví Dụ
Dưới đây là một ví dụ đơn giản sử dụng từ khóa "protected":

```scala
class Animal {
  protected def makeSound(): Unit = {
    println("Animal sound")
  }
}

class Dog extends Animal {
  def bark(): Unit = {
    makeSound() // Truy cập phương thức protected
    println("Bark")
  }
}

object Main extends App {
  val dog = new Dog
  dog.bark()
  // dog.makeSound() // Sẽ báo lỗi vì makeSound() là protected
}
```

## Giải Thích
Một số điều cần lưu ý khi sử dụng từ khóa "protected":
- Nếu bạn khai báo một thành viên là "protected", bạn không thể trực tiếp truy cập nó từ một đối tượng của lớp đó bên ngoài lớp hoặc lớp con.
- Nếu một lớp con không cần sử dụng một thành viên "protected", bạn nên cân nhắc việc sử dụng từ khóa "private" để hạn chế hơn nữa khả năng truy cập.
- "protected" cũng có thể được sử dụng trong các trait, nhưng cần lưu ý rằng các thành viên "protected" trong trait sẽ trở thành "protected" cho các lớp kế thừa.

## Tóm Tắt Một Dòng
Từ khóa "protected" trong Scala cho phép các thành viên của lớp chỉ được truy cập từ lớp đó và các lớp kế thừa của nó, tạo ra tính bảo mật và khả năng mở rộng.