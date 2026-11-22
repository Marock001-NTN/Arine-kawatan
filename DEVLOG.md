# DEVLOG.md — Nhật ký thay đổi dự án

Ghi chép ngắn gọn mọi thay đổi theo từng phiên làm việc để bất kỳ AI nào cũng nắm được lịch sử mà không cần đọc lại hội thoại cũ.

---

## 2026-11-23 — Khởi tạo bộ khung dự án (v0.1.0)
- **Tóm tắt:** Tạo bộ khung game Android dùng HTML5 Canvas + Capacitor 6 kèm auto-build APK trên GitHub Actions.
- **File đã tạo:**
  - `package.json`, `capacitor.config.json`, `.gitignore`
  - `.github/workflows/build-apk.yml` (tự động build `app-debug.apk` khi push lên `main`/`master` hoặc chạy tay)
  - `www/index.html`, `www/style.css`, `www/game.js` (mini-game mẫu cảm ứng để test pipeline cài APK)
  - `AGENTS.md`, `STATUS.md`, `DEVLOG.md`, `README.md`
- **Quyết định kỹ thuật:** Không commit thư mục `android/` để repo gọn nhẹ; GitHub Actions tự chạy `npx cap add android` và `npx cap sync android` khi build.

---

<!-- Mẫu cho phiên làm việc tiếp theo:
## YYYY-MM-DD — Tiêu đề ngắn gọn
- **Tóm tắt:** Đã làm gì?
- **File đã sửa/thêm:** `www/game.js`, ...
- **Lỗi đã fix / Lưu ý:** ...
-->
