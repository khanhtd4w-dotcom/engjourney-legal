# engjourney-legal

Trang pháp lý công khai của app **EngJourney** (dự án cá nhân), phục vụ submit lên Google Play + App Store.

## Link công khai (sau khi bật GitHub Pages)

| Trang | URL |
|---|---|
| Trang chủ | https://khanhtd4w-dotcom.github.io/engjourney-legal/ |
| Privacy Policy | https://khanhtd4w-dotcom.github.io/engjourney-legal/privacy.html |
| Terms of Service | https://khanhtd4w-dotcom.github.io/engjourney-legal/terms.html |
| Delete Account | https://khanhtd4w-dotcom.github.io/engjourney-legal/delete-account.html |

## Dùng ở đâu khi submit

- **Google Play Console** → App content → Privacy policy: dán link `privacy.html`
- **Google Play Console** → App content → Data deletion: dán link `delete-account.html` (bắt buộc nếu app có tài khoản)
- **App Store Connect** → App Information → Privacy Policy URL: dán link `privacy.html`
- **App Store Connect** → App Information → License Agreement: để mặc định của Apple, hoặc dán `terms.html` vào Custom EULA

## Cần kiểm tra lại trước khi submit

Nội dung hiện tại đang giả định app dùng **Firebase** (Auth/Analytics/Crashlytics/Firestore) và **IAP qua App Store + Google Play**. Nếu stack thực tế khác (Supabase, RevenueCat, AdMob, đăng nhập Facebook...), phải sửa mục "Third-party services" trong `privacy.html` cho khớp — Google Play đối chiếu nội dung này với khai báo Data Safety.

Ngoài ra cần đảm bảo app **thật sự có** luồng `Settings → Account → Delete account` như trang delete-account mô tả; Google Play bắt buộc có đường xoá tài khoản ngay trong app, không chỉ qua web.

## Cấu trúc

```
index.html          # trang chủ, điều hướng
privacy.html        # Privacy Policy (EN + VI)
terms.html          # Terms of Service (EN + VI)
delete-account.html # Hướng dẫn xoá tài khoản (EN + VI)
style.css           # style dùng chung, hỗ trợ dark mode
```

Sửa nội dung → commit → push. GitHub Pages tự deploy lại sau ~1 phút.
