<!--
Meta Description: # Câu lệnh "if" trong Scala: Cách sử dụng và ví dụ ## Tóm tắt Câu lệnh "if" trong Scala là một cấu trúc điều kiện cho phép lập trình viên kiểm tra các...
Meta Keywords: điều, kiện, câu, lệnh, khối
-->

# Câu lệnh "if" trong Scala: Cách sử dụng và ví dụ

## Tóm tắt
Câu lệnh "if" trong Scala là một cấu trúc điều kiện cho phép lập trình viên kiểm tra các điều kiện và thực hiện các khối mã khác nhau dựa trên kết quả của các điều kiện đó.

## Tài liệu
Câu lệnh "if" trong Scala là một phần thiết yếu trong lập trình điều kiện. Nó cho phép bạn xác định một điều kiện và thực hiện các hành động khác nhau tùy theo việc điều kiện đó có đúng hay không.

### Mục đích
Mục đích của câu lệnh "if" là để kiểm tra các điều kiện và thực hiện các khối mã khác nhau. Nếu điều kiện là đúng (true), khối mã sau câu lệnh "if" sẽ được thực thi. Nếu điều kiện là sai (false), bạn có thể cung cấp một khối mã thay thế với câu lệnh "else".

### Cách sử dụng
Câu lệnh "if" có thể được sử dụng theo nhiều cách khác nhau, bao gồm cả các câu lệnh đơn giản và phức tạp. Cú pháp cơ bản của câu lệnh "if" như sau:

```scala
if (điều_kiện) {
  // Khối mã thực hiện khi điều kiện đúng
} else {
  // Khối mã thực hiện khi điều kiện sai (tùy chọn)
}
```

Ngoài ra, bạn cũng có thể sử dụng "else if" để kiểm tra nhiều điều kiện khác nhau:

```scala
if (điều_kiện_1) {
  // Khối mã khi điều kiện 1 đúng
} else if (điều_kiện_2) {
  // Khối mã khi điều kiện 2 đúng
} else {
  // Khối mã khi tất cả điều kiện trên đều sai
}
```

## Ví dụ
### Ví dụ 1: Câu lệnh "if" cơ bản
```scala
val x = 10
if (x > 5) {
  println("x lớn hơn 5")
} else {
  println("x không lớn hơn 5")
}
```

### Ví dụ 2: Sử dụng "else if"
```scala
val y = 15
if (y < 10) {
  println("y nhỏ hơn 10")
} else if (y < 20) {
  println("y nhỏ hơn 20 nhưng lớn hơn hoặc bằng 10")
} else {
  println("y lớn hơn hoặc bằng 20")
}
```

## Giải thích
- **Cú pháp không bắt buộc dấu ngoặc**: Trong Scala, dấu ngoặc đơn không cần thiết cho câu lệnh "if" nếu điều kiện là một biểu thức một dòng. Tuy nhiên, việc sử dụng dấu ngoặc có thể làm cho mã dễ đọc hơn.
  
- **Các khối mã có thể là biểu thức**: Trong Scala, khối mã trong câu lệnh "if" có thể trả về giá trị, tương tự như một biểu thức. Điều này cho phép bạn sử dụng câu lệnh "if" trực tiếp trong các biểu thức khác.

### Lưu ý thường gặp
- **Kiểm tra điều kiện đúng**: Hãy chắc chắn rằng điều kiện được kiểm tra là một biểu thức boolean (true hoặc false).
- **Sử dụng đúng kiểu dữ liệu**: Đảm bảo rằng các biến được sử dụng trong điều kiện có kiểu dữ liệu phù hợp với phép toán bạn đang thực hiện.

## Tóm tắt một dòng
Câu lệnh "if" trong Scala cho phép lập trình viên kiểm tra điều kiện và thực hiện các khối mã khác nhau dựa trên kết quả của điều kiện đó.