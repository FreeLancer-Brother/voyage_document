# USER LANDING PAGE - TRANG CHÍNH / CARD DASHBOARD

## SECTION CARD (PROFILE) OVERVIEW

1. Mục đích: Cho user biết họ đang ở trạng thái nào
2. Hiển thị:
   - Card Name: Tam Son Yachting private charter card sau khi nhập ID -> lời chào Card Holder (just ID)
   - Card Status (Base / Gold / Diamond)
   - Voyages Completed (total): X number
   - Booking Spending: (x / $20,000 / $30,000) -> details qua section 5
   - Last Network Booking (date + yacht) -> details qua section 4
   - Progress Indicator: “x vnd to reach Gold”

## SECTION CHARTER PRICE

1. Mục đích: bảng thông tin giá cho thuê các tàu theo từng hạng mức của thẻ. Hiển thị giá trước giảm & sau giảm
- Áp dụng cho: Owners & Network users

Base Privilege (Default)
- Discount 10%

Gold Privilege (spending $20,000 annual combined trips)
- Discount 15%

Diamond Privilege (spending $30,000 annual combined trips): Discount 15%

## SECTION CARD BENEFITS

1. Base: Ưu đãi charter rate (10%)
2. Gold
   - Ưu đãi charter rate (15%)
   - Priority booking (high season / weekend)
   - Invitation-only previews / trials
3. Diamond
   - Keep all Gold benefits
   - Complimentary onboard services:
     - Upgraded welcome catering set
     - Extended cruising time (+30 mins)
   - Benefits from TSY’s Partners:

UI: checklist theo level (Base / Gold / Diamond), Gold/Diamond có thể mở (locked) nếu chưa đạt

## SECTION VOYAGE HISTORY

1. Hiển thị mỗi trip (User view - gọn)
   - Date
   - Yacht model
   - Location / Route
   - Booking type: Self / Refferal
   - Status: Completed / Upcoming
2. Highlight giá trị:
   - “You saved X VND on this trip”
   - Chỉ hiển thị với trip Completed

## SECTION PROGRESS & NEXT LEVEL

1. Mục đích
   - Cho user thấy cần chi tiêu thêm bao nhiêu để lên level tiếp theo
   - Không dùng từ “tích lũy”
2. Hiển thị
   - “Only X VND in savings to unlock next privileges”
3. CTA
   - Book next voyage
   - View benefits at next level

## SECTION FUTURE PRIVILEGES (PUBLIC, NOT LOCKED CONTENT)

- “Additional privileges are unlocked when annual spending thresholds are met”
- “Benefits evolve with usage, not publicly available outside the system.”
- Hiển thị benefit nhưng greyed / labelled “Available at Gold / Diamond”

## SECTION ABOUT TSY

CTA: visit tam son yachting website

- NOTE: Landing Page có thể hiển thị trên Search Engine, vì chỉ khi nhập ID thì mới có thông tin cụ thể là gì. Trang default chỉ là Welcome Aboard
- Mở đầu brief bằng yêu cầu đăng nhập với tư cách user/admin, sau đó mới triển khai tính năng của mỗi giao diện.
