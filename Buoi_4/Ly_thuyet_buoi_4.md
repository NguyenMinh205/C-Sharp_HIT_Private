# Lý thuyết C# buổi 4 (OOP - Phần 1)

## **1. TỔNG QUAN VỀ LẬP TRÌNH HƯỚNG ĐỐI TƯỢNG (OOP)**

### **1.1. Khái niệm chung**

Lập trình hướng đối tượng (Object-Oriented Programming – OOP) là mô hình lập trình dựa trên **lớp (class)** và **đối tượng (object)**. Mỗi đối tượng là một thực thể trong thế giới thực, có **thuộc tính (property)** và **phương thức (method)** riêng.

### **1.2. Sự tiến hóa của lập trình**

* **Lập trình tuyến tính**: Viết mã theo thứ tự, không chia nhỏ logic → khó bảo trì.
* **Lập trình có cấu trúc (Procedural)**: Chia nhỏ chương trình thành hàm, thủ tục → dễ đọc hơn nhưng dữ liệu và hành vi vẫn tách rời.
* **Lập trình hướng đối tượng (OOP)**: Kết hợp dữ liệu và hành vi vào cùng một thực thể → dễ mở rộng, bảo trì, tái sử dụng.

### **1.3. 4 đặc tính cơ bản của OOP**

1. **Tính đóng gói (Encapsulation)** – Ẩn dữ liệu, chỉ cung cấp giao diện truy cập an toàn.
2. **Tính trừu tượng (Abstraction)** – Chỉ hiển thị những gì cần thiết, che giấu chi tiết thực thi.
3. **Tính kế thừa (Inheritance)** – Cho phép lớp con kế thừa thuộc tính/phương thức của lớp cha.
4. **Tính đa hình (Polymorphism)** – Cùng một hành động có thể có nhiều cách thực hiện khác nhau tùy đối tượng.

### **1.4. Nguyên tắc SOLID trong OOP**

* **S – Single Responsibility**: Mỗi lớp chỉ nên có một nhiệm vụ duy nhất.
* **O – Open/Closed**: Mở rộng được nhưng hạn chế sửa đổi trực tiếp.
* **L – Liskov Substitution**: Lớp con có thể thay thế lớp cha mà không làm sai logic.
* **I – Interface Segregation**: Interface nên được chia nhỏ, cụ thể mục tiêu.
* **D – Dependency Inversion**: Mô-đun cấp cao không phụ thuộc vào cấp thấp, mà cùng phụ thuộc abstraction.

---

## **2. CLASS TRONG C#**

### **2.1. Khái niệm**

Class là khuôn mẫu để tạo đối tượng. Mỗi class bao gồm:

* **Field/Property:** là các thành phần dữ liệu hay còn gọi là các biến.
* **Method:** là các hàm thành phần thể hiện các hành vi của một đối tượng thuộc lớp.
* **Constructor:** hàm khởi tạo giá trị ban đầu.
* **Destructor/Finalizer:** hàm thu hồi tài nguyên khi đối tượng bị hủy.

### **2.2. Khai báo, khởi tạo và sử dụng class**
- Cú pháp:
```csharp
class <tên lớp>
{
    <Phạm vi truy cập> <Các thành phần của lớp>;
}
```
- Trong đó:
* <tên lớp> là tên do người dùng đặt và tuân theo quy tắc đặt tên.
* <Phạm vi truy cập> bao gồm các từ khoá như public, protected, private, static, . . .
* <Các thành phần của lớp> bao gồm các biến, phương thức của lớp. Các biến được khai báo như khai báo biến bình thường. Các phương thức (hàm) được khai báo như khai báo hàm.

**Ví dụ**
```csharp
class Animal
{
    public double Weight { get; set; }
    public double Height { get; set; }

    public void Run()
    {
        Console.WriteLine("Animal is running...");
    }
}
```

```csharp
Animal dog = new Animal();
dog.Weight = 5;
dog.Height = 40;
dog.Run();
```

### **2.3. Constructor và Destructor (Finalizer)**

```csharp
class Cat : IDisposable
{
    public double Weight { get; set; }

    // Constructor có tham số
    public Cat(double w)
    {
        Weight = w;
    }

    // Finalizer
    ~Cat()
    {
        Console.WriteLine("Finalizer executed");
    }

    // Giải phóng tài nguyên thủ công
    public void Dispose()
    {
        Console.WriteLine("Dispose called");
        GC.SuppressFinalize(this);
    }
}
```

### **2.4. Auto Property và Init Accessor**
**Auto Property:** là một cách viết ngắn gọn để khai báo thuộc tính mà không cần tạo biến private tương ứng.
**Init Accessor**: Từ C# 9.0 trở đi, Microsoft giới thiệu init như một cách thay thế set, cho phép gán giá trị chỉ một lần duy nhất — tại thời điểm khởi tạo object (qua constructor hoặc object initializer).
```csharp
public class Student
{
    public string Name { get; init; }  // chỉ gán được khi khởi tạo
    public int Age { get; set; }
}
```

### **2.5. So sánh Class và Struct**

| Đặc điểm             | Class                       | Struct                          |
| -------------------- | --------------------------- | ------------------------------- |
| Loại dữ liệu         | Tham chiếu (reference type) | Giá trị (value type)            |
| Lưu trữ              | Heap                        | Stack                           |
| Kế thừa              | Có                          | Không                           |
| Constructor mặc định | Có                          | Từ C# 10, struct cũng có thể có |
| Finalizer            | Có                          | Không                           |

