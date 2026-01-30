# BRIEF LANDING PAGE - VOYAGE+ CARD

thêm page tamsonyachting.com/voyageplus
(ko hiện trên menu bar ở homepage, chỉ hiện trên search engine)

## A. Objective

1. Xác thực & kích hoạt TSY Private Charter Card
2. Hiển thị giá thuê & quyền lợi riêng theo từng thẻ (Base / Gold / Diamond)
3. Theo dõi:
   - lịch sử sử dụng thẻ
   - số voyages (booking completed)
   - booking phát sinh từ refferal source
4. Thu thập thông tin khách thuê mới (CRM)

## C. DESIGN DIRECTION (để dev + UI thống nhất)

- Mood & Tone
  - Private / Calm luxury / Confident
  - Không phô trương
- Visual
  - Dark background
  - Neutral / champagne / gold accent
- Motion
  - Motion nhẹ:
    - Water movement
    - Light reflection
- UI priority
  - Highlight Private Rate
  - Status badge rõ (Base / Gold / Diamond)

## GLOBAL LOGIC (ÁP DỤNG TOÀN HỆ THỐNG)

- Voyage hợp lệ = booking status = Completed
- 1 booking completed = 1 voyage
- Refferal voyage
  - Booking phát sinh từ user không phải card owner
  - Nhưng dùng card serial hợp lệ
- Không dùng khái niệm điểm / tích lũy
  - Chỉ dùng:
    - Voyages logged
    - Total spending
- Không áp dụng song song với chương trình khuyến mãi khác

## B. USER TYPES & USER FLOW

1. Khách hàng
   - B1. Authentication: Nhập Card Serial Number để verify
   - B2. Sau khi verify, khách hàng được phép:
     - Xem:
       - a. Private rate (dynamic theo card status, hiển thị giá gốc + giá được ưu đãi)
       - b. Quyền lợi hiện tại & quyền lợi tương lai
       - c. Tổng spending theo card
     - Theo dõi:
       - a. Voyages history (lịch sử chuyến đi)
       - b. Card status (Base / Gold / Diamond)
       - c. Tổng spending của khách đang ở mức nào so với hạng thẻ tiếp theo (-> khuyến khích thêm chi tiêu)
     - Booking:
       - a. Book charter du thuyền với giá hiển thị theo card status
     - Notifications/ News:
       - Gửi thông báo sau khi booking, sau khi hoàn thành trip, số điểm được cộng vào tài khoản
       - Thông báo chúc mừng sinh nhật chủ thẻ

2. Admin, có quyền
   - Card management
     - a. Tạo card mới (generate serial)
     - b. Gắn card owner
     - c. Update card status (manual override nếu cần)
     - d. Tạo thông báo hàng loạt cho users, thông báo custom cho từng user
   - Booking management
     - a. Update giá thuê chuẩn
     - b. Gắn booking với:
       - Card serial
       - Booking type: holder (chủ thẻ) or refferal (mượn thẻ)
     - c. Theo dõi:
       - Booking history
       - Network bookings
       - Tổng spending theo card
   - Other features:
     - Edit card owner
     - View member list
     - View / edit card status
     - View / edit notification / news
