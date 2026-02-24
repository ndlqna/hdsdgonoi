# Mô Tả Chức Năng và Quyền Hạn

## 🔑 Vai Trò trong Hệ Thống

Hệ thống có 2 vai trò chính:
- 👤 **USER (Người dùng):** Nhân viên thông thường
- 👑 **ADMIN (Quản trị viên):** Người quản lý hệ thống

---

## 📋 Bảng So Sánh Quyền Hạn

| Chức năng | USER | ADMIN | Mô tả |
|-----------|:----:|:-----:|-------|
| **TRANG CHỦ** |
| Xem dashboard cá nhân | ✅ | ✅ | Xem thống kê lịch của bản thân |
| Xem tổng số người dùng | ❌ | ✅ | Xem số lượng người dùng trong hệ thống |
| Xem hoạt động gần đây | ✅ | ✅ | USER: Lịch của mình / ADMIN: Tất cả hoạt động |
| **LỊCH LÀM VIỆC** |
| Xem lịch của mình | ✅ | ✅ | Xem lịch được gán hoặc tự tạo |
| Xem lịch của người khác | ✅ | ✅ | Admin xem được lịch của tất cả mọi người |
| Tạo lịch mới | ✅ | ✅ | Tạo lịch làm việc/cuộc họp |
| Sửa lịch của mình | ✅ | ✅ | Chỉ sửa được lịch do mình tạo |
| Sửa lịch của người khác | ❌ | ✅ | Admin sửa được mọi lịch |
| Xóa lịch của mình | ✅ | ✅ | Chỉ xóa được lịch do mình tạo |
| Xóa lịch của người khác | ❌ | ✅ | Admin xóa được mọi lịch |
| Thêm người tham gia | ✅ | ✅ | Mời đồng nghiệp tham gia lịch |
| Thiết lập nhắc nhở | ✅ | ✅ | Đặt thời gian nhận thông báo nhắc |
| **THÔNG BÁO** |
| Đăng ký thiết bị | ✅ | ✅ | Đăng ký nhận thông báo trên thiết bị |
| Xóa thiết bị của mình | ✅ | ✅ | Xóa thiết bị không dùng nữa |
| Xem thiết bị của người khác | ❌ | ✅ | Admin xem danh sách thiết bị của mọi người |
| Gửi thông báo tùy chỉnh | ❌ | ✅ | Gửi thông báo quan trọng cho người dùng |
| Nhận thông báo hệ thống | ✅ | ✅ | Nhận thông báo từ Admin |
| Nhận thông báo lịch | ✅ | ✅ | Nhận nhắc nhở về lịch sắp tới |
| **NGƯỜI DÙNG** |
| Xem danh sách người dùng | ❌ | ✅ | Xem tất cả người dùng trong hệ thống |
| Tạo người dùng mới | ❌ | ✅ | Thêm nhân viên mới vào hệ thống |
| Sửa thông tin người dùng | ❌ | ✅ | Cập nhật thông tin người khác |
| Khóa/Mở khóa tài khoản | ❌ | ✅ | Vô hiệu hóa tài khoản vi phạm |
| Reset mật khẩu người khác | ❌ | ✅ | Đặt lại mật khẩu cho người dùng |
| **PHÒNG BAN** |
| Xem phòng ban của mình | ✅ | ✅ | Xem phòng ban mình thuộc về |
| Xem tất cả phòng ban | ✅ | ✅ | Xem danh sách phòng ban |
| Tạo phòng ban mới | ❌ | ✅ | Thêm phòng ban mới |
| Sửa/Xóa phòng ban | ❌ | ✅ | Quản lý phòng ban |
| Quản lý thành viên phòng ban | ❌ | ✅ | Thêm/Xóa thành viên khỏi phòng ban |
| **HỒ SƠ CÁ NHÂN** |
| Xem thông tin cá nhân | ✅ | ✅ | Xem thông tin mình |
| Sửa thông tin cá nhân | ✅ | ✅ | Cập nhật tên, email (chờ duyệt) |
| Đổi mật khẩu của mình | ✅ | ✅ | Đổi mật khẩu đăng nhập |
| **ADMIN PIN** |
| Thiết lập Admin PIN | ❌ | ✅ | Tạo mã PIN bảo mật |
| Đổi Admin PIN | ❌ | ✅ | Thay đổi PIN cũ |
| Mở khóa PIN bằng OTP | ❌ | ✅ | Mở khóa khi nhập sai quá nhiều |
| **NHẬT KÝ HỆ THỐNG** |
| Xem nhật ký hệ thống | ❌ | ✅ | Xem lịch sử thao tác trong hệ thống |
| Lọc nhật ký | ❌ | ✅ | Lọc theo người, thời gian, hành động |
| Xuất báo cáo nhật ký | ❌ | ✅ | Tải xuống file Excel |

