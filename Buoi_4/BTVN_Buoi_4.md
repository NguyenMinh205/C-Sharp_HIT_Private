# Bài tập về nhà C# buổi 4

## Bài 1:
## 1. Xây dựng lớp PERSON
Tạo lớp **Person** với các yêu cầu sau:

### Thuộc tính (private):
- Họ tên  
- Tuổi  
- Địa chỉ  

### Yêu cầu:
- Tất cả các biến phải khai báo dạng **private**  
- Truy cập thông qua **Property (get/set)**

### Phương thức:
- **Constructor** – không đối số và có đầy đủ đối số

---

## 2. Xây dựng lớp CONGNHAN kế thừa từ PERSON
Tạo lớp **CongNhan : Person** với yêu cầu sau:

### Thuộc tính thêm (private + property):
- Mã công nhân
- Chức vụ (**dùng enum ChucVu**)

```csharp
public enum ChucVu
{
    TruongNhom,
    PhoNhom,
    CongNhanBac3,
    CongNhanBac2,
    CongNhanBac1,
    Khac
}

### Phương thức:
- **Constructor** – không đối số và có đầy đủ đối số
- **TinhLuong()** – trả về:  
```
Luong = HeSoLuong × 8000000
```
Trong đó:
- Nếu chức vụ = `"Trưởng nhóm"` → hệ số lương = **3.0**  
- Nếu chức vụ = `"Phó nhóm"` → hệ số lương = **2.5**  
- Nếu chức vụ = `"Công nhân bậc 3"` → hệ số lương = **2.0**  
- Nếu chức vụ = `"Công nhân bậc 2"` → hệ số lương = **1.5**  
- Nếu chức vụ = `"Công nhân bậc 1"` → hệ số lương = **1.2**  
- Nếu chức vụ khác → hệ số lương = **1.0**

---

## 3. Viết mã trong phương thức Main
Trong phương thức **Main()**, thực hiện:
1. Tạo menu gồm các chức năng: Thêm, Hiển thị danh sách, Sắp xếp, Tìm công nhân theo Mã, Thoát. Chương trình chỉ kết thúc khi người dùng chọn Thoát.
2. Khi người dùng chọn Thêm: tạo đối tượng công nhân, nhập thông tin cho công nhân, thêm công nhân mới vào danh sách. Không cho phép thêm công nhân trùng mã.
3. Khi người dùng chọn Hiển thị danh sách: Hiển thị danh sách công nhân, thông tin mỗi công nhân trên 1 dòng. Các thông tin gồm: Mã công nhân, họ tên, tuổi, địa chỉ, chức vụ, lương.
4. Khi người dùng chọn Sắp xếp: hiển thị danh sách các công nhân được sắp xếp theo họ tên tăng dần. Nếu họ tên giống nhau thì sắp xếp theo lương tăng dần.
5. Khi người dùng chọn Tìm công nhân theo Mã: hiển thị công nhân tìm được theo mã công nhân. Nếu không có trả về thông báo tương ứng.

---

## 4. Yêu cầu bổ sung
- Tuổi phải > 0 
- Nếu nhập sai thì yêu cầu nhập lại  

---


