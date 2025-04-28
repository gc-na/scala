<!--
Meta Description: # Từ Khóa "extends" Trong Scala: Cách Mở Rộng Lớp và Giao Diện ## Tóm Tắt Từ khóa "extends" trong Scala được sử dụng để định nghĩa mối quan hệ kế thừa...
Meta Keywords: lớp, một, extends, thừa, scala
-->

# Từ Khóa "extends" Trong Scala: Cách Mở Rộng Lớp và Giao Diện

## Tóm Tắt
Từ khóa "extends" trong Scala được sử dụng để định nghĩa mối quan hệ kế thừa giữa các lớp và giao diện, cho phép một lớp kế thừa các thuộc tính và phương thức từ lớp cha hoặc giao diện.

## Tài Liệu
### Mục Đích
Từ khóa "extends" trong Scala cho phép lập trình viên tạo ra một lớp mới (lớp con) dựa trên một lớp hiện có (lớp cha). Điều này giúp tái sử dụng mã, mở rộng chức năng và tổ chức mã nguồn một cách có cấu trúc hơn.

### Cách Sử Dụng
Cú pháp cơ bản để sử dụng từ khóa "extends" là:

```scala
class TenLopCon extends TenLopCha {
  // Các thuộc tính và phương thức của lớp con
}
```

Bạn cũng có thể sử dụng "extends" để kế thừa từ một giao diện:

```scala
trait TenGiaoDien {
  def phuongThuc(): Unit
}

class TenLop extends TenGiaoDien {
  def phuongThuc(): Unit = {
    println("Thực hiện phương thức từ giao diện.")
  }
}
```

### Chi Tiết
- Khi bạn khai báo một lớp con, nó có thể kế thừa tất cả các thuộc tính và phương thức công khai (public) và bảo vệ (protected) từ lớp cha.
- Nếu lớp cha có một constructor (hàm khởi tạo), bạn cần gọi nó trong lớp con bằng cách sử dụng `extends` và có thể truyền các tham số cần thiết.
- Scala cho phép kế thừa từ một lớp cha duy nhất, nhưng một lớp có thể thực thi nhiều giao diện.

## Ví Dụ
### Ví Dụ 1: Kế Thừa Lớp
```scala
class DongVat {
  def keu(): Unit = {
    println("Tôi là một động vật.")
  }
}

class Cho extends DongVat {
  override def keu(): Unit = {
    println("Gâu gâu!")
  }
}

val cho = new Cho()
cho.keu()  // Kết quả: Gâu gâu!
```

### Ví Dụ 2: Kế Thừa Giao Diện
```scala
trait Hinh {
  def dienTich(): Double
}

class HinhChuNhat(val chieuDai: Double, val chieuRong: Double) extends Hinh {
  def dienTich(): Double = {
    chieuDai * chieuRong
  }
}

val hcn = new HinhChuNhat(5, 3)
println(hcn.dienTich())  // Kết quả: 15.0
```

## Giải Thích
Một số vấn đề thường gặp khi sử dụng từ khóa "extends":
- **Không thể kế thừa từ nhiều lớp**: Scala không hỗ trợ kế thừa từ nhiều lớp, điều này có thể gây khó khăn khi bạn muốn kết hợp các chức năng từ nhiều nguồn khác nhau.
- **Thứ tự khởi tạo**: Khi kế thừa, lớp cha sẽ được khởi tạo trước lớp con. Do đó, bạn cần chú ý đến việc khởi tạo các thuộc tính trong lớp cha.
- **Phương thức trùng lặp**: Khi lớp con định nghĩa lại một phương thức đã có trong lớp cha, bạn cần sử dụng từ khóa `override` để chỉ định rằng bạn đang ghi đè phương thức đó.

## Tóm Tắt Một Dòng
Từ khóa "extends" trong Scala cho phép bạn kế thừa thuộc tính và phương thức từ lớp cha hoặc giao diện, tạo nên các lớp con mạnh mẽ và linh hoạt.