---

## 📚 Mô Tả Chi Tiết Chức Năng

### 1. 📊 Trang Chủ (Dashboard)

**Mục đích:** Cung cấp cái nhìn tổng quan về công việc và lịch sắp tới

**Chức năng:**
- Hiển thị số lượng lịch trong tuần, số cuộc họp hôm nay
- Danh sách lịch sắp diễn ra (trong 7 ngày tới)
- Hoạt động gần đây (10 hoạt động mới nhất)
- Admin thêm được xem số lượng người dùng trong hệ thống

**Đối tượng sử dụng:** USER & ADMIN

---

### 2. 📅 Quản Lý Lịch Làm Việc

**Mục đích:** Lập kế hoạch, theo dõi và quản lý lịch làm việc

**Chức năng:**

#### 📌 Xem lịch
- **Lịch tuần:** Xem theo dạng bảng 7 ngày từ Thứ 2 đến Chủ nhật
- **Danh sách:** Xem dạng bảng chi tiết với tìm kiếm, lọc
- Di chuyển qua lại giữa các tuần
- Lọc theo loại lịch: Công việc cá nhân, Cuộc họp, Sự kiện

#### ➕ Tạo lịch mới
- Điền tiêu đề, ngày giờ, địa điểm, mô tả
- Chọn loại lịch (Công việc/Cuộc họp/Sự kiện)
- Thêm người tham gia (đồng nghiệp)
- Thiết lập nhắc nhở (5 phút, 15 phút, 30 phút, 1 giờ, 1 ngày trước)
- Lưu và gửi thông báo cho người tham gia

#### ✏️ Sửa/Xóa lịch
- USER: Chỉ sửa/xóa lịch do mình tạo
- ADMIN: Sửa/xóa mọi lịch trong hệ thống

#### 👀 Xem lịch người khác (Admin)
- Admin bật chế độ "Xem tất cả" để thấy lịch của mọi người
- Hỗ trợ điều phối công việc nhóm

**Đối tượng sử dụng:** USER & ADMIN

---

### 3. 📱 Quản Lý Thông Báo

**Mục đích:** Nhận thông báo nhắc nhở và thông tin quan trọng

**Chức năng:**

#### 🔔 Đăng ký thiết bị
- Đăng ký máy tính, điện thoại để nhận thông báo
- Đặt tên cho thiết bị (ví dụ: "Máy tính văn phòng")
- Cho phép trình duyệt gửi thông báo
- Có thể đăng ký nhiều thiết bị

#### 📋 Quản lý thiết bị
- Xem danh sách thiết bị đã đăng ký
- Xem trạng thái hoạt động
- Xóa thiết bị không dùng nữa

#### 📢 Gửi thông báo (Admin)
- Soạn tiêu đề và nội dung
- Chọn người nhận (có thể chọn nhiều)
- Đặt độ ưu tiên: Thấp/Trung bình/Cao
- Gửi ngay hoặc hẹn giờ

#### 📨 Nhận thông báo
- Thông báo nhắc lịch (trước 5 phút, 15 phút, 30 phút, 1 giờ, 1 ngày)
- Thông báo từ Admin (thông tin quan trọng)
- Thông báo được gán vào lịch mới

**Đối tượng sử dụng:** USER & ADMIN

---

### 4. 👥 Quản Lý Người Dùng (Admin)

**Mục đích:** Quản lý tài khoản và thông tin nhân viên

**Chức năng:**

