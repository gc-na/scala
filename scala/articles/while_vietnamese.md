<!--
Meta Description: # Câu Lệnh "while" trong Scala: Sử Dụng, Ví Dụ và Lưu Ý ## Tóm Tắt Câu lệnh "while" trong Scala là một cấu trúc điều kiện cho phép lập trình viên thực...
Meta Keywords: trong, điều, while, kiện, lặp
-->

# Câu Lệnh "while" trong Scala: Sử Dụng, Ví Dụ và Lưu Ý

## Tóm Tắt
Câu lệnh "while" trong Scala là một cấu trúc điều kiện cho phép lập trình viên thực hiện một khối mã lặp lại cho đến khi điều kiện được chỉ định trở thành sai.

## Tài Liệu
Câu lệnh "while" là một trong những cấu trúc điều khiển lặp cơ bản trong Scala. Nó cho phép bạn thực hiện một khối mã lặp lại miễn là điều kiện được chỉ định là đúng (true). Cú pháp cơ bản của câu lệnh "while" như sau:

```scala
while (điều kiện) {
  // khối mã cần thực hiện
}
```

### Mục Đích
Câu lệnh "while" được sử dụng khi bạn không biết trước số lần lặp, mà chỉ muốn tiếp tục lặp cho đến khi một điều kiện trở thành sai.

### Cách Sử Dụng
- **Điều kiện**: Là biểu thức Boolean, nếu đúng, khối mã bên trong sẽ được thực hiện.
- **Khối mã**: Là đoạn mã sẽ được thực hiện trong mỗi lần lặp.

### Chi Tiết
- Đảm bảo điều kiện sẽ trở thành sai trong một khoảng thời gian nhất định để tránh vòng lặp vô hạn.
- Khối mã bên trong có thể thay đổi giá trị của biến mà điều kiện kiểm tra.

## Ví Dụ
Dưới đây là một số ví dụ đơn giản để minh họa cách sử dụng câu lệnh "while":

### Ví Dụ 1: Đếm từ 1 đến 5
```scala
var i = 1
while (i <= 5) {
  println(i)
  i += 1
}
```
**Kết quả**: In ra các số từ 1 đến 5.

### Ví Dụ 2: Tính tổng các số nguyên từ 1 đến n
```scala
val n = 10
var sum = 0
var i = 1
while (i <= n) {
  sum += i
  i += 1
}
println(s"Tổng từ 1 đến $n là $sum")
```
**Kết quả**: In ra tổng từ 1 đến 10.

## Giải Thích
### Cạm Bẫy Thường Gặp
- **Vòng lặp vô hạn**: Nếu điều kiện trong "while" luôn đánh giá là đúng, chương trình sẽ không bao giờ dừng lại.
- **Biến không được cập nhật**: Đảm bảo rằng biến được sử dụng trong điều kiện sẽ thay đổi trong khối mã để điều kiện có thể trở thành sai.

### Lưu Ý
- **Hiệu suất**: Sử dụng "while" có thể kém hiệu quả hơn so với các cấu trúc lặp khác như "for" trong một số trường hợp, đặc biệt khi số lần lặp là xác định.

## Tóm Tắt Một Dòng
Câu lệnh "while" trong Scala cho phép lặp lại một khối mã miễn là điều kiện được chỉ định là đúng, rất hữu ích trong các tình huống mà số lần lặp không được biết trước.