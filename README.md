# BK-HOME Admin PWA — Hướng dẫn deploy GitHub Pages

## Cấu trúc file
```
bkhome-admin-app/
├── index.html      ← App chính
├── manifest.json   ← PWA manifest
├── sw.js           ← Service Worker (offline)
├── icons/
│   ├── icon-192.png
│   └── icon-512.png
└── README.md
```

## Các bước deploy lên GitHub Pages

### Bước 1 — Tạo repository
1. Vào github.com → New repository
2. Tên repo: `bkhome-admin` (hoặc tên tùy chọn)
3. Chọn Public → Create repository

### Bước 2 — Upload files
**Cách A (kéo thả — dễ nhất):**
1. Vào repo vừa tạo → Add file → Upload files
2. Kéo toàn bộ thư mục `bkhome-admin-app` vào
3. Commit changes

**Cách B (Git command line):**
```bash
cd bkhome-admin-app
git init
git add .
git commit -m "Initial BK-HOME Admin PWA"
git branch -M main
git remote add origin https://github.com/[username]/bkhome-admin.git
git push -u origin main
```

### Bước 3 — Bật GitHub Pages
1. Vào Settings → Pages
2. Source: Deploy from a branch
3. Branch: main / root → Save
4. Chờ ~2 phút

### Bước 4 — Truy cập app
URL sẽ là: `https://[username].github.io/bkhome-admin/`

---

## Cách nhân viên cài app trên điện thoại

### Android (Chrome):
1. Mở URL trên Chrome
2. Nhấn nút "Cài App ↓" trên header
3. Hoặc: menu Chrome (⋮) → "Thêm vào màn hình chính"

### iPhone (Safari):
1. Mở URL trên Safari (bắt buộc dùng Safari)
2. Nhấn nút Share (□↑) ở thanh dưới
3. Chọn "Thêm vào màn hình chính"
4. Đặt tên → Thêm

---

## Cập nhật nội dung
- Chỉnh sửa `index.html`
- Commit & push lên GitHub
- App tự động cập nhật khi nhân viên mở lại (do Service Worker)
- Không cần thông báo nhân viên cập nhật thủ công
