<!--
Meta Description: # Từ Khóa "super" trong Scala: Hiểu Rõ và Sử Dụng Hiệu Quả ## Tóm tắt Từ khóa "super" trong Scala được sử dụng để truy cập các phương thức và thuộc tí...
Meta Keywords: lớp, super, trong, cha, phương
-->

# Từ Khóa "super" trong Scala: Hiểu Rõ và Sử Dụng Hiệu Quả

## Tóm tắt
Từ khóa "super" trong Scala được sử dụng để truy cập các phương thức và thuộc tính của lớp cha trong một lớp con, giúp làm rõ ràng hơn trong việc kế thừa.

## Tài liệu
Từ khóa "super" trong Scala có vai trò quan trọng trong ngữ cảnh lập trình hướng đối tượng. Nó cho phép lập trình viên gọi các phương thức và thuộc tính của lớp cha từ lớp con. Khi lớp con kế thừa từ một lớp cha, "super" cung cấp cách để truy cập các thành phần đã bị ghi đè trong lớp con. 

Cú pháp sử dụng từ khóa "super" rất đơn giản:
```scala
super.methodName
super.propertyName
```
Trong đó, `methodName` và `propertyName` là tên của phương thức hoặc thuộc tính trong lớp cha mà bạn muốn truy cập.

### Mục đích
- **Truy cập phương thức:** Cho phép gọi lại các phương thức của lớp cha, hữu ích khi bạn muốn mở rộng hoặc thay đổi hành vi của phương thức mà không làm mất đi tính năng gốc của nó.
- **Truy cập thuộc tính:** Cung cấp cách để sử dụng thuộc tính của lớp cha mà có thể bị ghi đè bởi lớp con.

## Ví dụ
```scala
class Animal {
  def sound(): String = "Some sound"
}

class Dog extends Animal {
  override def sound(): String = {
    super.sound() + " Woof"
  }
}

val dog = new Dog()
println(dog.sound())  // Kết quả: Some sound Woof
```
Trong ví dụ trên, lớp `Dog` kế thừa từ lớp `Animal`. Khi gọi phương thức `sound()` trong lớp `Dog`, nó sử dụng `super.sound()` để truy cập phương thức gốc từ lớp cha.

## Giải thích
Một số điều cần lưu ý khi sử dụng từ khóa "super":
- **Ghi đè phương thức:** Khi bạn ghi đè một phương thức trong lớp con, bạn có thể sử dụng `super` để gọi phương thức gốc, điều này giúp tránh việc mất các hành vi của lớp cha.
- **Kiểm tra null:** Trong trường hợp lớp cha có thể là `null`, việc gọi `super` có thể dẫn đến lỗi. Bạn nên đảm bảo rằng lớp cha đã được khởi tạo trước khi sử dụng "super".
- **Chỉ áp dụng cho lớp cha ngay lập tức:** Từ khóa "super" chỉ có thể được sử dụng để truy cập các phương thức và thuộc tính của lớp cha ngay lập tức, không phải của các lớp cha khác.

## Tóm tắt một dòng
Từ khóa "super" trong Scala cho phép truy cập các phương thức và thuộc tính của lớp cha từ lớp con, hỗ trợ trong việc kế thừa và mở rộng hành vi của lớp.