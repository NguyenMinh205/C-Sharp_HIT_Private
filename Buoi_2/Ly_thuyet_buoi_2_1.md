# Lý thuyết C# buổi 2 (Các kiến thức và thành phần cơ bản trong C#)

## 1. Giới thiệu ngôn ngữ C#
C# là một ngôn ngữ lập trình hướng đối tượng, bậc cao, có cấu trúc rõ ràng, dễ hiểu và dễ học, được Microsoft xây dựng dựa trên C++ và Java. C# thừa hưởng những ưu việt từ ngôn ngữ Java và C++ cũng như khắc phục được những hạn chế của các ngôn ngữ này.

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

- using: Lệnh Using dùng để chỉ cho trình biên dịch biết rằng những thư viện được sử dụng trong chương trình.
- namespace: báo cho trình biên dịch biết rằng các thành phần bên trong khối { } ngay bên dưới tên namespace thuộc vào chính namespace đó. 
- class: báo cho trình biên dịch biết rằng những thành phần trong khối { } ngay sau tên lớp thuộc vào chính lớp đó.
- Hàm (Phương thức) Main(): Đây là hàm chính – điểm bắt đầu chương trình

## 3. Comment và dấu chấm phẩy

### Có 3 cách để comment code trong Visual Studio:
- // → comment 1 dòng
- /* ... */ → comment nhiều dòng
- /// → comment tài liệu (XML Documentation)

### Có một điểm cần lưu ý khi viết code. Mỗi khi kết thúc một dòng lệnh. Chúng ta sẽ viết thêm 1 dấu ; ngay phía sau đoạn code đó để báo hiệu chúng ta đã kết thúc dòng lệnh hiện tại.

## 4. Nhập Xuất Cơ Bản Trong C#
Trong C# có 5 lệnh dùng để nhập xuất đó là:

### Xuất dữ liệu
- Console.Write(): In giá trị ra màn hình console mà không xuống dòng.
- Console.WriteLine(): In giá trị ra màn hình console và sau đó xuống dòng.
- Console.Write("\n"): Xuống dòng bằng ký tự đặc biệt
- Console.Write(Environment.NewLine): Xuống dòng bằng lệnh hệ thống

### Nhập dữ liệu
- Console.Read(): Đọc một ký tự từ bàn phím và trả về mã ASCII của ký tự đó.
- Console.ReadLine(): Đọc dữ liệu từ bàn phím cho đến khi nhấn Enter và trả về một chuỗi.
- Console.ReadKey(): Đọc một ký tự từ bàn phím và trả về thông tin về phím đó.

## 5. Biến trong C#

### Khái niệm: 
- Là tên đại diện cho vùng nhớ lưu dữ liệu có thể thay đổi.
- Là thành phần cơ bản của mọi chương trình.

### Cú pháp
```csharp
<Kiểu dữ liệu> <Tên biến>;
```

- <Kiểu dữ liệu> có thể là:
+ Kiểu dữ liệu cơ bản.
+ Kiểu dữ liệu có cấu trúc
- <Tên biến> :
+ Là tên do người dùng đặt.
+ Phải tuân thủ theo quy tắc đặt tên.

### Ví dụ
```csharp
int age;
float score;
string name;
bool isPassed;
char grade;
```

### Gán giá trị
```csharp
age = 20;
string student = "HIT";
int a = 1, b = 2;
int c = a + b;
```

### Quy tắc đặt tên biến :
- Tên biến là một chuỗi ký tự liên kết (không có khoảng trắng) và không chứa ký tự đặc biệt.
- Tên biến không được đặt bằng tiếng việt có dấu.
- Tên không được bắt đầu bằng số.
- Tên biến không được trùng nhau.
- Tên biến không được trùng với từ khóa.
- Ngoài ra các lập trình viên cũng đưa ra một số quy tắc chung trong việc đặt tên để dễ quản lý và giúp cho người khác có thể dễ dàng đọc code của mình : 
+ Quy tắc Lạc Đà :
* Viết thường từ đầu tiên và viết hoa chữ cái đầu tiên của những từ tiếp theo.
* Thường được dùng để đặt tên cho các biến có phạm vi truy cập là private hoặc protected và các tham số của hàm.
* Ví dụ: educationFree, chiPi, . . .
+ Quy tắc Pascal :
* Viết hoa chữ cái đầu tiên của mỗi từ.
* Thường được dùng để đặt tên cho những thành phần còn lại như hàm, Interface, Enum, Sự kiện, . . .
- Một số lưu ý khi đặt tên biến:
+ Nên đặt tên ngắn gọn dễ hiểu, thể hiện rõ mục đích của biến. Ví dụ như: Name, Tuoi, GioiTinh, . . .
+ Không nên đặt tên biến bằng một ký tự như i, k, m, . . . như vậy sau này khi xem lại code hoặc đưa code cho người khác đọc thì chúng ta sẽ không hiểu biến này dùng để làm gì. Trừ những trường hợp đặc biệt như ở trong vòng lặp, ...
+ C# có phân biệt chữ hoa chữ thường. Ví dụ biến a khác biến A hoặc lệnh Console.WriteLine() khác lệnh Console.WRITELINE().

## 6. Biến Toàn Cục Và Biến Cục Bộ Trong C#
Biến toàn cục là biến được khai báo ở phân cấp cao hơn vị trí đang xác định.

Biến cục bộ là biến được khai báo ở cùng phân cấp tại vị trí đang xác định.

