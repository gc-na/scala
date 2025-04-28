<!--
Meta Description: # Lớp (Class) trong Scala: Cách định nghĩa và sử dụng ## Tóm tắt Lớp (class) trong Scala là một khái niệm cơ bản, cho phép lập trình viên định nghĩa l...
Meta Keywords: lớp, scala, định, các, nghĩa
-->

# Lớp (Class) trong Scala: Cách định nghĩa và sử dụng

## Tóm tắt
Lớp (class) trong Scala là một khái niệm cơ bản, cho phép lập trình viên định nghĩa loại dữ liệu mới với các thuộc tính và phương thức. Tính năng này hỗ trợ lập trình hướng đối tượng, giúp tổ chức mã nguồn một cách hiệu quả và dễ bảo trì.

## Tài liệu
Lớp trong Scala được sử dụng để mô tả các đối tượng và hành vi của chúng. Một lớp có thể chứa các biến (thuộc tính) và phương thức (hành động) mà các đối tượng của lớp đó có thể thực hiện. Để định nghĩa một lớp, bạn sử dụng từ khóa `class` theo cú pháp sau:

```scala
class ClassName(parameters) {
  // Các thuộc tính và phương thức
}
```

### Ví dụ cơ bản:
1. **Định nghĩa một lớp đơn giản**:

```scala
class Dog(val name: String, var age: Int) {
  def bark(): Unit = {
    println(s"$name says: Woof!")
  }
}
```

2. **Tạo đối tượng từ lớp**:

```scala
val myDog = new Dog("Buddy", 3)
myDog.bark() // In ra: Buddy says: Woof!
```

3. **Truy cập và thay đổi thuộc tính**:

```scala
println(myDog.age) // In ra: 3
myDog.age += 1
println(myDog.age) // In ra: 4
```

## Giải thích
Khi làm việc với lớp trong Scala, có một số điểm cần lưu ý:

- **Từ khóa `val` và `var`**: Sử dụng `val` để định nghĩa thuộc tính không thể thay đổi (immutable) và `var` để định nghĩa thuộc tính có thể thay đổi (mutable).
- **Kế thừa**: Scala hỗ trợ kế thừa, cho phép bạn tạo ra các lớp con từ lớp cha bằng cách sử dụng từ khóa `extends`.
- **Phương thức và tham số**: Các phương thức có thể được định nghĩa bên trong lớp để thực hiện các hành động liên quan đến đối tượng. Tham số của phương thức có thể được sử dụng để nhận dữ liệu từ bên ngoài.

### Một số cạm bẫy thường gặp:
- **Quên từ khóa `new`**: Khi tạo đối tượng từ lớp, bạn phải sử dụng từ khóa `new` để khởi tạo đối tượng, nếu không sẽ gặp lỗi biên dịch.
- **Không xác định biến**: Nếu không khai báo biến là `val` hoặc `var`, biến sẽ không thể truy cập bên ngoài lớp.

## Tóm tắt một câu
Lớp trong Scala cho phép lập trình viên định nghĩa các loại dữ liệu mới và tổ chức mã nguồn theo phương pháp lập trình hướng đối tượng.