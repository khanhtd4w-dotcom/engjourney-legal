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

Nội dung đang khai theo stack thực tế: **Supabase** (đăng nhập + dữ liệu), **Firebase** (Analytics + Crashlytics), **Google AdMob** (quảng cáo), **IAP qua App Store + Google Play**. Nếu sau này đổi/thêm dịch vụ, phải sửa mục "Third-party services" trong `privacy.html` cho khớp — Google Play đối chiếu nội dung này với khai báo Data Safety.

Hai thứ phải có trong app trước khi submit, nếu không sẽ bị từ chối:

1. **Luồng xoá tài khoản trong app** (`Settings → Account → Delete account`) đúng như trang `delete-account.html` mô tả. Google Play bắt buộc có đường xoá ngay trong app, không chỉ qua web.
2. **Consent screen cho quảng cáo** ở EEA/UK/Thuỵ Sĩ (Google UMP SDK) và **ATT prompt** trên iOS. Trang privacy đã cam kết có hai thứ này.

Khai Data Safety trên Play nhớ tick **Device or other IDs** vì AdMob thu thập Advertising ID.

## Cấu trúc

```
index.html          # trang chủ, điều hướng
privacy.html        # Privacy Policy (EN + VI)
terms.html          # Terms of Service (EN + VI)
delete-account.html # Hướng dẫn xoá tài khoản (EN + VI)
style.css           # style dùng chung, hỗ trợ dark mode
```

Sửa nội dung → commit → push. GitHub Pages tự deploy lại sau ~1 phút.
