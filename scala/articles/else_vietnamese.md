<!--
Meta Description: # Câu Lệnh "else" trong Scala: Hướng Dẫn Chi Tiết và Ví Dụ ## Tóm Tắt Câu lệnh "else" trong Scala là một phần quan trọng của cấu trúc điều kiện, cho p...
Meta Keywords: câu, lệnh, else, điều, kiện
-->

# Câu Lệnh "else" trong Scala: Hướng Dẫn Chi Tiết và Ví Dụ

## Tóm Tắt
Câu lệnh "else" trong Scala là một phần quan trọng của cấu trúc điều kiện, cho phép lập trình viên thực hiện các hành động khác nhau dựa trên điều kiện đã cho. Nó thường được sử dụng để xử lý các tình huống mà điều kiện trước đó không được thỏa mãn.

## Tài Liệu
Câu lệnh "else" được sử dụng trong các biểu thức điều kiện trong Scala để chỉ định hành động sẽ được thực hiện khi điều kiện trước đó (sử dụng "if") không đúng. Câu lệnh này thường đi kèm với câu lệnh "if" để tạo thành một cấu trúc điều kiện hoàn chỉnh.

### Cú Pháp
```scala
if (điều_kiện) {
  // Thực hiện hành động nếu điều kiện đúng
} else {
  // Thực hiện hành động nếu điều kiện sai
}
```

### Chi Tiết
- **Mục Đích**: Câu lệnh "else" cho phép bạn xác định các hành động khác nhau dựa trên kết quả của một điều kiện "if".
- **Sử Dụng**: Câu lệnh "else" có thể được sử dụng một mình hoặc kết hợp với nhiều câu lệnh "if" khác nhau (cấu trúc lồng nhau).
- **Lưu ý**: Câu lệnh "else" không cần một điều kiện đi kèm; nó sẽ tự động được thực thi nếu điều kiện "if" không đúng.

## Ví Dụ
Dưới đây là một số ví dụ về cách sử dụng câu lệnh "else" trong Scala:

### Ví Dụ 1: Sử Dụng Cơ Bản
```scala
val age = 18

if (age >= 18) {
  println("Bạn đã đủ tuổi.")
} else {
  println("Bạn chưa đủ tuổi.")
}
```

### Ví Dụ 2: Cấu Trúc Lồng Nhau
```scala
val score = 85

if (score >= 90) {
  println("Xuất sắc")
} else if (score >= 75) {
  println("Khá")
} else {
  println("Cần cải thiện")
}
```

### Ví Dụ 3: Kết Hợp Với Các Câu Lệnh Khác
```scala
val number = -5

if (number >= 0) {
  println("Số dương hoặc bằng không")
} else {
  println("Số âm")
}
```

## Giải Thích
Một số vấn đề thường gặp khi sử dụng câu lệnh "else":
- **Không có câu lệnh "if"**: Câu lệnh "else" cần phải luôn đi kèm với một câu lệnh "if". Nếu không, chương trình sẽ không biên dịch.
- **Cấu trúc lồng nhau**: Khi sử dụng cấu trúc lồng nhau, dễ dẫn đến nhầm lẫn trong việc xác định điều kiện nào đang được kiểm tra. Cần chú ý đến độ thụt lề để đảm bảo mã nguồn rõ ràng.

## Tóm Tắt Một Câu
Câu lệnh "else" trong Scala cho phép xác định hành động thay thế khi điều kiện trong câu lệnh "if" không được thỏa mãn.