Vòng đời của biến toàn cục và biến cục bộ bắt đầu khi khối lệnh chứa nó bắt đầu (khối lệnh bắt đầu bằng dấu “{“) và kết thúc khi khối lệnh chứa nó kết thúc (khối lệnh kết thúc bằng dấu “}”).

Biến cục bộ được ưu tiên sử dụng hơn biến toàn cục trong trường hợp 2 biến này trùng tên.

Lưu ý:
- Parameter chính là một biến cục bộ.
- Biến cục bộ có phạm vi sử dụng bên trong cặp dấu ngoặc nhọn { }.

## 7. Kiểu dữ liệu trong C#
Khái niệm
- Là tập hợp các nhóm dữ liệu có cùng đặc tính, cách lưu trữ và thao tác xử lý trên trường dữ liệu đó.
- Là một tín hiệu để trình biên dịch nhận biết kích thước của một biến (ví dụ như int là 4 bytes) và khả năng lưu trữ của nó (ví dụ biến kiểu int chỉ có thể chứa được các số nguyên).
- Là thành phần cốt lõi của một ngôn ngữ lập trình.

Phân loại kiểu dữ liệu
- Trong C#, kiểu dữ liệu được chia thành 2 tập hợp kiểu dữ liệu chính: kiểu dữ liệu dựng sẵn (built - in) mà ngôn ngữ cung cấp và kiểu dữ liệu do người dùng định nghĩa (user - defined).
- Mỗi tập hợp kiểu dữ liệu trên lại phân thành 2 loại:
+ Kiểu dữ liệu giá trị (value): Một biến khi khai báo kiểu dữ liệu giá trị thì vùng nhớ của biến đó sẽ chứa giá trị của dữ liệu và được lưu trữ trong vùng nhớ Stack (VD: bool, byte, short, int, long, float, double, decimal, char, struct, ...)
+ Kiểu dữ liệu tham chiếu (reference): Một biến khi khai báo kiểu dữ liệu tham chiếu thì vùng nhớ của biến đó chỉ chứa địa chỉ của đối tượng dữ liệu và lưu trong vùng nhớ Stack. (VD: object, dynamic, string và tất cả các kiểu dữ liệu do người dùng định nghĩa)

## 8. Toán Tử Trong C#
Toán tử là một công cụ để thao tác với dữ liệu.

Một toán tử là một ký hiệu dùng để đại diện cho một thao tác cụ thể được thực hiện trên dữ liệu.

Có 6 loại toán tử cơ bản:
- Toán tử toán học: + - * / % ++ --
- Toán tử quan hệ: == != > < >= <=
- Toán tử logic: && || !
- Toán tử khởi tạo và gán: = += -= *= /= %=
- Toán tử so sánh trên bit (Khá ít gặp): & | ^ ~ << >>
- Toán tử khác
+ Toán tử "sizeof()" : Trả về kích cỡ của một kiểu dữ liệu, VD : sizeof(int) sẽ trả về 4
+ Toán tử "typeof()" : Trả về kiểu dữ liệu của một lớp, VD : typeof(string) sẽ trả về kiểu dữ liệu System.String
+ Toán tử "new" : Cấp phát vùng nhớ mới, áp dụng cho kiểu dữ liệu tham chiếu, VD : DateTime dt = new DateTime() 
+ Toán tử "is" : Xác định đối tượng có phải là một kiểu cụ thể nào đó hay không. Nếu đúng sẽ trả về true ngược lại trả về false
+ Toán tử "as" : Ép kiểu mà không gây ra lỗi. Nếu ép kiểu không thành công sẽ trả về null
+ Toán tử "?:" : Được gọi là toán tử 3 ngôi. Tương đương với cấu trúc điều kiện 

## 9. Hằng Trong C#
Khái niệm:
- Là một biến những giá trị không thay đổi trong suốt chương trình.
- Bắt buộc phải khởi tạo giá trị khi khai báo.

Trong C#, hằng được chia làm 3 loại:
- Giá trị hằng: Là biến có giá trị cố định, không thể thay đổi, được khai báo bằng từ khóa const và bắt buộc phải gán giá trị tại thời điểm khai báo
```csharp
//Cú pháp
const <kiểu_dữ_liệu> <tên_hằng> = <giá_trị>;
```

- Biểu tượng hằng: Là hằng định nghĩa ở mức tiền biên dịch (preprocessor constant), sử dụng từ khóa #define để khai báo và không có kiểu dữ liệu và không nằm trong phạm vi lớp.
```csharp
//Cú pháp
#define TÊN_HẰNG
#undef TÊN_HẰNG // hủy định nghĩa (nếu cần)
```

- Kiểu liệt kê (enum): Là tập hợp các hằng số có tên (named constants) thuộc cùng một kiểu dữ liệu, giúp dễ đọc, dễ bảo trì mã khi làm việc với nhóm giá trị cố định. Mặc định, mỗi phần tử trong enum là một hằng số nguyên (int), bắt đầu từ 0.
```csharp
//Cú pháp
enum <TênEnum> { GiáTrị1, GiáTrị2, GiáTrị3, ... }
```

## 10. Ép Kiểu Trong C#
Ép kiểu là biến đổi dữ liệu thuộc kiểu dữ liệu này thành kiểu dữ liệu khác.
- Trong C#, ép kiểu có 4 loại:
+ Chuyển đổi kiểu ngầm định (implicit)
+ Chuyển đổi kiểu tường minh (explicit)
+ Sử dụng phương thức, lớp hỗ trợ sẵn: Dùng phương thức Parse(), TryParse() hoặc lớp hỗ trợ sẵn (Convert).
+ Người dùng tự định nghĩa kiểu chuyển đổi.