#### 📄 Danh sách người dùng
- Xem tất cả người dùng: Họ tên, Email, Vai trò, Phòng ban, Trạng thái
- Tìm kiếm theo tên, email
- Lọc theo vai trò (USER/ADMIN), phòng ban, trạng thái
- Thống kê số lượng: Tổng cộng, Đang hoạt động, Bị khóa, Admin

#### ➕ Tạo người dùng mới
- Nhập họ tên, email, mật khẩu
- Chọn vai trò: USER hoặc ADMIN
- Gán phòng ban (tùy chọn)
- Đặt trạng thái: Hoạt động/Vô hiệu hóa

#### ✏️ Sửa người dùng
- Cập nhật họ tên, email
- Thay đổi vai trò
- Thay đổi phòng ban

#### 🔒 Khóa/Mở khóa tài khoản
- Vô hiệu hóa tài khoản vi phạm
- Không cho đăng nhập
- Có thể mở lại bất kỳ lúc nào
- Lưu ý: Admin không thể khóa chính mình

#### 🔑 Reset mật khẩu
- Đặt lại mật khẩu cho người dùng quên
- Yêu cầu nhập Admin PIN để xác thực
- Đặt mật khẩu tạm, người dùng nên đổi ngay

**Đối tượng sử dụng:** Chỉ ADMIN

---

### 5. 🏢 Quản Lý Phòng Ban (Admin)

**Mục đích:** Phân nhóm người dùng theo bộ phận

**Chức năng:**

#### 📋 Danh sách phòng ban
- Xem tất cả phòng ban
- Hiển thị tên, màu sắc, số thành viên, trạng thái
- Tìm kiếm phòng ban

#### ➕ Tạo phòng ban mới
- Đặt tên phòng ban
- Chọn màu sắc đại diện (để dễ phân biệt)
- Thêm mô tả (tùy chọn)
- Đặt trạng thái: Hoạt động/Không hoạt động

#### ✏️ Sửa phòng ban
- Đổi tên, màu sắc, mô tả
- Thay đổi trạng thái

#### 👥 Quản lý thành viên
- Xem danh sách thành viên hiện tại
- Thêm người dùng vào phòng ban
- Xóa người dùng khỏi phòng ban
- Một người có thể thuộc nhiều phòng ban

#### 🗑️ Xóa phòng ban
- Xóa phòng ban không dùng nữa
- Không xóa thành viên, chỉ bỏ liên kết

**Đối tượng sử dụng:** Chỉ ADMIN

---

### 6. 👤 Hồ Sơ Cá Nhân

**Mục đích:** Quản lý thông tin và bảo mật tài khoản cá nhân

**Chức năng:**

#### 📇 Thông tin cá nhân
- Xem họ tên, email, vai trò
- Xem phòng ban đang tham gia
- Xem ngày tạo tài khoản

#### ✏️ Cập nhật thông tin
- Đổi họ tên
- Đổi email (cần xác thực)

#### 🔐 Đổi mật khẩu
- Nhập mật khẩu hiện tại
- Nhập mật khẩu mới và xác nhận
- Yêu cầu: Tối thiểu 8 ký tự, có chữ hoa, chữ thường, số, ký tự đặc biệt

#### 📊 Quyền hạn
- Xem mô tả quyền hạn theo vai trò của mình

**Đối tượng sử dụng:** USER & ADMIN

---

### 7. 🔐 Quản Lý Admin PIN (Admin)

**Mục đích:** Bảo mật quy trình reset mật khẩu người dùng

**Chức năng:**

#### 🔑 Thiết lập PIN
- Tạo mã PIN 6 chữ số lần đầu
- Xác nhận PIN
- Lưu vào hệ thống (được mã hóa)

#### 🔄 Đổi PIN
- Nhập PIN hiện tại
- Nhập PIN mới và xác nhận
- Cập nhật PIN

#### 🔓 Mở khóa PIN bằng OTP
- Khi nhập sai PIN 5 lần, bị khóa tạm thời
- Yêu cầu mở khóa bằng OTP
- Hệ thống gửi mã OTP qua email
- Nhập OTP để mở khóa

#### ℹ️ Xem trạng thái PIN
- Đã thiết lập hay chưa
- Đang hoạt động hay bị khóa
- Số lần nhập sai còn lại

**Đối tượng sử dụng:** Chỉ ADMIN

---

