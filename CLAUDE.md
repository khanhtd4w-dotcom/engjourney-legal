# engjourney-legal

Trang pháp lý tĩnh (HTML) của app **EngJourney**, host qua GitHub Pages tại `https://khanhtd4w-dotcom.github.io/engjourney-legal/`.

## Mục đích

Cung cấp URL công khai cho Privacy Policy, Terms of Service, và hướng dẫn xoá tài khoản — **bắt buộc** khi submit app lên Google Play Console và App Store Connect.

## Cấu trúc

```
index.html          — Trang chủ, điều hướng tới 3 trang pháp lý
privacy.html        — Privacy Policy (EN + VI, song ngữ)
terms.html          — Terms of Service (EN + VI, song ngữ)
delete-account.html — Hướng dẫn xoá tài khoản (EN + VI, song ngữ)
style.css           — Style dùng chung, hỗ trợ dark mode (prefers-color-scheme)
```

Không có framework/build step — sửa file HTML/CSS, commit, push, GitHub Pages tự deploy (~1 phút).

## Stack khai báo trong privacy.html

Nội dung privacy khai theo stack thực tế của EngJourney:
- **Supabase** — đăng nhập (Anonymous Auth + Google/Apple) + lưu dữ liệu học tập
- **Firebase** — Analytics + Crashlytics
- **Google AdMob** — quảng cáo (chủ ý, chưa gắn SDK)
- **IAP** qua Google Play + App Store (chưa live)

Nếu sau này đổi/thêm dịch vụ → phải sửa mục "Third-party services" trong `privacy.html` cho khớp — Google Play đối chiếu nội dung này với khai báo Data Safety.

## Quy tắc khi sửa

1. **Đổi nội dung pháp lý (privacy/terms/delete-account) PHẢI Edward duyệt trước khi push** — nội dung này ảnh hưởng compliance với Google Play/App Store, sai có thể bị reject hoặc gỡ app.
2. Sửa style/layout thuần tuý (CSS, HTML structure) không cần duyệt.
3. Luôn cập nhật "Last updated" date trong file khi thay đổi nội dung.
4. Giữ song ngữ EN + VI trong mọi trang (đã có anchor `#vi` cho phần tiếng Việt).
5. **Không thêm JavaScript, tracking, hay external dependency** — đây là trang pháp lý tĩnh, càng đơn giản càng tốt.

## Liên kết với dự án chính

- Repo docs + spec: `/Users/edward/Documents/Edward/EngJourney`
- Repo app Android: `engjourney-android/` (bên trong EngJourney)
- Email liên hệ: `engjourneyapp@gmail.com`
- GitHub Pages: cần bật trong repo Settings > Pages > Source: Deploy from branch `main`
