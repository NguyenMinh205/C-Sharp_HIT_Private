# Lý thuyết C# buổi 2 (Phần 2)

## 11. Cấu Trúc Lệnh Rẽ Nhánh if else Trong C#

Cấu trúc rẽ nhánh là phương pháp để chương trình đưa ra quyết định, thực hiện các hành động khác nhau tùy vào điều kiện. Nó dùng để kiểm tra và thực hiện hành động trong các trường hợp khác nhau.

### Các loại cấu trúc rẽ nhánh trong C#:

* `if-else`: Cấu trúc điều kiện phổ biến, giúp thực hiện hành động dựa trên một điều kiện.
* `switch-case`: Một cách khác để thực hiện các quyết định, thường dùng khi có nhiều giá trị để so sánh.

### Cấu trúc if đơn giản:

```csharp
if ([Biểu thức điều kiện])
    <Câu lệnh thực hiện>;
```

**Ý nghĩa:** Nếu biểu thức điều kiện trả về `true`, thực hiện câu lệnh sau `if`, ngược lại không làm gì.

### Cấu trúc if-else đầy đủ:

```csharp
if ([Biểu thức điều kiện])
    <Câu lệnh thực hiện 1>;
else
    <Câu lệnh thực hiện 2>;
```

**Ý nghĩa:** Nếu điều kiện đúng, thực hiện lệnh 1; nếu sai, thực hiện lệnh 2.

### Lưu ý khi sử dụng:

* Biểu thức điều kiện phải trả về `true` hoặc `false`.
* Nên dùng `{}` khi có nhiều câu lệnh để dễ đọc.
* Có thể lồng nhiều `if-else` (nested).
* Có thể dùng `if-else if-else` để xử lý nhiều trường hợp.

### Sự khác biệt với toán tử ba ngôi:

* `if-else` giúp thực hiện nhiều câu lệnh, dễ đọc.
* Toán tử ba ngôi `?:` dùng cho các trường hợp đơn giản.

---

## 12. Cấu Trúc switch case Trong C#

Cấu trúc `switch-case` so sánh một biểu thức với nhiều giá trị khả dĩ khác nhau. Khi có giá trị trùng khớp, chương trình thực thi lệnh tương ứng; nếu không, dùng `default`.

### Cấu trúc dạng thiếu:

```csharp
switch (<biểu thức>)
{
    case <giá trị 1>:
        <câu lệnh 1>;
        break;
    case <giá trị 2>:
        <câu lệnh 2>;
        break;
}
```

### Cấu trúc dạng đủ:

```csharp
switch (<biểu thức>)
{
    case <giá trị 1>:
        <câu lệnh 1>;
        break;
    case <giá trị 2>:
        <câu lệnh 2>;
        break;
    default:
        <câu lệnh mặc định>;
        break;
}
```

### Lưu ý:

* `break` là bắt buộc để kết thúc case.
* Kiểu dữ liệu của biểu thức và case phải khớp nhau.
* `default` là tùy chọn nhưng nên có để xử lý ngoại lệ.

---

## 13. Vòng Lặp Trong C#

Vòng lặp là chuỗi các hành động lặp lại đến khi thỏa mãn điều kiện dừng.

### Các loại vòng lặp:

* `for`: Lặp với số lần xác định.
* `while`: Lặp khi điều kiện là `true`.
* `do-while`: Lặp ít nhất một lần rồi kiểm tra điều kiện.
* `foreach`: Duyệt qua các phần tử trong tập hợp.
* `goto`: Nhảy đến nhãn khác (hiếm dùng).

### Vòng lặp for

```csharp
for ([Khởi tạo]; [Điều kiện]; [Bước lặp])
{
    // Khối lệnh
}
```

* **Khởi tạo:** Thực hiện 1 lần trước khi lặp.
* **Điều kiện:** Kiểm tra trước mỗi vòng.
* **Bước lặp:** Thực hiện sau mỗi vòng.

