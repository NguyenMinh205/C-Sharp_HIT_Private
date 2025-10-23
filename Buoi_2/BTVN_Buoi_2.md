# Bài tập về nhà C# buổi 2

## **Bài 1: “Thử thách Tam Giác Nhiệm Màu” 🛕**

### Yêu cầu
Người chơi nhập vào độ dài ba thanh gỗ khác nhau, hệ thống cần xác định xem có thể ghép lại thành **một tam giác** không.  
Nếu có, hãy cho biết đó là:
- Tam giác đều (3 cạnh bằng nhau)
- Tam giác cân (2 cạnh bằng nhau)
- Tam giác thường (3 cạnh khác nhau)

Nếu không thể tạo tam giác, hiển thị thông báo “Ba thanh gỗ này không thể ghép thành hình tam giác!

### 🧾 Ví dụ minh họa
| Input (a, b, c) | Output |
|------------------|--------|
| 5, 5, 5          | Tam giác đều |
| 6, 6, 9          | Tam giác cân |
| 3, 4, 5          | Tam giác thường |
| 2, 3, 6          | Không thể tạo thành tam giác |

---

## **Bài 2: “Máy tính hình học mini” 📐**

### Yêu cầu
Viết chương trình hiển thị menu cho người dùng lựa chọn loại hình để tính diện tích:

1️⃣ Hình tròn (nhập bán kính)  
2️⃣ Hình chữ nhật (nhập chiều dài và chiều rộng)  
3️⃣ Hình tam giác (nhập đáy và chiều cao)

Sau khi chọn, hệ thống in ra kết quả diện tích tương ứng.  

### 🧾 Ví dụ minh họa
| Lựa chọn | Dữ liệu nhập | Output |
|-----------|---------------|--------|
| 1 | r = 4 | Diện tích hình tròn = 50.27 |
| 2 | a = 5, b = 3 | Diện tích hình chữ nhật = 15 |
| 3 | d = 6, h = 5 | Diện tích hình tam giác = 15 |

---

## **Bài 3: “Vẽ tam giác số đối xứng”**

## **Đề bài:**

Viết chương trình **C#** để **vẽ một tam giác số đối xứng** theo mẫu dưới đây.  
Tam giác được tạo thành từ các chữ số, trong đó:

- Mỗi hàng **bắt đầu và kết thúc bằng số 1**.  
- Các số trong hàng **tăng dần từ 1 đến i**, sau đó **giảm dần trở lại 1**.  
- Toàn bộ tam giác được **căn giữa** theo chiều ngang để tạo hình cân đối.

---

## **Yêu cầu cụ thể:**

1. Chương trình yêu cầu người dùng **nhập vào một số nguyên dương `n`**, là **chiều cao của tam giác** (tức là số hàng cần in ra).  
2. Với mỗi hàng `i` (từ 1 đến `n`):
   - In ra `(n - i)` khoảng trắng ở đầu để căn giữa.  
   - Sau đó in dãy số **tăng dần từ 1 đến i**.  
   - Tiếp theo in dãy số **giảm dần từ (i - 1)** về 1.  
3. Sau khi hoàn tất, chương trình hiển thị kết quả **tam giác số đối xứng** ra màn hình.

---

## **Ví dụ minh họa:**
### input
```
n = 5
```
### output
```
    1
   121
  12321
 1234321
1234543221
```

---

## **Bài 4: “Trò ghép từ bí ẩn” ✍️**

### 🧠 Yêu cầu
Người chơi nhập vào 3 chuỗi:
1. Chuỗi ban đầu  
2. Chuỗi cần tìm  
3. Chuỗi cần chèn  

Hãy chèn chuỗi con (3) **vào trước lần xuất hiện đầu tiên** của chuỗi (2) trong chuỗi ban đầu.

Nếu chuỗi cần tìm không tồn tại, hiển thị thông báo "Không thể ghép từ – đoạn không tồn tại!

### 🧾 Ví dụ minh họa
| Input | Output |
|--------|--------|
| Chuỗi ban đầu: `Lan dang doc sach`<br>Chuỗi cần tìm: `doc`<br>Chuỗi cần chèn: `cham chi` | Kết quả: `Lan dang cham chi doc sach` |

---

## **Bài 5: “Thống kê điểm lớp học” 🎓

### 🧠 Yêu cầu
Viết chương trình sử dụng **hàm tự định nghĩa** để xử lý danh sách điểm của một lớp học.  
Chương trình cần thực hiện các công việc sau:

1️⃣ **Nhập dữ liệu**
- Nhập số lượng học sinh `n` (n > 0).  
- Nhập `n` điểm (từ 0 đến 10).  

2️⃣ **Sử dụng các hàm tự định nghĩa** để:
- Tính **điểm trung bình** của lớp
- Tìm **điểm cao nhất và thấp nhất**
- Tính **tỷ lệ học sinh đạt (điểm ≥ 5.0)**
- Phân loại học sinh theo thang điểm:
  - Giỏi: ≥ 8.0  
  - Khá: [6.5 – 7.9]  
  - Trung bình: [5.0 – 6.4]  
  - Yếu: < 5.0  

3️⃣ **In báo cáo tổng kết**
- Trung bình lớp  
- Điểm cao nhất, thấp nhất  
- Tỉ lệ đạt (%)  
- Số lượng học sinh ở từng loại (Giỏi, Khá, Trung bình, Yếu)

### 🧾 Ví dụ minh họa
**Input**
```
Số học sinh: 6
Điểm: 9, 8, 7, 5, 4, 10
```
**Output**
```
Trung bình lớp: 7.17
Điểm cao nhất: 10
Điểm thấp nhất: 4
Tỉ lệ đạt: 83.33%
Phân loại:
Giỏi: 2 học sinh
Khá: 2 học sinh
Trung bình: 1 học sinh
Yếu: 1 học sinh
```
