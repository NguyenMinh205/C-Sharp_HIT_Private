# Lý thuyết C# buổi 2 (Các cáu trúc trong C#)

## 11. Cấu Trúc Lệnh Rẽ Nhánh if else Trong C#
Cấu trúc rẽ nhánh: là một phương pháp để chương trình đưa ra quyết định, thực hiện các hành động khác nhau tùy vào điều kiện kiểm tra. Nó được dùng để kiểm tra và thực hiện các hành động trong các trường hợp khác nhau.

### Các loại cấu trúc rẽ nhánh trong C#:
- if-else: Cấu trúc điều kiện phổ biến, giúp thực hiện hành động dựa trên một điều kiện.
- switch-case: Một cách khác để thực hiện các quyết định, thường dùng khi có nhiều giá trị để so sánh.

### Cấu trúc if else dạng thiếu (if đơn giản):
- Cú pháp:
```csharp
if ([Biểu thức điều kiện])
    <Câu lệnh thực hiện>;
```

Ý nghĩa: Nếu biểu thức điều kiện trả về true, thực hiện câu lệnh sau if, ngược lại không làm gì.

### Cấu trúc if else dạng đủ (if-else):
- Cú pháp:
```csharp
if ([Biểu thức điều kiện])
    <Câu lệnh thực hiện 1>;
else
    <Câu lệnh thực hiện 2>;
```

Ý nghĩa: Nếu điều kiện đúng (true), thực hiện Câu lệnh thực hiện 1. Nếu sai (false), thực hiện Câu lệnh thực hiện 2.

### Các lưu ý khi sử dụng if-else:
Biểu thức điều kiện phải trả về giá trị boolean (true hoặc false).

Nên sử dụng dấu {} để nhóm nhiều câu lệnh lại với nhau, giúp code rõ ràng và dễ bảo trì.

Có thể có các câu lệnh điều kiện lồng nhau (nested if-else).

Khi sử dụng nhiều câu lệnh điều kiện, có thể dùng if-else if-else để xử lý nhiều trường hợp.

### Sự khác biệt giữa if-else và toán tử 3 ngôi:

Cấu trúc if-else giúp thực hiện nhiều câu lệnh hơn và dễ đọc hơn.

Toán tử 3 ngôi (?:) có thể sử dụng cho các trường hợp đơn giản, giúp code ngắn gọn hơn.

## 12. Cấu Trúc switch case Trong C#
Cấu trúc switch-case trong C# được sử dụng để so sánh một biểu thức với nhiều giá trị khả dĩ khác nhau. Khi một giá trị trùng khớp với một trong các case, chương trình sẽ thực thi câu lệnh tương ứng. Nếu không có giá trị nào trùng khớp, cấu trúc switch-case có thể sử dụng default để xử lý trường hợp mặc định.

### Cấu trúc switch-case dạng thiếu:
Cú pháp:
```csharp
switch (<biểu thức>)
{
    case <giá trị thứ 1>:
        <câu lệnh thứ 1>;
        break;
    case <giá trị thứ 2>:
        <câu lệnh thứ 2>;
        break;
    ...
    case <giá trị thứ n>:
        <câu lệnh thứ n>;
        break;
}
```

### Cấu trúc switch-case dạng đủ:
Cú pháp:
```csharp
switch (<biểu thức>)
{
    case <giá trị thứ 1>:
        <câu lệnh thứ 1>;
        break;
    case <giá trị thứ 2>:
        <câu lệnh thứ 2>;
        break;
    ...
    case <giá trị thứ n>:
        <câu lệnh thứ n>;
        break;
    default:
        <câu lệnh mặc định>;
        break;
}
```
### Sự khác biệt giữa cấu trúc switch-case dạng thiếu và dạng đủ:
Dạng thiếu không có default, sẽ chỉ thực hiện hành động nếu giá trị của biểu thức khớp với một trong các case.

Dạng đủ có thêm default, được sử dụng khi không có case nào khớp với giá trị của biểu thức. Đây là một cách dự phòng, đảm bảo rằng luôn có một hành động được thực thi.

### Những điểm cần lưu ý khi sử dụng switch-case:
Lệnh break là bắt buộc trong mỗi case để kết thúc việc kiểm tra và thoát khỏi cấu trúc switch.

Kiểu dữ liệu của biểu thức và các giá trị trong case phải khớp nhau (ví dụ: nếu biểu thức là kiểu số nguyên (int), thì các giá trị case cũng phải là kiểu số nguyên).

default là một phần tùy chọn trong cấu trúc switch, nhưng rất hữu ích để xử lý các trường hợp không mong đợi.

