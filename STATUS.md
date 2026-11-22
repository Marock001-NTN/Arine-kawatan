# STATUS.md — Trạng thái hiện tại của dự án

- **Phiên bản hiện tại:** `v0.1.0` (Bộ khung khởi tạo)
- **Cập nhật lần cuối:** 2026-11-23
- **Trạng thái build APK:** Sẵn sàng chạy trên GitHub Actions ngay khi push lên `main`

## Tính năng đã hoạt động
- [x] Khung dự án HTML5 + Capacitor 6 (`package.json`, `capacitor.config.json`)
- [x] Workflow GitHub Actions tự động build `app-debug.apk` mỗi lần push (`.github/workflows/build-apk.yml`)
- [x] Mini-game mẫu chơi được ngay trên cảm ứng (di chuyển phi thuyền, hứng sao ghi điểm, né thiên thạch, lưu điểm cao)
- [x] Hỗ trợ `deltaTime` cho màn hình tần số quét cao (60Hz–144Hz) và `devicePixelRatio`

## Lỗi đang tồn đọng / Hạn chế
- Chưa có âm thanh (Web Audio / SFX).
- Chưa cấu hình icon ứng dụng và splash screen riêng.
- Đang dùng Debug APK (chưa ký Release keystore để phát hành lên Google Play).

## Việc tiếp theo (Ưu tiên)
- [ ] Chốt ý tưởng, thể loại và tên chính thức của game (cập nhật `appId` và `appName` trong `capacitor.config.json`).
- [ ] Thay mini-game mẫu trong `www/` bằng gameplay chính.
- [ ] Thêm âm thanh hiệu ứng và menu cài đặt.
