# Android Game Starter (HTML5 + Capacitor + GitHub Actions)

Bộ khung dự án game Android gọn nhẹ, tối ưu để nhiều AI (Gemini, Claude, ChatGPT, Copilot, Cursor...) cùng đọc, sửa và tự động xuất file `.apk` miễn phí trên GitHub.

## Cách đưa lên GitHub và tải file APK đầu tiên

1. Tạo một repository mới trên GitHub (để **Public** nếu muốn dán link cho AI trên web đọc trực tiếp, hoặc **Private** nếu làm việc qua VS Code / AI IDE).
2. Giải nén toàn bộ thư mục này và push lên nhánh `main`:
   ```bash
   git init
   git add .
   git commit -m "init: android game starter"
   git branch -M main
   git remote add origin https://github.com/<ten-cua-ban>/<ten-repo>.git
   git push -u origin main
   ```
3. Mở repo trên GitHub, vào tab **Actions** -> chọn workflow **Build Android APK** đang chạy (mất khoảng 2–4 phút).
4. Khi chạy xong (dấu tích xanh), kéo xuống mục **Artifacts** và tải `game-debug-apk` -> giải nén để lấy `app-debug.apk` và cài lên điện thoại.

## Cách làm việc với nhiều AI mà không cần kể lại hội thoại cũ

Mỗi khi mở phiên chat mới hoặc đổi sang AI khác, chỉ cần gửi câu lệnh mở đầu:

> Hãy đọc `AGENTS.md`, `STATUS.md` và `DEVLOG.md` trước để nắm toàn bộ dự án và lịch sử sửa đổi. Sau đó giúp tôi làm [yêu cầu mới]. Khi xong nhớ cập nhật lại `DEVLOG.md` và `STATUS.md`.
