# Vocab PWA — GitHub Pages

## 1. Tạo repository
1. Vào GitHub.
2. Chọn **New repository**.
3. Đặt tên, ví dụ: `vocab-app`.
4. Chọn **Public**.
5. Bấm **Create repository**.

## 2. Upload bộ PWA
Upload nguyên các file/thư mục ở đây vào **root** của repository:

- `index.html`
- `manifest.json`
- `sw.js`
- thư mục `icons/`

Quan trọng: không đổi `index.html` thành tên khác.

## 3. Bật GitHub Pages
Trong repository:

**Settings → Pages → Build and deployment**

- Source: **Deploy from a branch**
- Branch: **main**
- Folder: **/(root)**
- Bấm **Save**

Chờ GitHub deploy.

Link thường sẽ có dạng:

`https://TEN_GITHUB_CUA_BAN.github.io/vocab-app/`

Nếu repository của bạn tên khác thì phần cuối URL sẽ là tên repository đó.

## 4. Cài lên iPhone
1. Mở link GitHub Pages bằng **Safari**.
2. Chờ app tải xong ít nhất một lần khi đang có mạng.
3. Bấm nút **Share**.
4. Chọn **Add to Home Screen**.
5. Nếu iOS hiện tùy chọn **Open as Web App**, bật nó.
6. Bấm **Add**.

Ngoài Home Screen sẽ xuất hiện app **Vocab**.

## 5. Offline
Sau khi đã mở app online ít nhất một lần, service worker sẽ cache app để có thể mở lại khi mất mạng.

Font Awesome đang được app tải từ CDN. Service worker sẽ runtime-cache các file icon/font sau lần tải online đầu tiên, vì vậy hãy mở app online một lần trước khi thử offline.

## 6. Quan trọng: dữ liệu học cũ
`localStorage` phụ thuộc vào địa chỉ website.

Nếu bạn đã học bằng file HTML cũ hoặc một domain khác:

1. Mở app cũ.
2. Vào **Kho từ vựng → Sao lưu** để tải file JSON.
3. Mở app trên GitHub Pages.
4. Chọn **Khôi phục** và nhập file JSON đó.

Như vậy Level, lịch sử, missCount... sẽ được chuyển sang bản GitHub.

## 7. Cập nhật app sau này
Mỗi lần có file HTML mới:

1. Đổi nội dung `index.html` trong repository.
2. Nếu bạn thay đổi `sw.js`, nên tăng tên cache ở dòng đầu, ví dụ:
   `vocab-pwa-v1` → `vocab-pwa-v2`.
3. Commit thay đổi.
4. GitHub Pages sẽ tự deploy lại.

Bản service worker hiện tại dùng network-first cho trang HTML, nên khi có mạng app sẽ ưu tiên lấy bản mới nhất; khi offline mới dùng bản cache.
