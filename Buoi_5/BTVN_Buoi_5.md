# Bài tập về nhà C# buổi 5

## Mục tiêu
- Xây một trò chơi đơn giản chạy trên Console: bản đồ là grid 2D, có Player và nhiều Enemy (tùy độ khó) 
- Trò chơi chạy theo lượt: lượt Player → lượt Enemy; mỗi lượt: di chuyển (W/A/S/D), nếu có mục tiêu trong tầm thì tấn công. 
- Dùng các nguyên lý OOP: kế thừa, đóng gói, trừu tượng, đa hình

## Cấu trúc chương trình & các lớp yêu cầu (Gợi ý)
**1️ Lớp Character (lớp trừu tượng)**

Chức năng: đại diện cho mọi thực thể có thể di chuyển và chiến đấu trên bản đồ.

### Thuộc tính:
- posX, posY — vị trí của nhân vật trên grid.
- damage — lượng sát thương gây ra khi tấn công.
- rangeAttack — phạm vi tấn công.
- health — máu của nhân vật.

### Phương thức:
- public abstract void Move(char direction = ' '); → Di chuyển nhân vật theo hướng chỉ định. Nếu không truyền tham số, mặc định ' ' (bỏ lượt).
- public void TakeDamage(double damage); → Giảm máu của nhân vật tương ứng với lượng damage nhận vào.
- public virtual void Attack(Tile[,] grid); → Gây sát thương lên mục tiêu nếu nằm trong phạm vi tấn công.
- public virtual Character CheckRangeAttack(Tile[,] grid); → Kiểm tra xem có kẻ địch trong tầm đánh không, nếu có thì trả về đối tượng đó, nếu không thì null.

**2️ Lớp Enemy (kế thừa Character)**

Chức năng: đại diện cho quái vật.

### Hành vi đặc trưng:
- Di chuyển ngẫu nhiên mỗi lượt (Nâng cao: Có thể code logic di chuyển cho nó sao cho tối ưu)
- Tấn công Player nếu trong tầm.

### Phương thức:
- public override void Move(char direction = ' '); → Di chuyển ngẫu nhiên theo 4 hướng (lên/xuống/trái/phải). Nếu ô đích trống → di chuyển theo hướng.
- public override void Attack(Tile[,] grid); → Kiểm tra nếu Player trong tầm → gọi TakeDamage() lên Player.

**3️ Lớp Player (kế thừa Character)**

Chức năng: đại diện cho người chơi điều khiển.

### Thuộc tính bổ sung:
- Weapon CurrentWeapon — vũ khí hiện tại (random mỗi khi bắt đầu game).

### Phương thức:
- public override void Move(char direction = ' '); → Nhập từ bàn phím hướng di chuyển (W/A/S/D). → Nếu ô đích trống → di chuyển; nếu có Enemy trong tầm → tấn công.
- public override void Attack(Tile[,] grid); → Dựa vào CurrentWeapon.Attack và CurrentWeapon.RangeAttack để gây sát thương.
- public override Character CheckRangeAttack(Tile[,] grid); → Trả về Enemy nếu có Enemy nằm trong tầm.

**4️ Lớp Weapon**

Chức năng: chứa thông tin về vũ khí của Player.

### Thuộc tính:
- name — tên vũ khí.
- damage — sát thương.
- rangeAttack — phạm vi tấn công.

**5️ Lớp Tile (đại diện cho 1 ô trên bản đồ)**

Chức năng: mô tả từng ô trong grid.

### Thuộc tính:
- occupant — nhân vật đang đứng trên ô (để null nếu không có nhân vật nào trong ô)
- posX, posY — vị trí ô.

### Phương thức:
- public bool IsOccupied() — trả true nếu có nhân vật đứng trên ô.

**6️ Lớp GridManager (quản lý toàn bộ bản đồ)**
### Thuộc tính:
- xWide, yHigh — kích thước bản đồ.
- enemyList — danh sách Enemy.
- player — người chơi.
- grid — mảng chứa toàn bộ các ô.

### Phương thức:
- public void SpawnTile(int x, int y) — tạo mới toàn bộ grid (các Tile).
- public void UpdateGrid() — cập nhật lại vị trí của Player và Enemy lên grid sau mỗi lượt.
- public void DrawGrid() — in ra màn hình console (ký tự 0 cho Player, 1 cho Enemy, X cho ô trống).

**7️ Lớp GameManager (điều khiển toàn bộ game)**
### Thuộc tính:
- xWide, yHigh — kích thước grid.
- player - người chơi
- enemyList - danh sách enemy
- gridManager - quản lý grid
- turn — xác định lượt (0 = Player, 1 = Enemy).

### Phương thức:
- public void StartBattle() — bắt đầu trò chơi, khởi tạo Player, Enemy, và vòng lặp chính.
- public void SpawnEntity() — tạo Player và Enemy ở vị trí ngẫu nhiên.
- public void TurnPlayer() — gọi Player.Move() rồi Player.CheckRangeAttack().
- public void TurnEnemy() — duyệt qua tất cả Enemy, gọi Move() và CheckRangeAttack().
- public void CheckWinOrLose() — kiểm tra điều kiện kết thúc trận (Player chết hoặc tất cả Enemy chết).

**8️ Lớp ActiveGame (chạy chương trình chính)**
Chức năng: khởi tạo các đối tượng và bắt đầu game.

### Trong Main():
- Khởi tạo danh sách vũ khí (3–4 loại).
- Random chọn vũ khí cho Player.
- Random số lượng Enemy (tùy độ khó).
- Gọi GameManager.StartBattle() để bắt đầu.

**🧩 Luồng hoạt động tổng quát của trò chơi**
- Tạo bản đồ grid 2D.
- Sinh Player và Enemy ngẫu nhiên trong grid.
- In trạng thái hiện tại (vẽ map, máu của các nhân vật).
- Lượt Player: nhập hướng, di chuyển, tấn công nếu có thể.
- Lượt Enemy: di chuyển ngẫu nhiên, tấn công nếu trong tầm.
- Cập nhật lại grid, vẽ lại bản đồ.
- Kiểm tra thắng/thua, lặp lại đến khi kết thúc.

**💡 Ví dụ kết quả khi chạy (Console)**
```
Bắt đầu game!
Vũ khí của bạn là: Sword
Tầm đánh của bạn là: 2
Sát thương bạn gây ra: 2
Máu của Player: 10
Enemy 1: 6 HP
Enemy 2: 8 HP
-------------------------
0 X X 1 X
X X X X X
X 1 X X X
X X X X X
-------------------------
Nhập hướng (W/A/S/D): D

Bạn di chuyển sang phải.
Bạn tấn công Enemy 1, gây 2 sát thương!
Enemy 1 còn 4 HP.
-------------------------
Tiếp tục trò chơi
Vũ khí của bạn là: Sword
Tầm đánh của bạn là: 2
Sát thương bạn gây ra: 2
Máu của Player: 10
Enemy 1: 6 HP
Enemy 2: 8 HP
-------------------------
0 X X 1 X
X X X X X
X 1 X X X
X X X X X
-------------------------
Nhập hướng (W/A/S/D): 
```

**Lưu ý:**
- Mọi thuộc tính cần để phạm vi truy cập là private và truy cập thông qua property (getter/setter)
- Mọi người có thể hoàn thành bài tập theo ý mình, không cần phải giống hoàn toàn yêu cầu đề (tức có thể thêm, bớt thuộc tính/phương thức/lớp hoặc sử dụng logic của mình để hoàn thành thay vì những lớp/thuộc tính/phương thức đề cho)