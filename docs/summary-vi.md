# Tóm tắt yêu cầu dự án (docs)

Liên kết nhanh: [Tech Stack](./tech-stack.md) · [User Stories](./user-stories.md)

## Tổng quan

- Dự án: chương trình thẻ VOYAGE+ và cổng thành viên của Tam Son Yachting
- Phạm vi giao diện: trang landing công khai (SEO), cổng người dùng, và trang quản trị
- Nền tảng: Web, responsive cho mobile/desktop
- Ngôn ngữ: VI | EN

## Bối cảnh hệ thống hiện tại

- Đã có website (ví dụ: abc.com) và hệ thống admin để quản lý blog/nhân sự...
- Kế hoạch: tái sử dụng codebase admin React hiện tại và bổ sung 3 trang/module mới (không tạo codebase mới trừ khi backend bị giới hạn).

## Thông tin bổ sung (Các trang)

- Các trang cần làm: User Page, Admin Page, Member Page
- User Page:
  - Truy cập qua QR code trên thẻ khách hàng với ID duy nhất
  - Sau khi quét, chuyển đến trang đăng nhập
  - Sau khi đăng nhập, người dùng xem quyền lợi, hạng, điểm
- Admin Page:
  - Nhân viên nhập điểm/score, chọn quyền lợi, CRUD quyền lợi cho khách hàng/thành viên
- Member Page:
  - Module mở rộng của admin hiện tại (bonus module)
  - Nhân viên quản lý khách hàng/thành viên (chỉ xem)
  - Xem điểm/score, quyền lợi, trạng thái active, ngày offline

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

### Card Overview
- Card name, Card status (Base/Gold/Diamond)
- Voyages completed (total)
- Tiến độ chi tiêu so với mốc $20k / $30k
- Last network booking (date + yacht)
- Progress indicator (vd: “x VND to reach Gold”)

### Charter Price
- Bảng giá thuê theo cấp thẻ
- Hiển thị giá trước và sau giảm
- Áp dụng cho Owners & Network users

### Card Benefits
- Base: giảm 10%
- Gold: giảm 15%, ưu tiên booking, invitation-only preview
- Diamond: giữ quyền lợi Gold + dịch vụ onboard (+30 mins), partner benefits
- UI checklist theo level; level cao bị khóa/grey nếu chưa đạt

### Voyage History
- Mỗi trip: ngày, tàu, route, loại booking (Self/Referral), trạng thái
- Hiển thị tiết kiệm cho trip Completed (vd: “You saved X VND”)

### Progress & Next Level
- Hiển thị số tiền cần để lên hạng tiếp theo (không dùng từ “tích lũy”)
- CTA: Book next voyage, View benefits at next level

### Future Privileges
- Teaser quyền lợi tương lai; greyed/label “Available at Gold/Diamond”
- Copy về ngưỡng chi tiêu và quyền lợi mở dần

### About TSY
- CTA: truy cập website Tam Son Yachting

## Admin Dashboard

### Quick Stats
- Total cards, Active cards, Newest bookings (kèm Card ID)
- Tap mở card list hoặc booking detail (mobile-friendly)

### Primary Actions
- Update giá charter
- View/Edit/Update member list (owner + khách mượn thẻ)
- Card status management (add/edit/delete)
- Post news/notices

### Recent Activity
- Timeline 3 ngày gần nhất: new member, new booking, card status updated
- Scrollable, tap xem chi tiết

### Modules Navigation
- Members, Benefits, Reports, Settings
- Layout grid hoặc sidebar; icon rõ, nhãn ngắn, nhất quán

## Định hướng thiết kế

- Mood/Tone: private, calm luxury, confident, không phô trương
- Visual: nền tối, neutral/champagne/gold accent
- Motion: chuyển động nhẹ (water movement, light reflection)
- UI priority: nhấn mạnh private rate, badge trạng thái rõ (Base/Gold/Diamond)
