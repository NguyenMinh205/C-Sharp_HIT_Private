# Hướng Dẫn Sử Dụng Git - Các Lệnh Cơ Bản Của Git

## 1. Git là gì? 
Git là hệ thống quản lý phiên bản (VCS - Version Control System) giúp kiểm soát các thay đổi, phiên bản của dự án, bao gồm ai thực hiện thay đổi, khi nào và tại sao. Git cũng cho phép khôi phục lại các phiên bản trước của dự án.

### Nguyên tắc làm việc của Git:
- Có một kho lưu trữ trung tâm (repository).
- Lấy dữ liệu về, thực hiện công việc, và cập nhật lên kho trung tâm.
- Công cụ để giải quyết các xung đột (conflict).

### Lợi ích của Git:
- Đảm bảo không làm hỏng phiên bản hiện tại (chúng ta có thể quay lại các phiên bản trước đó của project)
- Giúp làm việc cộng tác với nhiều người
- Cho phép ta can thiệt và phát triển phiên bản mới mà không ảnh hưởng đến phiên bản cũ
- Khôi phục lại phiên bản trước bất kỳ lúc nào.
- Chia sẻ với người khác

Git ≠ GitHub: GitHub chỉ là kho lưu trữ trực tuyến, hỗ trợ các công nghệ của Git.

### Cài đặt Git:
Truy cập [Git-SCM.com](https://git-scm.com) để tải về và cài đặt.

Video hướng dẫn cài đặt: (https://youtu.be/4FjgUp0zgcM?si=FRA_Po2osgXEdEYv)

## 2. Các câu lệnh cơ bản của Git

### Các câu lệnh terminal cơ bản:
- `cd <thư_mục>`: Thay đổi thư mục làm việc.
- `cd ..`: Quay lại thư mục cha.
- `dir (ls với mac)`: hiện thị tất cả các danh sách tập tin bên trong thư mục hiện thành
- `mkdir <thư_mục>`: Tạo thư mục mới.
- `touch <tên_file>`: Tạo một tệp tin mới.
- `echo “noidung” ( > “noicanxuatvao”)` : in/xuất một nội dung
- `cat` : hiện thị nội dung
- `diff filename1 filename2`: so sánh xem file1 và file2 khác nhau chỗ nào
- `rm <tên_file>`: Xóa file hoặc folder rỗng.
- `rm -rf <tên_file>`: Xóa tất cả các file trong thư mục.

### Các câu lệnh Git cơ bản:
- `git --help`: Hiện trợ giúp.
- `git --version`: Hiển thị phiên bản Git hiện tại.
- `git status`: Hiển thị trạng thái của kho lưu trữ.
- `git log`: Hiển thị lịch sử các commit.
- `git init [tên_repo]`: Tạo một kho lưu trữ Git mới.
- `git clone [repo] [tên_clone]`: Tạo một bản sao của repo.
- `git add <tệp>`: Thêm tệp vào index.
- `git add .`: Thêm tất cả các tệp.
- `git commit -m "<tin nhắn>"`: Tạo commit.
- `git push`: Đẩy commit lên remote repository.
- `git pull`: Lấy dữ liệu từ remote repository về local.
- `git fetch`: tải (cập nhật) thông tin và commit mới từ remote nhưng KHÔNG tự động gộp vào nhánh đang làm việc.

## 3. Xử lý lỗi conflict trong Git
Lỗi conflict (xung đột) trong Git xảy ra khi hai hoặc nhiều thay đổi mâu thuẫn với nhau, và Git không thể tự động hợp nhất (merge) chúng. 
Điều này thường xảy ra khi bạn cố gắng merge hoặc pull các thay đổi từ một nhánh hoặc remote repository vào nhánh hiện tại, và có sự khác biệt giữa các tệp mà cả hai bên đã sửa đổi.

### Cách khắc phục:
Bạn cần mở file bị xung đột, xem xét sự khác biệt, và chọn giữ lại hoặc xóa phần nào theo nhu cầu. Sau đó commit lại kết quả đã sửa.

## 4. Làm việc với nhánh (Branch)
- `git branch <tên_nhánh>`: Tạo nhánh mới.
- `git checkout <tên_nhánh>`: Chuyển sang nhánh khác.
- `git branch -l`: Xem danh sách các nhánh.
- `git push -u origin <tên_nhánh>`: Tạo nhánh mới trên remote repository.
- `git merge <tên_nhánh>`: Kết hợp nhánh hiện tại với nhánh khác.

## 5. Kết nối với GitHub
1. Đẩy dự án lên GitHub:
   ```bash
   B1: Tạo một repository mới trên GitHub
   B2: Mở dự án cần push lên GitHub ở trong Git Bash
   B3: git remote add origin <link_repo_trên_github>
   B4: Cấu hình git
   B5: Chuyển sang nhánh chính git branch -M main
   B6: đẩy commit lên GitHub: git push -u origin main
2. Clone dự án về
   ```bash
   B1: Sao chép đường link của repository trên GitHub
   B2: Mở Git Bash và chạy lệnh: git clone <link_repo_trên_github>
### Lưu ý khi clone dự án của người khác
Quyền hạn: Khi clone một dự án công khai (public repository), bạn có thể đọc và xem mã nguồn, nhưng bạn không thể push các thay đổi trực tiếp lên repository của người khác. 
Nếu bạn muốn đóng góp vào dự án, bạn cần tạo một fork và sau đó pull request để yêu cầu người chủ dự án xem xét và hợp nhất các thay đổi của bạn.

Forking: Nếu bạn muốn thực hiện các thay đổi trên một dự án của người khác và gửi lại cho họ, bạn cần thực hiện một thao tác gọi là Fork. Forking tạo ra một bản sao repository vào tài khoản GitHub của bạn.

### Cách fork repository:
```bash
B1: Truy cập vào repository mà bạn muốn fork.
B2: Nhấn vào nút Fork (góc trên bên phải).
B3: Sau khi fork xong, bạn có thể clone repository từ tài khoản của mình và thực hiện thay đổi.
B4: Pull request: Sau khi thực hiện thay đổi trên bản fork, bạn có thể gửi một pull request để yêu cầu người chủ repository hợp nhất (merge) các thay đổi của bạn vào dự án chính.
```

## 6. TÀI LIỆU HƯỚNG DẪN CHI TIẾT (Xem thêm):
https://youtube.com/playlist?list=PLyxSzL3F7485Xgn7novgNxnou8QU6i485&si=fn7EFYOpzgb8D9f9
