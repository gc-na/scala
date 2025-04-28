<!--
Meta Description: # Hiểu về "yield" trong Scala: Tính Năng Quan Trọng để Tạo Ra Các Collection ## Tóm Tắt Từ khóa "yield" trong Scala cho phép người dùng tạo ra một col...
Meta Keywords: collection, yield, một, trong, các
-->

# Hiểu về "yield" trong Scala: Tính Năng Quan Trọng để Tạo Ra Các Collection

## Tóm Tắt
Từ khóa "yield" trong Scala cho phép người dùng tạo ra một collection mới từ một collection hiện có thông qua các phép toán được thực hiện trên các phần tử của nó. Đây là một công cụ mạnh mẽ trong lập trình hàm, giúp tối ưu hóa và làm cho mã nguồn trở nên rõ ràng hơn.

## Tài Liệu
### Mục Đích
"yield" được sử dụng trong các vòng lặp để thu thập và trả về các giá trị mới, tạo thành một collection mới từ những giá trị đã được xử lý. Điều này rất hữu ích khi bạn muốn biến đổi một collection mà không cần phải viết nhiều dòng mã.

### Cách Sử Dụng
Cú pháp của "yield" thường được sử dụng trong vòng lặp `for`. Dưới đây là cấu trúc cơ bản:

```scala
val newCollection = for (element <- oldCollection) yield {
  // Biến đổi element
}
```

Trong đó:
- `oldCollection` là collection hiện có (ví dụ: List, Array, v.v.)
- `newCollection` là collection mới được tạo ra từ các giá trị đã biến đổi.

### Chi Tiết
- "yield" có thể được sử dụng với nhiều loại collection trong Scala, bao gồm List, Set, Map, và Array.
- Kết quả của một biểu thức "yield" sẽ là một collection mới, giữ nguyên các thuộc tính của collection gốc.

## Ví Dụ
### Ví Dụ Cơ Bản 1: Sử Dụng với List
```scala
val numbers = List(1, 2, 3, 4, 5)
val doubled = for (n <- numbers) yield n * 2
println(doubled) // Kết quả: List(2, 4, 6, 8, 10)
```

### Ví Dụ Cơ Bản 2: Lọc và Biến Đổi
```scala
val names = List("Alice", "Bob", "Charlie")
val lengths = for (name <- names if name.startsWith("A")) yield name.length
println(lengths) // Kết quả: List(5)
```

### Ví Dụ Cơ Bản 3: Sử Dụng với Tuples
```scala
val pairs = List((1, "one"), (2, "two"), (3, "three"))
val numbersOnly = for ((num, _) <- pairs) yield num
println(numbersOnly) // Kết quả: List(1, 2, 3)
```

## Giải Thích
- Một trong những cạm bẫy phổ biến khi sử dụng "yield" là việc quên thêm điều kiện lọc (if clause) trong vòng lặp có thể dẫn đến collection mới chứa nhiều giá trị không mong muốn.
- "yield" không thay đổi collection gốc mà chỉ tạo ra một bản sao mới, giúp bảo toàn tính bất biến (immutability) của các collection trong Scala.
- Việc sử dụng "yield" có thể làm cho mã nguồn trở nên dễ hiểu hơn, đặc biệt là khi xử lý các collection phức tạp.

## Tóm Tắt Một Dòng
Từ khóa "yield" trong Scala cho phép tạo ra một collection mới từ một collection hiện có thông qua các phép toán biến đổi trên các phần tử của nó.