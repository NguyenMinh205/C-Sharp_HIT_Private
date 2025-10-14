# Lý thuyết C# buổi 3 (Collection)

## 1. Tổng quan về collections trong C#
Collections là tập hợp các lớp hỗ trợ lưu trữ, quản lý và thao tác với các đối tượng một cách có thứ tự. Các lớp này nằm trong namespace System.Collections.

### Đặc điểm của Collections
- Là mảng có kích thước động, có thể tự tăng hoặc giảm số phần tử.
- Lưu trữ linh hoạt: chứa nhiều kiểu dữ liệu khác nhau.
- Cung cấp nhiều phương thức hỗ trợ như tìm kiếm, sắp xếp, đảo ngược, thêm, xóa, v.v.
- Là các lớp đối tượng nên cần khởi tạo trước khi sử dụng.

### Ưu điểm so với mảng
- Có nhiều lớp phục vụ các mục đích khác nhau.
- Truy xuất phần tử bằng chỉ số hoặc khóa (key).
- Hỗ trợ tìm kiếm nhanh (ví dụ: HashTable dùng bảng băm).
- Hỗ trợ thêm/xóa linh hoạt (ArrayList).
- Bao gồm cả các cấu trúc dữ liệu phổ biến như Stack và Queue.

### Một số loại Collection phổ biến

| **Tên Lớp**  | **Mô tả** |
|---------------|------------|
| **ArrayList** | Mảng động, có thể tự tăng kích thước. |
| **HashTable** | Lưu dữ liệu dạng **Key–Value**. |
| **SortedList** | Kết hợp `ArrayList` và `HashTable`, luôn được sắp xếp theo **Key**. |
| **Stack** | Ngăn xếp, hoạt động theo nguyên lý **LIFO (Last In – First Out)**. |
| **Queue** | Hàng đợi, hoạt động theo nguyên lý **FIFO (First In – First Out)**. |
| **BitArray** | Lưu danh sách các bit *(true = 1, false = 0)*. |

## 2. List Trong C#
List<T> là một Generic Collection, tương tự ArrayList nhưng có kiểu dữ liệu xác định.
Thuộc namespace: System.Collections.Generic.

### Ví dụ khởi tạo:
```csharp
List<int> numbers = new List<int>();
List<int> numbers2 = new List<int>(5); // Chỉ định sức chứa ban đầu
List<int> numbers3 = new List<int>(numbers2); // Sao chép danh sách khác
```

### Một số thuộc tính
- Count: Số phần tử hiện có.
- Capacity: Sức chứa (có thể thay đổi tự động).

### Phương thức hỗ trợ sẵn trong List
| **Phương thức**         | **Chức năng**                           |
|--------------------------|-----------------------------------------|
| `Add(value)`             | Thêm phần tử vào cuối danh sách.        |
| `AddRange(list)`         | Thêm danh sách khác vào cuối.           |
| `Clear()`                | Xóa toàn bộ phần tử.                    |
| `Contains(value)`        | Kiểm tra tồn tại phần tử.               |
| `IndexOf(value)`         | Vị trí đầu tiên xuất hiện.              |
| `Insert(index, value)`   | Chèn phần tử tại vị trí chỉ định.       |
| `Remove(value)`          | Xóa phần tử đầu tiên tìm thấy.          |
| `Sort()`                 | Sắp xếp danh sách.                      |
| `ToArray()`              | Chuyển `List` sang mảng.                |

### Ví dụ:
```csharp
List<string> MyList = new List<string>();
MyList.Add("Free");
MyList.Add("Education");

foreach (string item in MyList)
{
    Console.WriteLine(item);
}
```

## 3. Dictionary Trong C#
Dictionary<TKey, TValue> lưu trữ dữ liệu dưới dạng cặp Key–Value, là bản nâng cấp của Hashtable.
Thuộc namespace: System.Collections.Generic.

```csharp
Dictionary<string, string> dic = new Dictionary<string, string>();
dic.Add("C", "Chi");
dic.Add("P", "Pi");
```

### Một số thuộc tính và phương thức hỗ trợ sẵn

| **Thành phần**                     | **Mô tả**                        |
|-----------------------------------|----------------------------------|
| `Count`                           | Số phần tử hiện có.              |
| `Keys / Values`                   | Danh sách khóa / giá trị.        |
| `Add(key, value)`                 | Thêm cặp Key–Value.              |
| `ContainsKey(key)`                | Kiểm tra tồn tại khóa.           |
| `Remove(key)`                     | Xóa phần tử theo khóa.           |
| `TryGetValue(key, out value)`     | Lấy giá trị an toàn, không lỗi.  |

