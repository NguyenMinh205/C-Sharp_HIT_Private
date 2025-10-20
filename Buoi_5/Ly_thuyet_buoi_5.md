# Lý thuyết C# buổi 5 (OOP - Phần 2)

## **1. Method Overloading và Overriding**

### 🔹 Overloading (Nạp chồng phương thức)
- Cho phép nhiều phương thức **cùng tên nhưng khác tham số** (số lượng, kiểu dữ liệu hoặc thứ tự tham số).  
- Thể hiện **đa hình ở thời điểm biên dịch** (compile-time polymorphism).  

**Ví dụ:**
```csharp
public class Player
{
    public void TanCong() => Console.WriteLine("Tấn công tay: 10 sát thương");
    public void TanCong(string vuKhi) => Console.WriteLine($"Tấn công bằng {vuKhi}");
    public void TanCong(string vuKhi, int soDan) => Console.WriteLine($"Bắn bằng {vuKhi} với {soDan} viên đạn");
}
```

### 🔹 Overriding (Ghi đè phương thức)
- Lớp con ghi đè lại hành vi của phương thức được định nghĩa ở lớp cha.
- Thể hiện đa hình ở thời điểm thực thi (runtime polymorphism).

**Ví dụ:**
```csharp
public abstract class Weapon
{
    public abstract void TanCong();
}

public class Sword : Weapon
{
    public override void TanCong() => Console.WriteLine("Vung kiếm chém, 25 sát thương!");
}
```

### So sánh Overloading vs Overriding

| **Tiêu chí** | **Overloading** | **Overriding** |
|---------------|------------------|----------------|
| **Vị trí định nghĩa** | Trong cùng một lớp | Giữa lớp cha và lớp con |
| **Tên phương thức** | Giống nhau | Giống nhau |
| **Tham số (parameter)** | Phải khác nhau (số lượng, kiểu hoặc thứ tự) | Giống hoàn toàn |
| **Từ khóa sử dụng** | Không cần từ khóa đặc biệt | Dùng `virtual` (ở lớp cha) và `override` (ở lớp con) |
| **Thời điểm xác định** | Khi biên dịch (*compile time*) | Khi thực thi (*runtime*) |
| **Mục đích** | Tăng tính linh hoạt trong cùng hành động | Tùy biến lại hành vi của lớp cha |
| **Đa hình** | *Compile-time Polymorphism* | *Runtime Polymorphism* |


## 2. Interface trong OOP C#
### Khái niệm
Interface là bản hợp đồng hành vi, chỉ định nghĩa “làm gì” chứ không nói “làm như thế nào”. Các lớp triển khai interface phải cài đặt toàn bộ phương thức được khai báo.

**Ví dụ:**
```csharp
interface IMovable
{
    void Move(float speed);
}

class Player : IMovable
{
    public void Move(float speed) => Console.WriteLine($"Player di chuyển với tốc độ {speed}");
}
```

### Đặc điểm
- Không có triển khai (chỉ khai báo).
- Tất cả thành phần trong interface đều public.
- Một lớp có thể kế thừa nhiều interface.
- Không có biến, constructor hay destructor.

### Mục đích: 
- Tăng tính trừu tượng và tính linh hoạt.
- Đảm bảo đồng nhất hành vi giữa các lớp.
- Là giải pháp thay thế đa kế thừa trong C#.

## 3. Generic trong C#
### Khái niệm
Generic (kiểu tổng quát) cho phép viết lớp, phương thức hoặc interface có thể làm việc với nhiều kiểu dữ liệu khác nhau mà không cần viết lại code.

**Ví dụ:**
```csharp
public static void Swap<T>(ref T a, ref T b)
{
    T temp = a;
    a = b;
    b = temp;
}
```

- Khi gọi: Swap<int>(ref x, ref y) hoặc Swap<string>(ref a, ref b) đều hợp lệ.

### Ưu điểm
- Tăng khả năng tái sử dụng code.
- An toàn kiểu dữ liệu (type safety).
- Giảm số dòng code trùng lặp.
- Tối ưu hiệu suất (không cần boxing/unboxing).

## 4. Delegate trong C#
### Khái niệm
Delegate là kiểu dữ liệu lưu trữ tham chiếu đến một hoặc nhiều phương thức.
Giúp truyền phương thức như tham số, tương tự callback function.

**Ví dụ**
```csharp
delegate void Notify();

class Game
{
    public static void ShowMessage() => Console.WriteLine("Wave đã bắt đầu!");
}

class Program
{
    static void Main()
    {
        Notify n = Game.ShowMessage;
        n(); // Gọi delegate
    }
}
```

### Multicast Delegate
Một delegate có thể gọi nhiều phương thức cùng lúc:
```csharp
Notify n = StartWave;
n += SpawnEnemies;
n += ShowUI;
n();
```

## 5. Nguyên tắc SOLID trong OOP
### Giới thiệu
SOLID là 5 nguyên tắc cốt lõi giúp thiết kế phần mềm dễ bảo trì, mở rộng và test.

### Ý nghĩa nguyên tắc SOLID trong lập trình hướng đối tượng

| **Chữ cái** | **Nguyên tắc** | **Mô tả** |
|--------------|----------------|------------|
| **S** | **Single Responsibility** | Mỗi lớp chỉ có **một nhiệm vụ duy nhất** |
| **O** | **Open/Closed** | Cho phép mở rộng, nhưng không sửa mã gốc |
| **L** | **Liskov Substitution** | Lớp con có thể thay thế lớp cha mà không làm sai hành vi |
| **I** | **Interface Segregation** | Chia nhỏ interface – tránh ép class cài đặt hàm không cần |
| **D** | **Dependency Inversion** | Module cấp cao không phụ thuộc module cấp thấp; dùng interface trung gian |

## 6. Giới thiệu về LINQ trong C#
### Khái niệm
LINQ (Language Integrated Query) cho phép truy vấn dữ liệu trực tiếp trong C# giống như SQL, áp dụng được cho:
- Mảng (Array)
- List<T>, Dictionary<TKey,TValue>
- CSDL (Entity Framework)
- XML hoặc JSON

**Ví dụ**
```csharp
List<Player> players = new List<Player>
{
    new Player { Name = "A", Score = 120 },
    new Player { Name = "B", Score = 200 },
    new Player { Name = "C", Score = 150 }
};

var topPlayers = from p in players
                 where p.Score >= 150
                 orderby p.Score descending
                 select p;

foreach (var p in topPlayers)
    Console.WriteLine($"{p.Name}: {p.Score}");
```

### Ưu điểm
- Cú pháp ngắn gọn, dễ đọc.
- Truy vấn dữ liệu ngay trong C#, không cần chuyển qua SQL thủ công.
- Hỗ trợ lọc, sắp xếp, nhóm, kết nối dữ liệu rất mạnh mẽ.