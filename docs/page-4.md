# USER LANDING PAGE - ENTRY / WELCOME SCREEN

## BƯỚC 1 - QR ACCESS

1. Mục đích:
   - Dẫn vào hệ thống bằng trình duyệt (không cần app)
   - Chuẩn bị cho các bước xác thực tiếp theo
2. User Flow
   - User quét QR code trên thẻ Membership
   - QR mở Landing Page bằng trình duyệt (mobile / desktop)

## BƯỚC 2 - NHẬP SERIAL NUMBER THẺ

1. Mục đích:
   - Kích hoạt quyền lợi
   - Gắn user với thẻ cụ thể
2. Logic:
   - Mỗi thẻ = 1 serial number duy nhất
   - 1 serial number: dùng được cho nhiều user; mọi booking đều gắn về thẻ gốc
3. UI:
   - Input: Serial Number
   - Status: ‘Valid’ / ‘Invalid’ or ‘Active’

Admin tạo trước ID thẻ và tên chủ thẻ trên hệ thống. Khi khách hàng (user) nhập đúng số thẻ, hệ thống sẽ hiển thị trạng thái Active/Valid. Nếu hiển thị Invalid, có thể do thẻ chưa được tạo trên hệ thống (miss). Khi đó sẽ có nút “Liên hệ admin để được hỗ trợ thêm”.

4. Copy:
   - Welcome to Your Member Portal (more ideas)
   - Please enter your membership number to continue.
6. Language Selector: VI | EN
