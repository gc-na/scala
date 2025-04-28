<!--
Meta Description: # Cách sử dụng `def` trong Scala: Định nghĩa Hàm ## Tóm tắt Câu lệnh `def` trong Scala được sử dụng để định nghĩa các hàm, cho phép lập trình viên tạo...
Meta Keywords: hàm, scala, def, định, kiểu
-->

# Cách sử dụng `def` trong Scala: Định nghĩa Hàm

## Tóm tắt
Câu lệnh `def` trong Scala được sử dụng để định nghĩa các hàm, cho phép lập trình viên tạo ra các khối mã có thể tái sử dụng.

## Tài liệu
Câu lệnh `def` là một phần quan trọng trong ngôn ngữ lập trình Scala. Nó giúp lập trình viên định nghĩa các hàm với cú pháp rõ ràng và dễ hiểu. Để định nghĩa một hàm, bạn sử dụng cú pháp sau:

```scala
def tenHam(thamSo1: Kieu, thamSo2: Kieu, ...): KieuTraVe = {
  // Thân hàm
}
```

- `tenHam`: Tên của hàm.
- `thamSo`: Các tham số đầu vào của hàm, bao gồm tên và kiểu dữ liệu.
- `KieuTraVe`: Kiểu dữ liệu mà hàm sẽ trả về.
- Thân hàm chứa mã mà hàm sẽ thực hiện.

Hàm trong Scala có thể không có tham số và không cần kiểu trả về nếu nó không cần trả giá trị.

## Ví dụ
### Ví dụ 1: Hàm không có tham số
```scala
def sayHello(): Unit = {
  println("Hello, Scala!")
}
```

### Ví dụ 2: Hàm có tham số và kiểu trả về
```scala
def add(a: Int, b: Int): Int = {
  a + b
}
```

### Ví dụ 3: Hàm không có kiểu trả về
```scala
def printMessage(message: String) {
  println(message)
}
```

## Giải thích
Mặc dù việc sử dụng `def` rất đơn giản, nhưng vẫn có một số điều cần lưu ý:

- **Kiểu trả về**: Nếu không chỉ định kiểu trả về, Scala sẽ tự động suy diễn kiểu. Tuy nhiên, việc khai báo rõ ràng kiểu trả về giúp mã nguồn dễ đọc hơn.
  
- **Hàm ẩn danh**: Trong một số trường hợp, bạn có thể sử dụng hàm ẩn danh (lambda) thay vì định nghĩa hàm bằng `def`. Điều này có thể giúp mã ngắn gọn hơn.

- **Gọi hàm**: Để gọi một hàm đã định nghĩa, bạn chỉ cần sử dụng tên hàm kèm theo các tham số (nếu có).

- **Tham số mặc định**: Scala hỗ trợ tham số mặc định, cho phép bạn gọi hàm mà không cần cung cấp tất cả các tham số.

## Tóm tắt một dòng
Câu lệnh `def` trong Scala cho phép lập trình viên định nghĩa và sử dụng các hàm một cách dễ dàng và hiệu quả.