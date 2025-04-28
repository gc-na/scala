<!--
Meta Description: # Hướng Dẫn Chi Tiết Về Câu Lệnh "import" Trong Scala ## Tóm Tắt Câu lệnh `import` trong Scala cho phép lập trình viên sử dụng các lớp, đối tượng, và ...
Meta Keywords: scala, import, dụng, nhập, lớp
-->

# Hướng Dẫn Chi Tiết Về Câu Lệnh "import" Trong Scala

## Tóm Tắt
Câu lệnh `import` trong Scala cho phép lập trình viên sử dụng các lớp, đối tượng, và hàm từ các gói khác nhau mà không cần phải chỉ định đường dẫn đầy đủ mỗi lần.

## Tài Liệu

### Mục Đích
Câu lệnh `import` được sử dụng để đưa vào không gian tên (namespace) những thành phần từ các gói khác, giúp mã nguồn trở nên ngắn gọn và dễ đọc hơn.

### Cách Sử Dụng
Câu lệnh `import` có thể được sử dụng theo nhiều cách khác nhau:

1. **Nhập toàn bộ gói**:
   ```scala
   import scala.collection._
   ```
   Cách này cho phép bạn sử dụng tất cả các lớp và đối tượng trong gói `scala.collection`.

2. **Nhập một lớp hoặc đối tượng cụ thể**:
   ```scala
   import scala.collection.mutable.ArrayBuffer
   ```
   Chỉ cần nhập lớp `ArrayBuffer` từ gói `scala.collection.mutable`.

3. **Nhập nhiều lớp hoặc đối tượng**:
   ```scala
   import scala.collection.mutable.{ArrayBuffer, ListBuffer}
   ```
   Bạn có thể nhập nhiều lớp trong cùng một dòng bằng cách sử dụng dấu `{}`.

4. **Nhập với bí danh**:
   ```scala
   import scala.math.{Pi => π}
   ```
   Bạn có thể tạo một bí danh cho một lớp hoặc đối tượng bằng cách sử dụng toán tử `=>`.

5. **Nhập cho các thành phần với cùng tên**:
   Nếu bạn cần nhập nhiều thành phần có cùng tên từ các gói khác nhau, bạn có thể sử dụng `import` với bí danh để tránh xung đột.

## Ví Dụ

1. **Nhập toàn bộ gói**:
   ```scala
   import scala.util._
   val randomNum = Random.nextInt(100) // Sử dụng Random mà không cần chỉ định đường dẫn
   ```

2. **Nhập lớp cụ thể**:
   ```scala
   import java.time.LocalDate
   val today = LocalDate.now() // Sử dụng LocalDate
   ```

3. **Nhập với bí danh**:
   ```scala
   import scala.math.{Pi => π}
   println(π) // In ra giá trị của Pi
   ```

## Giải Thích
- **Cạm bẫy và Lưu ý**:
  - Khi sử dụng `import`, hãy cẩn thận với các xung đột tên. Nếu bạn nhập hai lớp có cùng tên từ các gói khác nhau mà không sử dụng bí danh, Scala sẽ báo lỗi.
  - Sử dụng `import` một cách có tổ chức để duy trì tính rõ ràng trong mã nguồn của bạn. Tránh việc nhập toàn bộ gói nếu chỉ cần một vài lớp cụ thể.

## Tóm Tắt Một Dòng
Câu lệnh `import` trong Scala giúp lập trình viên dễ dàng sử dụng các lớp và đối tượng từ các gói khác mà không cần phải chỉ định đường dẫn đầy đủ, tạo điều kiện cho việc viết mã ngắn gọn và rõ ràng.