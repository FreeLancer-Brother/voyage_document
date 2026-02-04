# Tóm tắt yêu cầu dự án (docs)

Liên kết nhanh: [Summary (EN)](./summary.md) · [Tech Stack](./tech-stack.md) · [User Stories](./user-stories.md) · [Client Feedback](./client-feedback.md)

## Tổng quan

- Dự án: chương trình thẻ VOYAGE+ và cổng thành viên của Tam Son Yachting
- Phạm vi giao diện: trang landing công khai (SEO), cổng người dùng, và trang quản trị
- Nền tảng: Web, responsive cho mobile/desktop
- Ngôn ngữ: VI | EN

## Bối cảnh hệ thống hiện tại

- Codebase hiện tại tại `D:\Freelancer\tamson-project\www` gồm:
  - Admin: React 17 (CRA) + Ant Design + Redux
  - Frontend site: Nuxt 2 (Vue)
  - API: NestJS + MongoDB (Mongoose) + JWT auth + export CSV
- Kế hoạch: tái sử dụng FE/Admin/API và bổ sung trang/module mới (không tạo codebase mới trừ khi backend bị giới hạn).

## Làm rõ mới nhất từ khách hàng

- Mỗi thẻ cứng có QR code và Serial ID riêng.
- Luồng truy cập:
  - Quét QR → Welcome Aboard
  - Nhập Serial ID → User Dashboard
- Mục tiêu User Dashboard: theo dõi trạng thái, quyền lợi, và thúc đẩy booking tiếp theo (không phải hệ thống booking phức tạp).
- Admin: tập trung tính năng vận hành thẻ, tránh làm quá phức tạp.

## Các trang cần làm

- User Page:
  - Truy cập qua QR code trên thẻ khách hàng với ID duy nhất
  - Sau khi quét, chuyển đến trang đăng nhập
  - Sau khi đăng nhập, người dùng xem quyền lợi, hạng, điểm
- Admin Page:
  - Nhân viên nhập điểm/score, chọn quyền lợi, CRUD quyền lợi cho khách hàng/thành viên

## Chương trình & quyền lợi

- Cấp thẻ: Base (mặc định), Gold (sau USD 20,000 chi tiêu/năm), Diamond (sau USD 30,000)
- Base:
  - Giảm 10% giá thuê du thuyền tiêu chuẩn (chưa VAT)
  - Chỉ hiển thị giá sau khi xác thực serial
  - Áp dụng cho chủ thẻ và khách mượn thẻ
- Gold:
  - Private rate 15%
  - Ưu tiên booking mùa cao điểm/cuối tuần
  - Invitation-only preview / priority yacht trial
  - Ưu đãi mua tàu đến 3% (tùy ngân sách/dòng tàu)
- Diamond:
  - Giữ toàn bộ quyền lợi Gold
  - Dịch vụ onboard: lộ trình tùy chỉnh, tăng thời gian +30 phút
  - Ưu đãi mua tàu đến 5% (tùy ngân sách/dòng tàu)
- Quy tắc:
  - Hạng thẻ theo tổng giá trị chi tiêu tích lũy
  - Không dùng khái niệm điểm tích lũy; chỉ theo dõi Voyages logged và Total spending
  - Không cộng dồn với các chương trình khuyến mãi/voucher khác

## Logic chung

- Voyage hợp lệ = booking status Completed
- 1 booking completed = 1 voyage
- Referral voyage = booking do người không phải chủ thẻ tạo nhưng dùng serial hợp lệ

## Landing Page công khai (SEO)

- URL: tamsonyachting.com/voyageplus
- Không hiển thị trên menu homepage; chỉ có trên search engine
- Mặc định hiển thị Welcome Aboard (không lộ dữ liệu riêng)
- Phải xác thực serial trước khi hiển thị dữ liệu private

## Entry / Welcome Screen (User)

- Mục đích: tạo cảm giác private/restricted, không cho vào nội dung trực tiếp
- UI: full-screen overlay / animated popup
- Nội dung:
  - Logo TSY, headline “Welcome Aboard”
  - Subheadline: Member Access via Card Serial Number
  - Subheadline: Admin Access
  - Subtext: chỉ cho phép truy cập bằng card serial
  - CTA: Enter Your Card ID
- Hành vi:
  - Serial hợp lệ → xác thực → vào dashboard
  - Serial sai → giữ overlay và hiển thị lỗi nhẹ

## Luồng người dùng

- Bước 1: QR access từ thẻ Membership
  - QR mở landing page bằng trình duyệt (mobile/desktop)
- Bước 2: Nhập serial thẻ
  - 1 thẻ = 1 serial duy nhất; serial có thể dùng cho nhiều user
  - Tất cả booking gắn với thẻ gốc
  - Status: Valid / Invalid / Active
  - Nếu Invalid: hiển thị nút liên hệ admin

## User Dashboard (Card Portal)

### Mục tiêu chính

- Theo dõi trạng thái thẻ
- Hiển thị quyền lợi hiện tại
- Thúc đẩy tiếp tục booking charter

### Card Status
- Hạng thẻ hiện tại: Base / Gold / Diamond

### Current Privileges
- Quyền lợi theo hạng thẻ hiện tại

### Charter Price
- Giá thuê du thuyền theo hạng
- Admin có thể chỉnh thủ công

### Voyage History
- Lịch sử chuyến đi (destination, yacht, date, spending)

### Total Spending (to date)
- Tổng chi tiêu hiện tại
- Số tiền còn lại để lên hạng tiếp theo

### Next Privileges
- Quyền lợi hạng cao hơn (Gold / Diamond)
- Mục đích tạo động lực nâng hạng

### About Tam Son Yachting
- Giới thiệu ngắn + link về website chính

## Admin Dashboard

### Dashboard (Tổng quan nhanh)
- Tổng số thẻ đã issue (admin tạo serial trước)
- Số thẻ đã active (đã nhập serial và login)
- Booking/voyage trong 1 tuần vừa qua

### Members (Users & Cards)
- Serial ID
- Hạng thẻ hiện tại (Base / Gold / Diamond)
- Tổng spending (tách owner vs network users)
- Lịch sử chuyến đi (destination, yacht, date, booking type)
- Trạng thái thẻ: active / inactive
- Admin có thể:
  - Tạo thẻ mới
  - Update yêu cầu chi tiêu hạng thẻ
  - Edit spending thẻ
  - Deactivate thẻ

### Benefits (Quản lý quyền lợi)
- Admin chỉnh quyền lợi theo hạng không cần dev sửa code
- Admin chỉnh giá charter theo hạng
- Admin cập nhật “Next privileges” hiển thị cho User

### Reports
- Tổng spending theo tháng
- Số booking/voyage theo tháng
- Số khách lên Gold / Diamond
- Top members theo spending
- Export dữ liệu (Excel/CSV)

### Settings
- Mức lên hạng: Gold sau USD 20,000; Diamond sau USD 30,000
- Ngôn ngữ (VI / EN)
- Link về website Tam Sơn Yachting
- Tài khoản admin (login/password)

## Định hướng thiết kế

- Mood/Tone: private, calm luxury, confident, không phô trương
- Visual: nền tối, neutral/champagne/gold accent
- Motion: chuyển động nhẹ (water movement, light reflection)
- UI priority: nhấn mạnh private rate, badge trạng thái rõ (Base/Gold/Diamond)