Bạn có thể có nhiều case mà không có câu lệnh thực thi, ví dụ như khi muốn các giá trị tương tự xử lý cùng một hành động. Điều này gọi là fall-through, trong đó chương trình tiếp tục kiểm tra các case sau mà không cần break cho đến khi gặp một case có câu lệnh thực thi.

## 13. Vòng Lặp Trong C#
Một vòng lặp là một chuỗi các sự kiện, hành động lặp lại đến khi thỏa mãn điều kiện dừng nào đó. Hay nói cách khác, vòng lặp là chuỗi các sự kiện, hành động lặp đi lặp lại khi thỏa mãn điều kiện nào đó. Vòng lặp sẽ kết thúc khi không còn thỏa mãn điều kiện lặp nữa.

Vòng lặp vô tận là một chuỗi các sự kiện, hành động lặp lại vô tận do không bao giờ thỏa mãn điều kiện dừng.

### Các loại vòng lặp:
- for: Lặp với số lần xác định.
- while: Lặp khi điều kiện là true.
- do-while: Lặp ít nhất một lần và sau đó kiểm tra điều kiện.
- foreach: Duyệt qua các phần tử trong tập hợp.
- goto: Nhảy đến nhãn khác (hiếm khi sử dụng).

### Vòng lặp for
Cấu trúc của một vòng lặp for trong C#
- Cú pháp:
```csharp
for ([Khởi tạo]; [Điều kiện lặp]; [Bước lặp lại])
{
    // Khối lệnh được lặp lại. Có thể bỏ trống
}
```

- Khởi tạo: Được thực hiện 1 lần trước khi vòng lặp bắt đầu.
- Điều kiện lặp: Kiểm tra mỗi lần trước khi vào vòng lặp.
- Bước lặp: Được thực hiện sau mỗi vòng lặp (thường là tăng biến đếm).

Điều kiện lặp
- Điều kiện lặp là một biểu thức logic với kết quả trả về bắt buộc là true hoặc false (có thể bỏ trống sẽ trả về kết quả là true).
- Điều kiện lặp là dòng lệnh thứ 2 vòng for sẽ chạy vào khi chạy lần đầu tiên (Khởi tạo chạy trước). Từ lần lặp thứ 2 của vòng for, Điều kiện lặp cũng là dòng lệnh thứ 2 được chạy sau bước lặp lại. 
- Khi câu điều kiện lặp không còn thỏa mãn (kết quả là false) thì vòng lặp for sẽ kết thúc.
 
### Vòng lặp while
Cấu trúc của một vòng lặp while trong C#
- Cú pháp:
```csharp
while (điều_kiện_lặp)
{
    // Khối lệnh
}
```
- Điều kiện lặp là một biểu thức logic bắt buộc phải có với kết quả trả về bắt buộc là true hoặc false.
- Từ khóa while biểu thị đây là một vòng lặp while. Các câu lệnh trong khối lệnh sẽ được lặp lại đến khi không còn thỏa mãn điều kiện lặp sẽ kết thúc vòng lặp while.

### Vòng lặp do while
Cấu trúc của một vòng lặp do while trong C#
- Cú pháp:
```csharp
do
{
    // Khối lệnh
} while (điều_kiện_lặp);
```
Lưu ý: vòng lặp do while sẽ thực hiện câu lệnh trong khối code xong rồi mới kiểm tra điều kiện lặp. Cuối vòng lặp do while có dấu ; ở cuối.

## 14. Mảng trong C#

### Khái niệm:
- Mảng (Array) là một tập hợp các phần tử cùng kiểu dữ liệu, được lưu trữ liên tiếp nhau trong bộ nhớ.
- Mỗi phần tử trong mảng được xác định bằng chỉ số (index), bắt đầu từ 0.
- Mảng giúp lưu trữ và quản lý nhiều dữ liệu cùng loại một cách thuận tiện

### Mảng một chiều
Khai báo mảng:
```csharp
<kiểu dữ liệu>[] <tên mảng>;
```
Trong đó:
- <kiểu dữ liệu> là kiểu dữ liệu của các phần tử trong mảng.
- Cặp dấu [] là ký hiệu cho khai báo mảng 1 chiều.
- <tên mảng> là tên của mảng, cách đặt tên mảng cũng như cách đặt tên biến 

Cấp phát vùng nhớ:
```csharp
<kiểu dữ liệu>[] <tên mảng> = new <kiểu dữ liệu>[số phần tử];
```