### Vòng lặp while

```csharp
while (điều_kiện)
{
    // Khối lệnh
}
```

* Kiểm tra điều kiện trước khi lặp.

### Vòng lặp do-while

```csharp
do
{
    // Khối lệnh
} while (điều_kiện);
```

* Thực hiện ít nhất 1 lần trước khi kiểm tra điều kiện.

---

## 14. Mảng Trong C#

### Khái niệm:

* Mảng là tập hợp các phần tử cùng kiểu dữ liệu, lưu liên tiếp trong bộ nhớ.
* Mỗi phần tử có chỉ số (index) bắt đầu từ 0.

### Mảng một chiều:

```csharp
<kiểu dữ liệu>[] <tên mảng> = new <kiểu dữ liệu>[số phần tử];
int[] arr = {10, 20, 30};
```

**Truy xuất:**

```csharp
Console.WriteLine(arr[1]); // In ra 20
arr[2] = 50;
```

**Duyệt mảng:**

```csharp
for (int i = 0; i < arr.Length; i++)
    Console.WriteLine(arr[i]);
```

### Mảng hai chiều:

```csharp
int[,] matrix = new int[2,3] {{1,2,3},{4,5,6}};
for (int i = 0; i < matrix.GetLength(0); i++)
{
    for (int j = 0; j < matrix.GetLength(1); j++)
    {
        Console.Write(matrix[i, j] + "\t");
    }
    Console.WriteLine();
}
```

---

## 15. Chuỗi (string) Trong C#

### Khái niệm:

* `string` là kiểu tham chiếu dùng để lưu chuỗi ký tự.
* Chuỗi là **immutable** (bất biến) – khi thay đổi sẽ tạo chuỗi mới.

### Một số phương thức thông dụng:

* `Length` – Trả độ dài chuỗi.
* `String.Compare(a, b)` – So sánh 2 chuỗi.
* `String.Concat(a, b)` – Nối chuỗi.
* `IndexOf(c)` – Tìm vị trí đầu tiên của ký tự.
* `Insert(index, s)` – Chèn chuỗi.
* `IsNullOrEmpty(s)` – Kiểm tra chuỗi rỗng/null.
* `Remove(start, count)` – Xóa ký tự.
* `Replace(old, new)` – Thay ký tự.
* `Split(c)` – Cắt chuỗi thành mảng.
* `Substring(start, len)` – Cắt chuỗi con.

### Lớp StringBuilder:

* Cho phép chỉnh sửa trực tiếp chuỗi (ít tốn bộ nhớ hơn `string`).

```csharp
StringBuilder sb = new StringBuilder("Hello");
sb.Append(" World");
Console.WriteLine(sb.ToString());
```

---

## 16. Hàm Trong C#

### Khái niệm & Cú pháp:

Hàm (method) là khối lệnh có tên, thực hiện một nhiệm vụ, có thể nhận tham số và có/không trả giá trị.

```csharp
<Phạm vi> <Kiểu trả về> <Tên hàm>([tham_số]) { }
```

### Hàm Main:

```csharp
static void Main(string[] args) { }
```

* `static`: bắt buộc với `Main` trong Console app.
* `void`: không trả giá trị.
* `string[] args`: đối số dòng lệnh.

### Hàm void (không trả giá trị):

```csharp
static void Demo()
{
    Console.WriteLine("Hello!");
}
```

### Hàm có kiểu trả về:

```csharp
static int Sum(int a, int b)
{
    return a + b;
}
```

### Tham số:

* Dùng để truyền dữ liệu vào hàm.
* Có thể truyền nhiều tham số, ngăn cách bằng dấu phẩy.

```csharp
Console.WriteLine(Sum(5, 10)); // Kết quả: 15
```

> Vì `Main` là static nên các hàm muốn gọi trong đó cũng nên khai báo static (nếu không tạo object).