---

## **3. PHẠM VI TRUY CẬP VÀ TÍNH ĐÓNG GÓI (ACCESS MODIFIERS & ENCAPSULATION)**

### **3.1. Khái niệm đóng gói**
Đóng gói là việc **che giấu thông tin bên trong lớp**, chỉ cho phép bên ngoài truy cập qua **phương thức hoặc property an toàn**.

### **3.2. Công cụ đóng gói trong C#**
Sử dụng các phạm vi truy cập (`private`, `protected`, `public`, …) để kiểm soát mức độ truy cập.

| Từ khóa | Mô tả |
|----------|-------|
| `public` | Truy cập được ở mọi nơi. |
| `private` | Chỉ truy cập trong cùng lớp. |
| `protected` | Truy cập trong lớp và lớp dẫn xuất. |
| `internal` | Truy cập trong cùng assembly. |
| `protected internal` | Truy cập từ lớp dẫn xuất hoặc trong cùng assembly. |
| `private protected` | Truy cập trong lớp và lớp con trong cùng assembly. |

### **3.3. Property và Getter/Setter**
```csharp
private double _score;
public double Score
{
    get => _score;
    set => _score = Math.Clamp(value, 0, 10);
}
```

### Ví dụ: Đóng gói trong thực tế
```csharp
class CoinAccount
{
    private double numOfCoin;

    public double NumOfCoin
    {
        get => numOfCoin;
        private set
        {
            if (value >= 0)
                numOfCoin = value;
        }
    }

    public void Deposit(double amount)
    {
        if (amount > 0)
            NumOfCoin += amount;
    }

    public void Withdraw(double amount)
    {
        if (amount > 0 && amount <= Balance)
            NumOfCoin -= amount;
    }
}
```

### 3.4. Lợi ích của đóng gói
* Bảo vệ dữ liệu khỏi thay đổi không hợp lệ.
* Giúp mã dễ bảo trì, mở rộng.
* Che giấu chi tiết thực thi, chỉ cung cấp giao diện sử dụng.

---

## **4. KẾ THỪA (INHERITANCE)**

### **4.1. Khái niệm**

Kế thừa cho phép lớp con sử dụng và mở rộng chức năng của lớp cha.

### **4.2. Cú pháp và ví dụ**

```csharp
class Animal
{
    public double Weight { get; set; }
    public virtual void Speak() => Console.WriteLine("Animal sound");
}

class Dog : Animal
{
    public override void Speak() => Console.WriteLine("Woof!");
}
```

### **4.3. Gọi constructor cha bằng `base`**

```csharp
class Cat : Animal
{
    public Cat(double w) : base()
    {
        Weight = w;
    }
}
```

### **4.4. Che khuất phương thức (`new`) và ngăn kế thừa (`sealed`)**

```csharp
class A
{
    public virtual void Show() => Console.WriteLine("A");
}

class B : A
{
    public sealed override void Show() => Console.WriteLine("B");
}
```

---

## **5. TÍNH ĐA HÌNH (POLYMORPHISM)**

### **5.1. Khái niệm**

Tính đa hình cho phép nhiều đối tượng phản ứng khác nhau với cùng một lệnh.

### **5.2. Dạng compile-time và runtime**

* **Compile-time:** Overloading (nhiều phương thức cùng tên, khác tham số).
* **Runtime:** `virtual`/`override` hoặc interface.

### **5.3. Ví dụ**

```csharp
class Animal
{
    public virtual void Speak() => Console.WriteLine("Animal");
}

class Cat : Animal
{
    public override void Speak() => Console.WriteLine("Meow");
}
```

### **5.4. Interface-based Polymorphism**

```csharp
interface IShape { double Area(); }
class Circle : IShape { public double Radius { get; set; } public double Area() => Math.PI * Radius * Radius; }
class Square : IShape { public double Side { get; set; } public double Area() => Side * Side; }
```

---

## **6. TỪ KHÓA `STATIC`**

### **6.1. Biến và phương thức tĩnh**

```csharp
class Counter
{
    public static int Count { get; private set; }
    public Counter() => Count++;
}
```

### **6.2. Static Constructor**

```csharp
class Config
{
    public static string AppName { get; }
    static Config()
    {
        AppName = "OOP Example";
        Console.WriteLine("Static constructor chạy một lần");
    }
}
```

### **6.3. Const vs Static Readonly**

| Thành phần        | Thời điểm gán | Có thể thay đổi          |
| ----------------- | ------------- | ------------------------ |
| `const`           | Compile-time  | Không                    |
| `static readonly` | Runtime       | Có thể trong constructor |

---

## **7. TỪ KHÓA `THIS`**

### **7.1. Ý nghĩa**

`this` đại diện cho **đối tượng hiện tại** – cho phép truy cập thuộc tính hoặc phương thức trong cùng class.

### **7.2. Ứng dụng phổ biến**

```csharp
class Student
{
    private string name;
    public Student(string name)
    {
        this.name = name; // phân biệt biến cục bộ và field
    }
}
```

### **7.3. Gọi constructor khác trong cùng lớp**

```csharp
class Rectangle
{
    private int width, height;

    public Rectangle() { width = 10; height = 5; }

    public Rectangle(int w) : this() // gọi constructor mặc định
    {
        width = w;
    }
}
```