Khởi tạo bộ nhớ
```csharp
int[] arr = new int[3] {10, 20, 30};
// hoặc
int[] arr = {10, 20, 30};
```

Truy xuất phần tử:
```csharp
Sao chép mã
Console.WriteLine(arr[1]); // In ra 20
arr[2] = 50; // Gán lại giá trị phần tử thứ 3
```

Duyệt mảng:
```csharp
for (int i = 0; i < arr.Length; i++)
    Console.WriteLine(arr[i]);
```

### Mảng hai chiều
Mảng 2 chiều được hình dung như ma trận gồm hàng và cột (MxN).

Cú pháp:
```csharp
<kiểu dữ liệu>[,] <tên mảng> = new <kiểu dữ liệu>[số_hàng, số_cột];
```
Trong đó :
- <kiểu dữ liệu> là kiểu dữ liệu của các phần tử trong mảng.
- Cặp dấu [ , ] là ký hiệu cho khai báo mảng 2 chiều.
- <tên mảng> là tên của mảng, cách đặt tên mảng cũng như cách đặt tên biến (quy tắc đặt tên biến đã trình bày trong BIẾN TRONG C#).
- Để sử dụng được mảng ta phải khởi tạo giá trị hoặc cấp phát vùng nhớ cho mảng.

Khởi tạo giá trị
```csharp
<kiểu dữ liệu>[,] <tên mảng> =
{
   { <giá trị dòng 1 cột 1>, …, <giá trị dòng 1 cột n> },
            …
   { <giá trị dòng m cột 1>, …, <giá trị dòng m cột n> }
};
```

Duyệt mảng 2 chiều:
```csharp
for (int i = 0; i < matrix.GetLength(0); i++)
{
    for (int j = 0; j < matrix.GetLength(1); j++)
    {
        Console.Write(matrix[i, j] + "\t");
    }
    Console.WriteLine();
}
```
## 15. Chuỗi (string) trong C#

### Khái niệm: 
- string là kiểu dữ liệu tham chiếu dùng để lưu chuỗi ký tự.
- Mỗi chuỗi là một đối tượng bất biến (immutable): khi thay đổi giá trị, C# tạo chuỗi mới, không sửa chuỗi cũ.

### Một số phương thức thông dụng
- Length : Trả về 1 số nguyên kiểu int là độ dài của chuỗi
- String.Compare(string a, string b); : So sánh 2 chuỗi a và b có bằng nhau hay không. Nếu bằng nhau thì trả về 0, nếu a > b thì trả về 1, a < b thì trả về -1
- String.Concat(string a, string b); : Nối 2 chuỗi a và b thành 1 chuỗi, tương tự như phép cộng chuỗi bằng toán tử '+'
- IndexOf(char c); : Trả về 1 số nguyên kiểu int là vị trí xuất hiện đầu tiên của ký tự c có trong chuỗi. Nếu như không tìm thấy thì phương thức này sẽ trả về -1
- Insert(int StartIndex, string s); : Trả về 1 chuỗi mới trong đó bao gồm chuỗi cũ đã chèn thêm chuỗi s bắt đầu từ vị trí StartIndex
- String.IsNullOrEmpty(string s); : Kiểm tra chuỗi s có phải là chuỗi null hoặc chuỗi rỗng không, nếu đúng thì trả về true, sai thì trả về false
- LastIndexOf(char c); : Trả về 1 số nguyên kiểu int là vị trí xuất hiện cuối cùng của ký tự c có trong chuỗi. Nếu như không tìm thấy thì phương thức này sẽ trả về -1
- Remove(int StartIndex, int count); : Trả về 1 chuỗi mới sau khi đã xoá đi count ký tự bắt đầu từ vị trí StartIndex
- Replace(char oldc, char newc); : Trả về 1 chuỗi mới sau khi đã thay thế tất cả các ký tự oldc bằng các ký tự newc
- Split(char c); : Trả về 1 mảng các chuỗi được cắt ra từ chuỗi ban đầu tại những nơi có ký tự c. Ta có thể truyền vào nhiều ký tự khác nhau, khi đó phương thức sẽ thực hiện cắt theo từng ký tự đã truyền vào 
- Substring(int StartIndex, int length); : Trả về 1 chuỗi mới được cắt từ chuỗi ban đầu từ vị trí StartIndex với số ký tự cắt là length. Nếu ta gọi Substring mà chỉ truyền vào StartIndex thì máy tính sẽ cắt từ vị trí StartIndex đến cuối chuỗi

### Lớp StringBuilder trong C#
Đặc điểm :Lớp StringBuilder được .NET xây dựng sẵn giúp chúng ta thao tác trực tiếp với chuỗi gốc và giúp tiết kiệm bộ nhớ hơn so với lớp String.

Đặc điểm của StringBuilder là:
- Cho phép thao tác trực tiếp trên chuỗi ban đầu.
- Có khả năng tự mở rộng vùng nhớ khi cần thiết.
- Không cho phép lớp khác kế thừa.
- Từ 2 đặc điểm này đã làm nổi bật lên ưu điểm của StringBuilder so với String đó là ít tốn bộ nhớ. Cụ thể qua ví dụ sau:           

Cú pháp khởi tạo
```csharp
StringBuilder sb = new StringBuilder();              // Rỗng
StringBuilder sb2 = new StringBuilder("Hello");      // Có giá trị ban đầu
```

Trong lớp StringBuilder có các phương thức như: Remove, Insert, Replace được sử dụng hoàn toàn giống như lớp String. Chỉ có vài phương thức mới các bạn cần chú ý :
- Append(string s); : Nối chuỗi s vào chuỗi ban đầu
- Clear(); : Xoá toàn bộ nội dung trong đối tượng (không xoá vùng nhớ của đối tượng)
- ToString() : Chuyển đối đối tượng kiểu StringBuilder sang kiểu String

## 16. Hàm trong C#

### Khái niệm & cú pháp
Hàm (method) là khối lệnh có tên, thực hiện một nhiệm vụ, có thể nhận tham số và có/không trả về giá trị.

- Cú pháp khai báo hàm:          
```csharp
[Từ khóa 1] [Từ khóa 2]...[Từ khóa n]  <Kiểu dữ liệu trả về> <Tên hàm>([Parameter]){ }
```
Trong đó:
- [Từ khóa 1], [Từ khóa 2],..., [Từ khóa n] là các từ khóa như: public, static, read only … và có thể không điền.
- Kiểu dữ liệu trả về như: từ khóa void, hay mọi kiểu dữ liệu như int, long, bool, SinhVien…

Tên hàm:
- Là tên gọi của hàm.
- Tên bạn có thể đặt tùy ý nhưng nên đặt tên theo quy tắc đặt tên để có sự đồng bộ ngầm định giữa các lập trình viên và dễ tìm, dễ nhớ.
- Hãy xem cách khởi tạo hàm giống khởi tạo một biến ở chỗ : Đều cần kiểu dữ liệu và tên. Có thể có các từ khóa. Tên để tái sử dụng hàm ở nơi mong muốn.
- Parameter là tham số truyền vào để sử dụng nội bộ trong hàm. Cấu trúc khởi tạo như một biến bình thường. Có thể không điền.
- Hàm chỉ được khai báo bên trong class.

Hàm Main (điểm vào chương trình)
static void Main(string[] args) { }


static: bắt buộc với Main của ứng dụng Console.

void: không trả về giá trị (cũng có thể là int trong vài cấu hình).

string[] args: đối số dòng lệnh (có thể không dùng, nhưng dạng chuẩn thường có).

### Hàm void (hàm không trả về)
Không cần (và không có) giá trị sau return:
```csharp
static void Demo()
{
    Console.WriteLine("Called from Demo! Pi");
    // return; // có thể viết hoặc bỏ
}
```

Gọi hàm: dùng tên + (). Có thể gọi nhiều lần để tái sử dụng.

### Hàm có kiểu trả về (non-void)
Phải có return <giá trị> phù hợp kiểu trả về:
```csharp
static int ReturnANumber()
{
    return 5;
}
```

Có thể dùng giá trị trả về trực tiếp:
```csharp
Console.WriteLine(ReturnANumber()); // in 5
```

Có thể gọi hàm trong hàm (chaining/composition).

### Tham số (parameters)
Dùng để nhận dữ liệu đầu vào cho hàm; là biến cục bộ của hàm.

Khai báo nhiều tham số: cách nhau bằng dấu ,.

Khi gọi, phải đúng số lượng, đúng thứ tự, đúng kiểu.
```csharp
static int SumTwoNumber(int firstNumber, int secondNumber)
{
    return firstNumber + secondNumber;
}

// gọi:
Console.WriteLine(SumTwoNumber(5, 10)); // 15
```

Truyền tham trị (mặc định): hàm làm việc với bản sao giá trị; giá trị biến gốc không đổi sau khi hàm kết thúc.

### static và gọi hàm trong Console app
Vì Main là static, các hàm bạn muốn gọi từ Main cũng nên là static (trừ khi bạn tạo đối tượng để gọi instance method).