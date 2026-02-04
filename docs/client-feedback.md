# Tổng hợp phản hồi khách hàng (mới nhất)

## 1. Thẻ & định danh

- Mỗi thẻ cứng có: QR code + 1 Serial ID riêng
- Thuật ngữ:
  - User = khách hàng sử dụng thẻ
  - Admin = bên quản trị hệ thống

## 2. Luồng truy cập

- Quét QR code → vào trang Welcome Aboard (slide 5 & 9 trong Canva)
- Nhập đúng Serial ID → vào trang Dashboard (slide 6 & 10 trong Canva)

## 3. Nội dung & mục đích trang Dashboard (User)

### Mục đích chính

- Theo dõi tình trạng thẻ
- Biết quyền lợi đang được hưởng
- Tạo động lực tiếp tục booking charter

### Thông tin hiển thị

- Card Status: hạng thẻ hiện tại (Base / Gold / Diamond)
- Current Privileges: quyền lợi theo hạng thẻ hiện tại
- Charter Price: giá thuê du thuyền theo hạng thẻ (admin có thể edit manually)
- Voyage History: lịch sử chuyến đi (destination, yacht, date, spending)
- Total Spending (up to now): tổng chi tiêu hiện tại, và còn bao nhiêu để lên hạng tiếp
- Next Privileges: quyền lợi hạng cao hơn (Gold / Diamond) để tạo động lực nâng hạng
- About Tam Sơn Yachting: giới thiệu ngắn + link về tamsonyachting.com

### Mục tiêu tổng thể của Dashboard

- Không phải hệ thống booking phức tạp
- Là trang theo dõi quyền lợi + tham chiếu giá + thúc đẩy khách tiếp tục charter

## 4. Admin Page – Tập trung tính năng vận hành thẻ

### 4.1 Dashboard (tổng quan nhanh)

Mục tiêu: Admin mở lên nắm tình hình ngay

- Tổng số thẻ đã issue (ví dụ: 50 cards) – admin tạo serial trước
- Số thẻ đã active (ví dụ: 20/50) – cần cách nhận diện thẻ đã nhập serial và login để theo dõi
- Số booking/voyage phát sinh trong 1 tuần vừa qua

### 4.2 Members (quản lý users & cards)

Mục tiêu: quản lý từng thẻ và người dùng thẻ

Mỗi member gồm:
- Serial ID
- Hạng thẻ hiện tại (Base / Gold / Diamond)
- Tổng spending (tách owner vs network users)
- Lịch sử chuyến đi (destination, yacht, date, booking type: owner / network)
- Trạng thái thẻ: active / inactive

Admin có thể:
- Tạo thẻ mới
- Update yêu cầu chi tiêu hạng thẻ
- Edit spending thẻ
- Deactivate thẻ

### 4.3 Benefits (quản lý quyền lợi theo hạng)

Mục tiêu: admin chỉnh quyền lợi mà không cần dev sửa code

Ví dụ:
- Base: giá charter A, ưu đãi B
- Gold: giá charter A’, ưu đãi B’
- Diamond: giá charter A’’, ưu đãi B’’

Admin có thể:
- Edit nội dung quyền lợi
- Edit giá charter theo từng hạng
- Update “Next privileges” hiển thị cho User

### 4.4 Reports (báo cáo & theo dõi hiệu quả)

Mục tiêu: đo hiệu quả chương trình thẻ

- Tổng spending theo tháng
- Số booking/voyage theo tháng
- Số khách lên Gold / Diamond
- Top members theo spending
- Export dữ liệu (Excel / CSV)

### 4.5 Settings

Mục tiêu: cấu hình logic vận hành

- Mức lên hạng:
  - Gold: sau USD 20,000
  - Diamond: sau USD 30,000
- Ngôn ngữ (VI / EN)
- Link về website Tam Sơn Yachting
- Tài khoản admin (login / password)