### 8. 📝 Nhật Ký Hệ Thống (Admin)

**Mục đích:** Giám sát và theo dõi các thao tác trong hệ thống

**Chức năng:**

#### 📊 Xem nhật ký
- Bảng danh sách tất cả hoạt động
- Thông tin: Thời gian, Người thực hiện, Hành động, Đối tượng, Chi tiết thay đổi
- Phân trang để xem nhiều bản ghi

#### 🔍 Lọc nhật ký
- **Theo thời gian:** Chọn từ ngày - đến ngày
- **Theo người thực hiện:** Chọn người dùng cụ thể
- **Theo hành động:** Tạo mới (CREATE), Cập nhật (UPDATE), Xóa (DELETE)
- **Theo đối tượng:** Người dùng, Lịch, Phòng ban, Thông báo

#### 📈 Thống kê nhật ký
- Tổng số bản ghi
- Số bản ghi hôm nay
- Phân tích theo hành động (Tạo/Sửa/Xóa bao nhiêu)
- Phân tích theo đối tượng (User/Schedule/Department...)

#### 💾 Xuất nhật ký
- Xuất dữ liệu ra file Excel
- Tiện lưu trữ và báo cáo

#### 🔍 Xem chi tiết thay đổi
- Click vào bản ghi để xem chi tiết
- Xem giá trị cũ và giá trị mới
- Hiểu rõ thay đổi gì đã xảy ra

**Đối tượng sử dụng:** Chỉ ADMIN

---

## 🎯 Kịch Bản Sử Dụng Thực Tế

### 📖 Kịch bản 1: Nhân viên tạo lịch họp (USER)

1. **Đăng nhập** vào hệ thống
2. Vào **Lịch làm việc**
3. Nhấn **Tạo lịch mới**
4. Điền:
   - Tiêu đề: "Họp nhóm dự án X"
   - Loại: "Cuộc họp"
   - Ngày: 25/02/2026
   - Giờ: 14:00 - 15:30
   - Địa điểm: "Phòng họp tầng 3"
   - Người tham gia: Chọn 3 đồng nghiệp
   - Nhắc nhở: Trước 15 phút
5. Nhấn **Lưu**
6. ✅ Kết quả: Lịch được tạo, 3 đồng nghiệp nhận thông báo và thấy lịch trong trang của mình

---

### 📖 Kịch bản 2: Admin tạo tài khoản nhân viên mới

1. **Đăng nhập** với tài khoản Admin
2. Vào **Quản lý người dùng**
3. Nhấn **Thêm người dùng**
4. Điền thông tin:
   - Họ tên: "Nguyễn Văn A"
   - Email: "nguyenvana@company.com"
   - Mật khẩu: "TempPass@2026"
   - Vai trò: "USER"
   - Phòng ban: "Phòng IT"
5. Nhấn **Tạo mới**
6. ✅ Kết quả: Tài khoản được tạo
7. **Gửi thông tin** đăng nhập cho nhân viên qua email/tin nhắn
8. **Nhắc nhân viên** đổi mật khẩu ngay sau khi đăng nhập lần đầu

---

### 📖 Kịch bản 3: Admin reset mật khẩu cho người dùng quên

1. Nhân viên liên hệ: "Em quên mật khẩu rồi, anh giúp em với!"
2. Admin **đăng nhập** hệ thống
3. Vào **Quản lý người dùng**
4. Tìm nhân viên đó, nhấn **Reset mật khẩu**
5. Nhập **Admin PIN** (ví dụ: 123456)
6. Nhập mật khẩu mới: "NewPass@2026"
7. Xác nhận
8. ✅ Kết quả: Mật khẩu được đổi
9. **Thông báo** cho nhân viên mật khẩu mới
10. **Nhắc** họ đổi lại ngay

---

### 📖 Kịch bản 4: Admin gửi thông báo khẩn

1. Có thông tin quan trọng cần thông báo cho tất cả nhân viên
2. Admin **đăng nhập**
3. Vào **Thông báo** > Tab **Gửi thông báo**
4. Điền:
   - Tiêu đề: "🚨 Thông báo nghỉ lễ 30/4 - 1/5"
   - Nội dung: "Công ty nghỉ lễ từ 30/4 đến 1/5. Mọi người sắp xếp công việc hợp lý."
   - Người nhận: Chọn tất cả
   - Độ ưu tiên: Cao
