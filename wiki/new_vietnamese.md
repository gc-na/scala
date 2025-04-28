<!--
Meta Description: # Từ Khóa "new" Trong Scala: Tạo Đối Tượng Mới ## Tóm Tắt Từ khóa `new` trong Scala được sử dụng để khởi tạo các đối tượng mới từ lớp hoặc kiểu dữ liệ...
Meta Keywords: tạo, new, các, khởi, lớp
-->

# Từ Khóa "new" Trong Scala: Tạo Đối Tượng Mới

## Tóm Tắt
Từ khóa `new` trong Scala được sử dụng để khởi tạo các đối tượng mới từ lớp hoặc kiểu dữ liệu, giúp lập trình viên dễ dàng tạo ra các thực thể của các lớp đã định nghĩa.

## Tài Liệu
Từ khóa `new` là một phần quan trọng trong lập trình hướng đối tượng bằng Scala. Khi bạn muốn tạo một thể hiện của một lớp, bạn sẽ sử dụng từ khóa `new` theo sau là tên lớp. Cấu trúc cơ bản để sử dụng `new` là:

```scala
val obj = new ClassName(parameters)
```

- **Mục đích**: Tạo ra một thể hiện mới của lớp.
- **Cách sử dụng**: Bạn có thể khởi tạo đối tượng mà không cần tham số, hoặc với một hoặc nhiều tham số tùy thuộc vào cấu trúc khởi tạo của lớp đó.
- **Chi tiết**: Nếu lớp có một hoặc nhiều hàm khởi tạo, bạn có thể truyền các tham số cần thiết cho nó. Nếu lớp không có hàm khởi tạo nào được định nghĩa, Scala sẽ tự động tạo một hàm khởi tạo mặc định.

## Ví Dụ
### Ví dụ 1: Khởi Tạo Đối Tượng Không Có Tham Số
```scala
class Person {
  var name: String = "Unknown"
}

val person1 = new Person()
println(person1.name) // Kết quả: Unknown
```

### Ví dụ 2: Khởi Tạo Đối Tượng Với Tham Số
```scala
class Person(val name: String)

val person2 = new Person("John Doe")
println(person2.name) // Kết quả: John Doe
```

### Ví dụ 3: Khởi Tạo Đối Tượng Trong Một Lớp
```scala
class Car(val model: String) {
  def info(): String = s"Car model: $model"
}

val car = new Car("Toyota")
println(car.info()) // Kết quả: Car model: Toyota
```

## Giải Thích
- **Những điểm cần lưu ý**: 
  - Khi sử dụng `new`, bạn không cần phải sử dụng từ khóa `new` khi khởi tạo đối tượng cho các lớp case class. Ví dụ: 
    ```scala
    case class User(name: String)
    val user = User("Alice") // Không cần từ khóa new
    ```
  - Từ khóa `new` không chỉ áp dụng cho các lớp mà còn cho các kiểu dữ liệu như `Array`, `List`, v.v.

- **Cái bẫy phổ biến**: Một số lập trình viên mới có thể không chú ý đến việc khởi tạo đúng các tham số trong hàm khởi tạo, dẫn đến lỗi biên dịch. Hãy chắc chắn rằng các tham số bạn cung cấp khớp với các tham số mà lớp yêu cầu.

## Tóm Tắt Một Dòng
Từ khóa `new` trong Scala được sử dụng để khởi tạo các đối tượng mới từ các lớp, cho phép lập trình viên tạo ra các thực thể của các kiểu dữ liệu đã định nghĩa.