# Lý thuyết C# buổi 2 (Phần 1)

## 1. Giới thiệu ngôn ngữ C#

C# là một ngôn ngữ lập trình hướng đối tượng, bậc cao, có cấu trúc rõ ràng, dễ hiểu và dễ học, được Microsoft xây dựng dựa trên C++ và Java. C# thừa hưởng những ưu việt từ ngôn ngữ Java và C++ cũng như khắc phục được những hạn chế của các ngôn ngữ này.

---

## 2. Cấu Trúc Chương Trình Cơ Bản C# Console

```csharp
using System;

namespace CauTrucLenhCoBan
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Hello HIT");
            Console.ReadKey();
        }
    }
}
```

* **using:** Lệnh Using dùng để chỉ cho trình biên dịch biết rằng những thư viện được sử dụng trong chương trình.
* **namespace:** Báo cho trình biên dịch biết rằng các thành phần bên trong khối `{ }` ngay bên dưới tên namespace thuộc vào chính namespace đó.
* **class:** Báo cho trình biên dịch biết rằng những thành phần trong khối `{ }` ngay sau tên lớp thuộc vào chính lớp đó.
* **Hàm (Phương thức) Main():** Đây là hàm chính – điểm bắt đầu chương trình.

---

## 3. Comment và dấu chấm phẩy

### Có 3 cách để comment code trong Visual Studio:

* `//` → comment 1 dòng.
* `/* ... */` → comment nhiều dòng.
* `///` → comment tài liệu (XML Documentation).

### Lưu ý:

Mỗi khi kết thúc một dòng lệnh, ta viết thêm dấu `;` ngay phía sau đoạn code đó để báo hiệu kết thúc dòng lệnh hiện tại.

---

## 4. Nhập Xuất Cơ Bản Trong C#

Trong C# có 5 lệnh dùng để nhập xuất:

### Xuất dữ liệu:

* `Console.Write()` – In giá trị ra màn hình console mà không xuống dòng.
* `Console.WriteLine()` – In giá trị ra màn hình console và sau đó xuống dòng.
* `Console.Write("\n")` – Xuống dòng bằng ký tự đặc biệt.
* `Console.Write(Environment.NewLine)` – Xuống dòng bằng lệnh hệ thống.

### Nhập dữ liệu:

* `Console.Read()` – Đọc một ký tự từ bàn phím và trả về mã ASCII của ký tự đó.
* `Console.ReadLine()` – Đọc dữ liệu từ bàn phím cho đến khi nhấn Enter và trả về một chuỗi.
* `Console.ReadKey()` – Đọc một ký tự từ bàn phím và trả về thông tin về phím đó.

---

## 5. Biến trong C#

### Khái niệm:

* Là tên đại diện cho vùng nhớ lưu dữ liệu có thể thay đổi.
* Là thành phần cơ bản của mọi chương trình.

### Cú pháp:

```csharp
<Kiểu dữ liệu> <Tên biến>;
```

### Ví dụ:

```csharp
int age;
float score;
string name;
bool isPassed;
char grade;
```

### Gán giá trị:

```csharp
age = 20;
string student = "HIT";
int a = 1, b = 2;
int c = a + b;
```

### Quy tắc đặt tên biến:

* Không có khoảng trắng hoặc ký tự đặc biệt.
* Không dùng tiếng Việt có dấu.
* Không bắt đầu bằng số.
* Không trùng với từ khóa.
* Phân biệt chữ hoa chữ thường.

#### Quy tắc Lạc Đà (camelCase):

* Viết thường từ đầu tiên, viết hoa chữ cái đầu tiên của những từ tiếp theo.
* Dùng cho biến có phạm vi truy cập là private/protected hoặc tham số hàm.
* Ví dụ: `educationFree`, `chiPhi`.

#### Quy tắc PascalCase:

* Viết hoa chữ cái đầu tiên của mỗi từ.
* Dùng cho tên hàm, Interface, Enum, Sự kiện, v.v.
* Ví dụ: `GetUserName`, `PrintResult`.

---

## 6. Biến Toàn Cục Và Biến Cục Bộ Trong C#

* **Biến toàn cục:** Khai báo ở phân cấp cao hơn vị trí đang xác định.
* **Biến cục bộ:** Khai báo ở cùng phân cấp tại vị trí đang xác định.
* **Parameter:** Là một biến cục bộ.

### Vòng đời:

* Bắt đầu khi khối lệnh chứa nó bắt đầu (`{`) và kết thúc khi khối lệnh kết thúc (`}`).

> Biến cục bộ được ưu tiên sử dụng hơn biến toàn cục nếu trùng tên.

---

## 7. Kiểu dữ liệu trong C#

### Khái niệm:

* Là tập hợp các nhóm dữ liệu có cùng đặc tính, cách lưu trữ và thao tác xử lý.
* Là tín hiệu để trình biên dịch nhận biết kích thước và khả năng lưu trữ của biến.

### Phân loại kiểu dữ liệu:

1. **Kiểu dữ liệu dựng sẵn (built-in)** và **Kiểu dữ liệu do người dùng định nghĩa (user-defined).**
2. Mỗi loại chia thành:

   * **Kiểu dữ liệu giá trị (value type):** lưu trực tiếp giá trị trong Stack.
     *Ví dụ:* `bool`, `byte`, `short`, `int`, `long`, `float`, `double`, `decimal`, `char`, `struct`.
   * **Kiểu dữ liệu tham chiếu (reference type):** lưu địa chỉ trong Stack, giá trị trong Heap.
     *Ví dụ:* `object`, `dynamic`, `string`, và các kiểu người dùng định nghĩa.

---

## 8. Toán Tử Trong C#

### Phân loại:

* **Toán tử toán học:** `+`, `-`, `*`, `/`, `%`, `++`, `--`
* **Toán tử quan hệ:** `==`, `!=`, `>`, `<`, `>=`, `<=`
* **Toán tử logic:** `&&`, `||`, `!`
* **Toán tử gán:** `=`, `+=`, `-=`, `*=`, `/=`, `%=`
* **Toán tử bit:** `&`, `|`, `^`, `~`, `<<`, `>>`

### Toán tử khác:

* `sizeof()` → Trả về kích cỡ của một kiểu dữ liệu.
* `typeof()` → Trả về kiểu dữ liệu của một lớp.
* `new` → Cấp phát vùng nhớ mới.
* `is` → Xác định kiểu đối tượng.
* `as` → Ép kiểu an toàn, nếu sai trả `null`.
* `?:` → Toán tử ba ngôi.

---

## 9. Hằng Trong C#

### Khái niệm:

* Là biến có giá trị không thay đổi trong suốt chương trình.
* Bắt buộc phải khởi tạo giá trị khi khai báo.

### Các loại hằng:

1. **Giá trị hằng:**

   ```csharp
   const int MAX = 100;
   ```

2. **Biểu tượng hằng:**

   ```csharp
   #define DEBUG
   #undef DEBUG
   ```

3. **Kiểu liệt kê (enum):**

   ```csharp
   enum Level { Low, Medium, High }
   ```

---

## 10. Ép Kiểu Trong C#

### Khái niệm:

Ép kiểu là biến đổi dữ liệu từ kiểu dữ liệu này sang kiểu khác.

### Các loại ép kiểu:

1. **Chuyển đổi ngầm định (implicit)**
2. **Chuyển đổi tường minh (explicit)**
3. **Dùng phương thức/lớp hỗ trợ:** `Parse()`, `TryParse()`, `Convert`.
4. **Người dùng tự định nghĩa:** Tạo hàm chuyển đổi riêng giữa các kiểu.
