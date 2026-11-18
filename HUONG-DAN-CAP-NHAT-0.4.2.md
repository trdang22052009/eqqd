# Hướng dẫn cập nhật Ôn Thi AI v0.4.3 (hotfix Render)

Bản này sửa đúng hai lỗi TypeScript làm Render build thất bại trong v0.4.2:

- `TS6133`: tham số `completed` trong callback giải đề không được sử dụng. Đã đổi thành `_completed`.
- `TS2367`: điều kiện so sánh `exam.examType !== 'THPT'` là bất khả thi sau khi TypeScript đã thu hẹp kiểu về `TSA | HSA`. Đã bỏ điều kiện dư.

## Cập nhật vào GitHub hiện tại

1. Tải và giải nén ZIP v0.4.3.
2. Mở thư mục repository hiện tại bằng GitHub Desktop: Repository → Show in Explorer.
3. Mở thư mục `tsa-hsa-ai-render-simple` bên trong ZIP vừa giải nén.
4. Sao chép toàn bộ nội dung bên trong thư mục đó vào thư mục repository hiện tại, chọn ghi đè file trùng tên.
5. Không xóa thư mục `.git` của repository hiện tại.
6. GitHub Desktop → Summary: `Fix TypeScript build errors v0.4.3` → Commit to main → Push origin.
7. Render sẽ tự deploy theo commit mới.

## Cấu hình Render

Giữ nguyên Root Directory (để trống), Build Command `npm install && npm run build`, Start Command `npm start`. Không cần tạo service mới và không cần thay các biến môi trường API chỉ để sửa hai lỗi build này.

Sau deploy, mở Render → Events/Logs. Chỉ khi trạng thái là `Live` mới kiểm tra website. Nếu còn lỗi build, gửi ảnh phần cuối Build Logs.
