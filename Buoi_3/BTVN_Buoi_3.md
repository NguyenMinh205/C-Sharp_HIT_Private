# Bài tập về nhà C# buổi 3

## 🧾 **Bài 1: “Thử thách Dấu Ngoặc Ma Thuật” 🧩**

### 🧠 Yêu cầu
Một chuỗi ký tự chứa các loại dấu ngoặc `()`, `[]`, `{}` được coi là **bùa chú hợp lệ** nếu:
- Mỗi dấu mở đều có dấu đóng tương ứng.
- Thứ tự đóng mở hoàn toàn chính xác.

Hãy viết chương trình kiểm tra xem chuỗi nhập vào có hợp lệ hay không.  
Nếu hợp lệ → in “✨ Yes”  
Nếu không → in “❌ No”

### 🧾 Ví dụ minh họa
| Input | Output |
|--------|--------|
| `{[()]}` | Yes |
| `{(])}` | No |
| `{[}]` | No |

---

## 🧾 **Câu 2 – Đảo ngược chuỗi**
Viết chương trình để đảo ngược thứ tự các ký tự trong một chuỗi bất kỳ do người dùng nhập vào.

## **Yêu cầu**
1. Người dùng nhập vào một chuỗi (có thể chứa chữ cái, số hoặc ký tự đặc biệt).  
2. Chương trình **không được dùng hàm có sẵn như `Reverse()` hoặc `Array.Reverse()`**.  
3. In ra **chuỗi sau khi đã đảo ngược**.

## **Ví dụ minh họa**

| **Input** | **Output** |
|------------|------------|
| Hello World | dlroW olleH |
| ABC123 | 321CBA |
| ChatGPT | TPGtahC |

---

## 🧾 **Câu 3 – Quản lý bán hàng**
Viết chương trình C# để quản lý dữ liệu bán hàng theo mã sản phẩm. Mỗi sản phẩm có Name, Price, Quantity (số lượng bán được). Hệ thống phải hỗ trợ thao tác thêm, cập nhật, thống kê và xuất báo cáo.

1. **Định nghĩa struct `Product`** gồm các trường:
   - `Name` : tên sản phẩm  
   - `Price` : giá bán  
   - `Quantity` : số lượng bán được
   - `Category` : danh mục

2. **Tạo cấu trúc dữ liệu chính:**
 ```csharp
Dictionary<string, Product>
```
Trong đó:
- Khóa ngoài (string): mã sản phẩm
- Giá trị (Product): thông tin chi tiết của sản phẩm đã bán

3. Viết các phương thức:
- Thêm dữ liệu sản phẩm mới. Sản phẩm đã tồn tại → cộng dồn số lượng bán
- Trả về thông tin sản phẩm dựa theo mã sản phẩm
- Tính sản phẩm bán chạy nhất theo số lượng bán được
- Tính sản phẩm bán chạy nhất theo danh mục
- Tính tổng doanh thu theo danh mục