5. Nhấn **Gửi ngay**
6. ✅ Kết quả: Tất cả nhân viên đã đăng ký thiết bị sẽ nhận thông báo ngay lập tức

---

### 📖 Kịch bản 5: Admin kiểm tra ai đã chỉnh sửa lịch

1. Có lịch bị sửa, cần kiểm tra ai sửa
2. Admin **đăng nhập**
3. Vào **Nhật ký hệ thống**
4. **Lọc:**
   - Đối tượng: "Schedule" (Lịch)
   - Hành động: "UPDATE" (Cập nhật)
   - Thời gian: Hôm nay
5. Xem danh sách, tìm bản ghi liên quan
6. Click vào để xem chi tiết: Ai sửa, sửa gì, thời gian nào
7. ✅ Kết quả: Xác định được người sửa và nội dung thay đổi

---

## 💡 Mẹo Sử Dụng Hiệu Quả

### Dành cho USER:

✅ **Đăng ký thiết bị ngay:** Đăng ký cả máy tính và điện thoại để không bỏ lỡ thông báo  
✅ **Đặt nhắc nhở:** Luôn đặt nhắc nhở khi tạo lịch để không quên việc quan trọng  
✅ **Xem lịch tuần:** Mỗi sáng thứ 2, xem lịch tuần để nắm công việc cả tuần  
✅ **Đổi mật khẩu định kỳ:** Nên đổi mật khẩu 3-6 tháng/lần để bảo mật  
✅ **Kiểm tra lịch hàng ngày:** Mở hệ thống mỗi sáng để cập nhật công việc trong ngày

### Dành cho ADMIN:

✅ **Thiết lập Admin PIN ngay:** Đây là điều đầu tiên cần làm sau khi đăng nhập  
✅ **Ghi nhớ PIN:** Ghi PIN vào nơi an toàn, tránh quên  
✅ **Kiểm tra nhật ký định kỳ:** Mỗi tuần nên xem nhật ký để phát hiện bất thường  
✅ **Backup nhật ký:** Xuất Excel cuối mỗi tháng để lưu trữ  
✅ **Quản lý phòng ban:** Cập nhật phòng ban khi có người mới/chuyển đi  
✅ **Gửi thông báo nhắc:** Trước ngày lễ, sự kiện, nên gửi thông báo nhắc trước 1-2 ngày  
✅ **Không lạm dụng quyền:** Chỉ xem lịch người khác khi thực sự cần thiết

---

## ⚠️ Lưu Ý Quan Trọng

### 🔒 Về Bảo Mật:

- **Không chia sẻ mật khẩu** cho bất kỳ ai
- **Admin PIN** phải giữ bí mật tuyệt đối
- **Đổi mật khẩu ngay** sau khi nhận mật khẩu tạm từ Admin
- **Đăng xuất** khi rời khỏi máy tính
- **Không để người khác** truy cập bằng tài khoản của bạn

### 📱 Về Thông Báo:

- **Cần đăng ký thiết bị** mới nhận được thông báo
- **Cho phép trình duyệt** gửi thông báo khi có yêu cầu
- **Kiểm tra trạng thái thiết bị** định kỳ, nếu không hoạt động thì đăng ký lại
- **Không đăng ký quá nhiều thiết bị** không dùng (tốn tài nguyên)

### 📅 Về Lịch:

- **Tạo lịch trước ít nhất 1 ngày** để người tham gia có thời gian chuẩn bị
- **Kiểm tra trùng lịch** trước khi tạo mới
- **Cập nhật nếu có thay đổi** và thông báo cho người tham gia
- **Xóa lịch hủy** để tránh nhầm lẫn

### 👥 Về Quản Lý (Admin):

- **Không khóa tài khoản** khi chưa có lý do rõ ràng
- **Reset mật khẩu cẩn thận** và thông báo ngay cho người dùng
- **Kiểm tra nhật ký** để phát hiện hành vi bất thường
- **Backup dữ liệu** định kỳ (xuất nhật ký)

---

**📌 Tài liệu này luôn được cập nhật. Phiên bản mới nhất: 24/02/2026**
