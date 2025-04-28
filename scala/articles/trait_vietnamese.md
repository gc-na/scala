<!--
Meta Description: # Trait trong Scala: Đặc Điểm, Cách Sử Dụng và Ví Dụ Cụ Thể ## Tóm Tắt Trait trong Scala là một cấu trúc cho phép tái sử dụng mã nguồn, hỗ trợ tính kế...
Meta Keywords: trait, một, thể, scala, trong
-->

# Trait trong Scala: Đặc Điểm, Cách Sử Dụng và Ví Dụ Cụ Thể

## Tóm Tắt
Trait trong Scala là một cấu trúc cho phép tái sử dụng mã nguồn, hỗ trợ tính kế thừa và lập trình hướng đối tượng, giúp xây dựng các lớp một cách linh hoạt và hiệu quả.

## Tài Liệu
Trait là một khái niệm quan trọng trong Scala, cho phép bạn định nghĩa một tập hợp các phương thức (methods) và thuộc tính (fields) mà có thể được chia sẻ giữa nhiều lớp (classes). Trait tương tự như interface trong Java, nhưng nó có thể chứa cả phương thức đã được triển khai (implemented methods) và phương thức trừu tượng (abstract methods).

### Mục Đích
- **Tái sử dụng mã nguồn**: Trait cho phép bạn định nghĩa hành vi chung mà có thể được chia sẻ giữa nhiều lớp khác nhau.
- **Hỗ trợ kế thừa đa hình**: Scala cho phép một lớp kế thừa từ nhiều trait, giúp tạo ra các cấu trúc phức tạp hơn một cách dễ dàng.

### Cách Sử Dụng
Để định nghĩa một trait trong Scala, bạn sử dụng từ khóa `trait`, sau đó là tên của trait và các phương thức cần thiết. Một lớp có thể kế thừa từ một hoặc nhiều trait bằng cách sử dụng từ khóa `extends` và `with`.

```scala
trait HanhVi {
  def di(): Unit
}

trait HanhViChay extends HanhVi {
  def chay(): Unit = println("Chạy")
}

class ConMeo extends HanhViChay {
  def di(): Unit = println("Đi")
}

object Main extends App {
  val meo = new ConMeo
  meo.di()   // In ra: Đi
  meo.chay() // In ra: Chạy
}
```

## Ví Dụ
Dưới đây là một ví dụ cụ thể về cách sử dụng trait trong Scala:

```scala
trait ChucNang {
  def inThongTin(): Unit
}

class NhanVien(val ten: String) extends ChucNang {
  def inThongTin(): Unit = println(s"Tên nhân viên: $ten")
}

class QuanLy(ten: String, val phongBan: String) extends NhanVien(ten) {
  override def inThongTin(): Unit = {
    super.inThongTin()
    println(s"Phòng ban: $phongBan")
  }
}

object Main extends App {
  val nhanVien = new QuanLy("Nguyễn Văn A", "Kế Toán")
  nhanVien.inThongTin()
}
```

## Giải Thích
Một số điều cần lưu ý khi làm việc với trait trong Scala:
- **Kế thừa nhiều trait**: Một lớp có thể kế thừa từ nhiều trait, nhưng thứ tự kế thừa có thể ảnh hưởng đến cách phương thức được gọi.
- **Phương thức mặc định**: Trait có thể cung cấp các phương thức mặc định, giúp giảm thiểu mã lặp lại.
- **Trait không thể tạo ra thể hiện**: Bạn không thể tạo ra một thể hiện trực tiếp từ một trait, cần phải kế thừa nó trong một lớp.

## Tóm Tắt Một Dòng
Trait trong Scala là một công cụ mạnh mẽ cho phép tái sử dụng mã nguồn và hỗ trợ kế thừa đa hình, giúp phát triển ứng dụng một cách hiệu quả và linh hoạt.