### Duyệt Dictionary
```csharp
foreach (KeyValuePair<string, string> item in dic)
{
    Console.WriteLine($"{item.Key}: {item.Value}");
}
```

## 4. Stack Trong C#
Stack là cấu trúc dữ liệu LIFO (Last In – First Out) – phần tử vào sau được lấy ra trước.

### Một số thuộc tính và phương thức hỗ trợ sẵn
| **Tên**          | **Mô tả**                              |
|------------------|----------------------------------------|
| `Push(value)`    | Thêm phần tử vào đỉnh Stack.           |
| `Pop()`          | Lấy và xóa phần tử ở đỉnh Stack.       |
| `Peek()`         | Xem phần tử ở đỉnh Stack mà không xóa. |
| `Clear()`        | Xóa toàn bộ phần tử.                   |
| `Count`          | Số phần tử hiện có.                    |

### Ví dụ
```csharp
Stack MyStack = new Stack();
MyStack.Push("Pi");
MyStack.Push("Chi");
MyStack.Push("ChiPi");

Console.WriteLine(MyStack.Peek()); // Xem phần tử đầu
Console.WriteLine(MyStack.Pop());  // Lấy ra phần tử cuối cùng
```

## 5. Queue Trong C#
Queue là cấu trúc dữ liệu FIFO (First In – First Out) – phần tử vào trước được lấy ra trước.

### Một số thuộc tính và phương thức hỗ trợ sẵn
| **Tên**             | **Mô tả**                              |
|---------------------|----------------------------------------|
| `Enqueue(value)`    | Thêm phần tử vào cuối hàng đợi.        |
| `Dequeue()`         | Lấy và xóa phần tử đầu tiên.           |
| `Peek()`            | Xem phần tử đầu tiên mà không xóa.     |
| `Count`             | Số phần tử hiện có.                    |

### Ví dụ:
```csharp
Queue q = new Queue();
q.Enqueue("Chi");
q.Enqueue("Pi");
q.Enqueue("ChiPi");

Console.WriteLine(q.Peek());
Console.WriteLine(q.Dequeue());
```

## 6. Enum Trong C#
Enum là kiểu liệt kê (Enumeration) – tập hợp các hằng số có liên quan.
Mỗi phần tử là một giá trị nguyên cố định.

### Khai báo và sử dụng
Cú pháp:
```csharp
enum Color
{
    RED,
    BLUE,
    YELLOW
}
```

### Quy tắc:
- Mặc định giá trị bắt đầu từ 0 và tăng dần.
- Có thể gán giá trị cụ thể:
VD:
```csharp
enum Color { RED = 2, BLUE = 4, YELLOW = 6 }
```

### Ép kiểu và truy xuất:
```csharp
int choose = (int)Color.BLUE; // 1
Color c = (Color)2;           // Color.YELLOW
```

Ưu điểm:
- Dễ quản lý và gợi ý trong IDE.
- Tránh việc phải nhớ hàng loạt hằng rời rạc.

## 7. Struct Trong C#
Struct là kiểu dữ liệu có cấu trúc, gộp nhiều biến có liên quan.
Lưu trữ trên Stack (khác với Class lưu trên Heap), hiệu năng cao, nhẹ.

### Đặc điểm
- Là kiểu tham trị.
- Không thể kế thừa, nhưng có thể triển khai interface.
- Có thể chứa: field, property, method, constructor, event.
- Không dùng được null (trừ khi Nullable<T>).
- Thường dùng cho các đối tượng nhỏ: Vector2, Point, Color.

### Khai báo và sử dụng
Cú pháp:
```csharp
struct Point
{
    public int x, y;
    public Point(int x, int y)
    {
        this.x = x; this.y = y;
    }
    public void ShowInfo()
    {
        Console.WriteLine($"Toạ độ: ({x}, {y})");
    }
}
```

Ví dụ:
```csharp
Point p1 = new Point(5, 10);
Point p2;
p2.x = 3; p2.y = 7;

p1.ShowInfo();
p2.ShowInfo();
```

Kết quả:
```csharp
Tọa độ: (5, 10)
Tọa độ: (3, 7)
```