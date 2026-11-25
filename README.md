# Hệ Thống Đặt Sân Bóng Đá Trực Tuyến (Soccer Booker)

Dự án **Nhóm 04 (`173820_n04`) – Môn KTPMUD** giải quyết quy trình đặt sân bóng đá phong trào (tìm sân theo khu vực & bản đồ GPS, xem bảng giá 6 khung giờ, đặt sân giữ chỗ 4 giờ với chuyển khoản cọc, đánh giá/hỏi đáp và quản lý cụm sân cho Chủ sân).

- **Live Demo (GitHub Pages — 100% Static, Không cần Database hay Server bên thứ 3):**  
  `https://votandat-k69hust.github.io/KTPMUD-demo/#/`

## Thành viên thực hiện (Nhóm 04 – Lớp 173820)
- **Võ Tấn Đạt** — MSSV: `202414021`
- **Nguyễn Minh Quang** — MSSV: `20233605`
- **Bùi Tiến Đạt** — MSSV: `202414018`

## Kiến trúc triển khai (Zero-Backend / GitHub Pages Static SPA)
* **Frontend:** React 19 + TypeScript + Vite 8 (`HashRouter` tương thích GitHub Pages `/#/`) + Tailwind CSS v4 + Leaflet OpenStreetMap.
* **Tầng dữ liệu trình duyệt (`localMockAdapter`):** Tích hợp trực tiếp tại `frontend/src/shared/api/localMockAdapter.ts` qua Axios adapter, lưu trữ bền vững trên `localStorage` của trình duyệt:
  * Tự động khởi tạo dữ liệu **10 cụm sân Hà Nội** (15 sân con 5v5/7v7/11v11, tọa độ GPS, bảng giá 6 khung giờ theo ngày thường/cuối tuần), tài khoản demo, lịch giữ chỗ 4 giờ, đánh giá & bình luận.
  * Xử lý đầy đủ đăng ký/đăng nhập, chống đặt trùng khung giờ, hết hạn giữ chỗ 4 giờ, báo chuyển khoản cọc, chủ sân xác nhận/chốt hóa đơn, quản lý sân/giá và thống kê doanh thu.
* **Auto-Deploy:** GitHub Actions (`.github/workflows/deploy-gh-pages.yml`) tự động build và deploy `frontend/dist` lên GitHub Pages khi push nhánh `main`.
* *(Thư mục `backend/`, `demo_backend/` và `submission/database/` được giữ lại như tài liệu/mã tham khảo thiết kế kiến trúc CSDL quan hệ).*

## Chạy cục bộ (≤ 2 phút, không cần cài DB)
```bash
cd frontend
cp .env.example .env    # Đã bật sẵn VITE_USE_MOCK_DB=true
npm install
npm run dev             # Truy cập http://localhost:5173/#/
npm test                # Chạy kiểm thử tự động (Vitest)
```

## Tài khoản Demo có sẵn (Synthetic)
- **Chủ sân (`PITCH_OWNER`):** `owner@soccerbooker.vn` / `Demo@123`
- **Khách hàng (`CLIENT`):** `client@soccerbooker.vn` / `Demo@123`
*(Hoặc bấm nút điền nhanh tài khoản Demo ngay tại trang Đăng nhập).*
