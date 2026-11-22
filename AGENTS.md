# AGENTS.md — Quy tắc dự án cho mọi AI

File này là nguồn sự thật chung cho tất cả AI (Gemini, Claude, ChatGPT, Copilot, Cursor, Cline...) khi đọc hoặc chỉnh sửa dự án.

## 1. Bắt buộc đọc trước khi làm việc
Trước khi viết hoặc sửa bất kỳ dòng code nào, AI **phải đọc đủ 3 file**:
1. `AGENTS.md` (file này — kiến trúc & quy tắc)
2. `STATUS.md` (trạng thái hiện tại, lỗi đang tồn đọng, việc ưu tiên tiếp theo)
3. `DEVLOG.md` (lịch sử các thay đổi gần nhất để không làm lại việc cũ hoặc phá tính năng đã xong)

## 2. Thông tin dự án & Công nghệ
- **Tên game:** MyAndroidGame (đổi tên trong `capacitor.config.json` khi chốt tên chính thức)
- **Nền tảng mục tiêu:** Android (đóng gói `.apk` tự động qua GitHub Actions)
- **Công nghệ:** HTML5 Canvas + Vanilla JavaScript + CSS + Capacitor 6
- **Build pipeline:** `.github/workflows/build-apk.yml` tự chạy `npx cap add android` (nếu chưa có thư mục `android/`), `npx cap sync android`, và `./gradlew assembleDebug`.

## 3. Cấu trúc thư mục
- `www/index.html` — Khung HTML chính, khai báo viewport cho màn hình điện thoại
- `www/style.css` — Giao diện HUD, nút bấm cảm ứng, safe-area
- `www/game.js` — Vòng lặp game (`requestAnimationFrame`), xử lý cảm ứng, logic và render Canvas
- `capacitor.config.json` — Cấu hình `appId`, `appName`, `webDir`
- `.github/workflows/build-apk.yml` — Tự động build file `.apk` mỗi khi push lên `main`

## 4. Quy tắc code bắt buộc
- **Giữ code gọn trong `www/`:** Không thêm bundler phức tạp (Webpack/Vite) trừ khi người dùng yêu cầu rõ.
- **Ưu tiên trải nghiệm cảm ứng Android:**
  - Dùng `pointerdown` / `pointermove` / `pointerup` và đặt `touch-action: none` trên Canvas.
  - Hỗ trợ `window.devicePixelRatio` để đồ họa nét trên màn hình độ phân giải cao.
  - Tính chuyển động theo `deltaTime` (`dt`) để tốc độ game ổn định trên cả màn hình 60Hz, 120Hz và 144Hz.
  - Lưu dữ liệu người chơi (điểm cao, cài đặt) bằng `localStorage` có `try/catch`.
- **Không commit thư mục `android/` hoặc `node_modules/`:** Đã được liệt kê trong `.gitignore` để repo nhẹ và dễ đọc.

## 5. Quy tắc kết thúc phiên làm việc (Bắt buộc)
Sau khi hoàn thành yêu cầu của người dùng, AI **phải**:
1. Cập nhật `DEVLOG.md`: Thêm một mục mới theo ngày, ghi rõ đã thêm/sửa file nào và lý do.
2. Cập nhật `STATUS.md`: Đánh dấu việc đã xong, cập nhật danh sách lỗi (nếu có) và việc tiếp theo.
3. Gợi ý thông điệp Git commit ngắn gọn, rõ ràng (ví dụ: `feat: thêm hệ thống nâng cấp nhân vật`).
