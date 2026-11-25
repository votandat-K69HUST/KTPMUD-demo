# 📋 Hướng Dẫn & Timeline Nộp Bài Đồ Án KTPMUD — Nhóm N04 (`173820_n04`)

> **Nguồn SSoT:**
> - Trang tóm tắt môn học: https://fossbk-spec.github.io/ktpmud-book/nop_bai
> - Repo nộp bài chung của lớp: https://github.com/fossbk-spec/ktpmud-project
> - Hướng dẫn chi tiết chuẩn (ưu tiên đọc trước mỗi lần PR): `CONTRIBUTING.md` và `scripts/validate_submission.py` trong repo `ktpmud-project`.
> - **Mục đích file này:** Lưu lại toàn bộ mốc thời gian, quy tắc CI/CD, việc cần làm từng tuần (Tuần 11 → Tuần 15) và bảng theo dõi tiến độ để nhóm tiện cập nhật qua từng đợt nộp PR.

---

## 🚨 Cảnh báo khẩn & Điểm cần xử lý NGAY (Cập nhật ngày 25/11/2026)

1. **Hạn nộp Tuần 11 là `23:59` Thứ Tư `25/11/2026`** (hôm nay).
2. **Vấn đề `case_study_slug` cho đề tài Soccer Booker:**
   - Theo `scripts/validate_submission.py` của `fossbk-spec/ktpmud-project`, trường `case_study_slug` hiện **chỉ chấp nhận 9 slug đồ án**:
     `may_day`, `suy_tim`, `alzheimer`, `dreye`, `dai_thao_duong`, `nha_cho_thue`, `ban_do_lich_su`, `ke_hoach_hoc_tap`, `quan_ly_thiet_bi_y_te` *(và 2 slug BKT là `may_day_sprint`, `hoang_mai_toan` — nhóm `173820_n04` hiện đã có thư mục BKT `hoang_mai_toan_173820_n04`, chưa có thư mục đồ án)*.
   - **Việc cần làm ngay:** Nhắn giảng viên/TA xác nhận/bổ sung slug cho đề tài **Hệ thống Đặt sân bóng đá trực tuyến (Soccer Booker)** của nhóm `173820_n04` vào `VALID_CASE_STUDY_SLUGS` của repo `ktpmud-project` (hoặc hỏi thầy ghép vào slug nào). Nếu cần nộp sau khi thầy thêm slug, xin phép thầy trước theo đúng quy định của `CONTRIBUTING.md`.
3. **Cảnh báo bảo mật & ẩn danh khi đưa code từ `D:\2026\2026.1\KTPMUD` sang repo chung (CI sẽ chặn hoặc bị trừ điểm nếu sót!):**
   - ❌ **KHÔNG ghi họ tên đầy đủ** (`Võ Tấn Đạt`, `Nguyễn Minh Quang`, `Bùi Tiến Đạt`) trong `submission.json`, `README.md`, code, hay tên file khi PR lên `ktpmud-project` (repo công khai vĩnh viễn) → **CHỈ dùng MSSV: `202414021`, `20233605`, `202414018`**. *(Lưu ý: chỉ giữ họ tên ở máy local hoặc báo cáo riêng theo yêu cầu lớp nếu tách riêng, còn mọi file đẩy vào `submissions/<slug>_173820_n04/` trên GitHub chung phải thay họ tên bằng MSSV).*
   - ❌ **KHÔNG commit file `.env`, `.env.local`, khóa API, mật khẩu thật hay chuỗi kết nối Neon `DATABASE_URL`** (`postgresql://neondb_owner:...`) vào thư mục nộp bài! Chỉ để file `.env.example` mẫu.
   - ❌ **KHÔNG dùng dữ liệu người thật (Zero PII/PHI):** toàn bộ user/sân/đơn đặt trong seed SQL phải là dữ liệu mô phỏng/synthetic.
   - ❌ **KHÔNG để bất kỳ file nào > 10 MB** trong thư mục nộp bài (kiểm tra kỹ các file `.docx`, `.pdf`, `.pptx`, video, ảnh trước khi copy vào `src/` hoặc `report/`). File nặng > 10 MB đưa lên Google Drive và dán link vào `README.md`.

---

## 1. Thông tin định danh nộp bài của nhóm

| Thuộc tính | Giá trị chuẩn khi nộp trên `ktpmud-project` | Ghi chú |
|---|---|---|
| **Mã nhóm (`group_code`)** | `173820_n04` | Lớp `173820`, nhóm `N04` |
| **Danh sách MSSV (`members`)** | `["202414021", "20233605", "202414018"]` | Tuyệt đối không ghi họ tên đầy đủ trên repo chung |
| **Tên nhánh Git (branch)** | `submit/<case_study_slug>-173820_n04` | Ví dụ: `submit/dat_san_bong-173820_n04` *(sau khi GV cấp slug)* |
| **Thư mục nộp bài** | `submissions/<case_study_slug>_173820_n04/` | Chỉ chữ thường, số, gạch dưới; 1 PR chỉ sửa đúng 1 thư mục này |
| **`scenario`** | `"khong_ap_dung"` | Chỉ CS-1 (Dr May Day) mới dùng giá trị khác |

---

## 2. Timeline tổng quan các mốc quan trọng (Tuần 11 → Tuần 15)

> Mọi hạn nộp dưới đây tính tới **`23:59`** của ngày mốc.

| Tuần | Thời gian | Hạn nộp PR (23:59) | Trọng tâm | Sản phẩm bắt buộc phải nộp trong PR | Trạng thái |
|:---:|---|---|---|---|:---:|
| **Tuần 11** | 18/11 – 23/11 | **Thứ Tư 25/11/2026** | Chốt MVP & nền tảng chất lượng | `submission.json` + `README.md` (đủ 6 mục, ≥ 800 ký tự) + mã nguồn MVP + SRS/C4 ban đầu; chạy `validate_submission.py` đạt `[PASSED]` | 🚧 Đang làm |
| **Tuần 12** | 24/11 – 30/11 | **Thứ Hai 30/11/2026** | Kiểm thử & tích hợp | Bộ test tự động chạy bằng 1 lệnh (mục tiêu ≥ 60% module cốt lõi) + `report/Test_Report_v1.md` (hoặc PDF) + test máy sạch + Audit Trail/logging + cập nhật Mục 5 `README.md` | ⬜ Chưa làm |
| **Tuần 13** | 01/12 – 07/12 | **Thứ Hai 07/12/2026** | Bảo mật, hiệu năng & AI | Báo cáo rà soát bảo mật (RBAC, input validation, secret scan) & hiệu năng + đánh giá/giới hạn công cụ AI (Ch.9–10) trong `report/` + cập nhật Mục 5 `README.md` | ⬜ Chưa làm |
| **Tuần 14** | 08/12 – 14/12 | **Thứ Hai 14/12/2026** | Review chéo & hoàn thiện | Peer review PR/Issue của 1 nhóm khác + sửa code theo góp ý nhận được + quay **video demo 3–5 phút** + chụp ảnh màn hình + **Code Freeze** cuối tuần + cập nhật `README.md` | ⬜ Chưa làm |
| **Tuần 15** | 15/12 – 21/12 | **Chủ nhật 20/12/2026** | Nghiệm thu & bảo vệ | **PR cuối (`tag v1.0`)**: mã nguồn hoàn chỉnh + Báo cáo kỹ thuật cuối kỳ (`report/`) + Slide thuyết trình (`slides/`) + Video demo + `README.md` bản cuối (bảng Đã làm / Chưa làm) | ⬜ Chưa làm |

---

## 3. Kế hoạch công việc chi tiết từng tuần

### 📌 MỐC 1 — TUẦN 11 (Hạn chót: `25/11/2026 23:59`) — Chốt MVP & PR #1
**Mục tiêu:** PR #1 được mở vào `fossbk-spec/ktpmud-project`, CI xanh ✅ (`[PASSED]`), người lạ đọc `README.md` chạy được MVP trong ≤ 15 phút.

- [ ] **1. Xin/xác nhận `case_study_slug` với Giảng viên/TA:**
  - Hỏi thầy/TA slug hợp lệ cho đề tài Soccer Booker của nhóm `173820_n04` để không bị `validate_submission.py` báo lỗi `VALID_CASE_STUDY_SLUGS`.
- [ ] **2. Đóng băng phạm vi MVP (Nhánh 1, 2, 4):**
  - Chốt rõ trong `README.md`: Nhánh 1 (Auth/Profile), Nhánh 2 (Tìm sân, Đặt sân giữ chỗ 4h, Báo cọc CK, Chủ sân duyệt/từ chối/hoàn tất, Đánh giá & Bình luận), Nhánh 4 (Quản lý cụm sân/giá khung giờ/khóa slot/doanh thu/audit log) → **Đã làm**; Nhánh 3 (Giải đấu/Ghép kèo) → **Ngoài phạm vi MVP**.
- [ ] **3. Tạo fork & nhánh nộp bài từ `ktpmud-project`:**
  - Fork `https://github.com/fossbk-spec/ktpmud-project` về tài khoản GitHub đại diện nhóm (thêm 2 bạn còn lại làm collaborator).
  - Clone fork, tạo nhánh `submit/<slug>-173820_n04`, copy `submissions/_TEMPLATE/` thành `submissions/<slug>_173820_n04/`.
- [ ] **4. Chuẩn hóa thư mục nộp `submissions/<slug>_173820_n04/`:**
  - Điền `submission.json` (chỉ gồm `case_study_slug`, `case_study_id`, `group_code: "173820_n04"`, `members: ["202414021", "20233605", "202414018"]`, `scenario: "khong_ap_dung"`, `submitted_at: "2026-11-25"`).
  - Copy code sạch vào `src/` (gồm `frontend/`, `demo_backend/`, `database/` — **BẮT BUỘC loại bỏ** `.env`, `node_modules/`, `dist/`, file `DATABASE_URL` thật, chuỗi mật khẩu thật, và rà lại xem có họ tên đầy đủ ở trang LandingPage/README/seed hay không để đổi sang MSSV/tên nhóm `173820_n04` trước khi đẩy lên repo công khai!).
  - Copy tài liệu SRS, C4 Model, ERD vào `report/` (đảm bảo mọi file ≤ 10 MB; cập nhật thông tin dùng MSSV).
  - Chụp sẵn tối thiểu 2–3 ảnh giao diện (Trang tìm sân/bản đồ, Đặt sân giữ chỗ 4h/Báo cọc, Dashboard Chủ sân) lưu trong `report/screenshot-01.png`, `02.png`, `03.png`.
- [ ] **5. Viết `README.md` chuẩn 6 mục bắt buộc (≥ 800 ký tự, không còn chữ mẫu):**
  1. `## 1. Giới thiệu sản phẩm`: tên Soccer Booker, bài toán, người dùng đích, 3–5 tính năng MVP, nhúng ảnh chụp `report/screenshot-01.png`.
  2. `## 2. Phạm vi MVP`: bảng ✅ Đã làm / 🚧 Đang làm / ⬜ Chưa làm / 🚫 Ngoài phạm vi (trung thực).
  3. `## 3. Kiến trúc & công nghệ`: 1 sơ đồ C4 Context/Container (Mermaid hoặc ảnh) + phiên bản Node 20, React/Vite, PostgreSQL + cấu trúc `src/`.
  4. `## 4. Cài đặt & cách sử dụng`: lệnh chạy chuẩn 100% trên máy sạch (tạo DB từ `V1` + `V2` + `V3`, copy `.env.example` thành `.env`, chạy backend & frontend, chạy test), tài khoản demo synthetic (`owner@soccerbooker.vn` / `client@soccerbooker.vn`), **≥ 3 kịch bản sử dụng chi tiết**.
  5. `## 5. Hướng phát triển Tuần 11–15`: bảng lộ trình gắn đúng MSSV phụ trách từng tuần (`202414021`, `20233605`, `202414018`) khớp với GitHub Issues/Project Board của nhóm.
  6. `## 6. Nhóm & tuân thủ`: mã nhóm `173820_n04`, MSSV + vai trò, xác nhận Zero PII/PHI, liệt kê công cụ AI đã dùng & phạm vi, link dữ liệu lớn nếu có.
- [ ] **6. Lập GitHub Issues & Project Board cho Tuần 12–15** (tạo backlog trên repo fork/nhóm khớp bảng Mục 5).
- [ ] **7. Chạy `validate_submission.py` cục bộ & mở PR #1:**
  - Phải thấy `[PASSED] Nộp bài hợp lệ.` trước khi push và tạo PR vào `main` của `fossbk-spec/ktpmud-project`.

---

### 📌 MỐC 2 — TUẦN 12 (Hạn chót: `30/11/2026 23:59`) — Kiểm thử & Tích hợp
**Mục tiêu:** Đạt độ phủ kiểm thử tự động tốt cho các luồng cốt lõi, chạy được bằng 1 lệnh, có `Test Report v1` và Audit Trail đầy đủ.

- [ ] **1. Mở rộng & chuẩn hóa bộ kiểm thử tự động (mục tiêu ≥ 60% module cốt lõi):**
  - Backend (`demo_backend`): bổ sung test tích hợp cho tất cả route `compat.routes.js`, chống đặt trùng lịch (`btree_gist` / transaction), auto-expire giữ chỗ 4h, luồng báo cọc → xác nhận → hoàn tất → doanh thu (`ownerRevenue`).
  - Frontend (`frontend`): bổ sung test cho `CheckoutPage`, `OrderManagementTable`, `PlayerBookingHistory`, `BookingPage` tìm kiếm không dấu.
  - Tạo script hoặc lệnh chạy test thống nhất trong `README.md` (chạy 1 lệnh kiểm tra cả BE + FE).
- [ ] **2. Chạy thử `README.md` trên máy sạch (Clean Machine Test):**
  - 1 thành viên không dùng máy đang dev tự clone repo, làm theo từng bước trong Mục 4 của `README.md`, đo thời gian chạy (bắt buộc ≤ 15 phút) và sửa mọi lỗi thiếu bước nếu gặp.
- [ ] **3. Kiểm tra Audit Trail & Logging (Chương 11):**
  - Đảm bảo mọi thao tác quan trọng (tạo đơn, hủy đơn, báo cọc, duyệt/từ chối cọc, chốt hoàn tất, sửa giá slot, khóa slot) đều ghi `audit_logs` đầy đủ `[actor_user_id, action, entity_type, entity_id, reason, created_at]` và xem được trên màn hình Chủ sân.
- [ ] **4. Viết báo cáo `report/Test_Report_v1.md` (hoặc `.pdf`):**
  - Thống kê số lượng unit test, integration test, E2E kịch bản thủ công, tỷ lệ pass, coverage các module chính, các lỗi đã phát hiện & cách khắc phục.
- [ ] **5. Cập nhật Mục 5 `README.md` (Tuần 11 → ✅, Tuần 12 → ✅) + mở PR #2** (chỉ đụng thư mục `submissions/<slug>_173820_n04/`).

---

### 📌 MỐC 3 — TUẦN 13 (Hạn chót: `07/12/2026 23:59`) — Bảo mật, Hiệu năng & AI
**Mục tiêu:** Không còn lỗ hổng bảo mật mức cao, có số liệu đo hiệu năng thực tế và báo cáo sử dụng AI minh bạch.

- [ ] **1. Rà soát bảo mật toàn hệ thống:**
  - Phân quyền RBAC: kiểm chứng mọi endpoint `/api/v1/owner/*` và `/api/v1/admin/*` trả `403` với `CLIENT`, kiểm tra IDOR (chủ sân A không sửa/duyệt được sân/đơn của chủ sân B; client A không hủy/báo cọc được đơn của client B).
  - Input validation (Zod/Express), SQL injection (100% parameterized query `$1, $2`), không lộ stack trace DB / thông tin nhạy cảm ở response lỗi production.
  - Quét lại toàn bộ repo để chắc chắn không có `.env`, secret key, JWT secret cứng hay PII.
- [ ] **2. Đo & tối ưu hiệu năng các điểm nghẽn:**
  - Đo latency các API nóng (`/player/venues`, `/player/venues/:id/availability`, `POST /player/bookings`, `/admin/dashboard/stats`) bằng script benchmark hoặc k6/autocannon.
  - Kiểm tra index PostgreSQL cho truy vấn kiểm tra slot trống & thống kê doanh thu.
- [ ] **3. Viết báo cáo bảo mật, hiệu năng & đánh giá AI trong `report/`:**
  - Checklist bảo mật + kết quả benchmark trước/sau tối ưu.
  - Ghi nhận minh bạch việc sử dụng AI trong quá trình phát triển (sinh code, thiết kế SQL, crawl/seed dữ liệu mẫu, review test), các rủi ro/giới hạn đã kiểm soát (ảo giác API, ép kiểu SQL PostgreSQL, đồng bộ schema...).
- [ ] **4. Cập nhật Mục 5 `README.md` (Tuần 13 → ✅) + mở PR #3.**

---

### 📌 MỐC 4 — TUẦN 14 (Hạn chót: `14/12/2026 23:59`) — Review chéo & Code Freeze
**Mục tiêu:** Hoàn thành Peer Review nhóm khác, xử lý góp ý, quay video demo và đóng băng code.

- [ ] **1. Thực hiện Peer Review cho ít nhất 1 nhóm khác trên `ktpmud-project`:**
  - Đọc `README.md`, chạy thử sản phẩm của nhóm được phân công (hoặc 1 nhóm cùng lớp), để lại nhận xét mang tính xây dựng trên PR/Issue của nhóm đó; lưu lại link comment/biên bản review chéo.
- [ ] **2. Tiếp nhận & sửa lỗi theo góp ý từ Peer Review / TA:**
  - Tạo commit sửa lỗi hoặc bổ sung tài liệu trên nhánh nộp bài.
- [ ] **3. Quay Video Demo 3–5 phút:**
  - Kịch bản quay trọn luồng: Tìm sân Hà Nội theo quận/từ khóa không dấu & bản đồ → Đặt sân giữ chỗ 4h → Báo chuyển khoản cọc → Chủ sân nhận đơn, xác nhận cọc, xem Dashboard doanh thu & Audit Log → Khách đánh giá sân.
  - Up video lên Drive/YouTube (unlisted) hoặc nén < 10MB nếu nhúng, gắn link vào `README.md`.
- [ ] **4. Code Freeze (Đóng băng code) cuối Tuần 14:**
  - Không thêm tính năng mới sau Code Freeze; chỉ sửa bug nghiêm trọng nếu có.
- [ ] **5. Cập nhật Mục 5 `README.md` (Tuần 14 → ✅) + hoàn thiện `README.md` + mở PR #4.**

---

### 📌 MỐC 5 — TUẦN 15 (Hạn chót bản cuối: `20/12/2026 23:59`) — Nghiệm thu & Bảo vệ
**Mục tiêu:** Nộp PR cuối hoàn chỉnh (`tag v1.0`) và bảo vệ thành công trước giảng viên.

- [ ] **1. Hoàn thiện Báo cáo kỹ thuật cuối kỳ (`report/`):**
  - Tổng hợp đầy đủ SRS, Use Case, C4 Model, ERD & Database Migration (`V1`–`V3`), kết quả Test, Bảo mật & Hiệu năng, Bảng đối chiếu Đã làm / Chưa làm, Nhật ký đóng góp theo MSSV.
- [ ] **2. Hoàn thiện Slide thuyết trình (`slides/`):**
  - Sử dụng template của trường (`HUST_PPT_template...` hoặc tương đương), kiểm tra dung lượng slide **≤ 10 MB** (nén ảnh trước khi xuất nếu vượt 10 MB!).
  - Có sẵn slide Demo trực tiếp + tài khoản demo + kịch bản dự phòng (video).
- [ ] **3. Cập nhật Mục 5 `README.md` (tất cả 5 tuần → ✅) & gắn tag `v1.0` trên fork.**
- [ ] **4. Chạy `validate_submission.py` lần cuối → Mở PR cuối trước `20/12/2026 23:59` → Đợi CI xanh ✅.**
- [ ] **5. Diễn tập bảo vệ & demo trực tiếp trên lớp** (chạy Backend + Frontend qua Neon DB hoặc Forward Port để thầy/lớp trải nghiệm trực tiếp).

---

## 4. Quy trình thao tác Git & Lệnh kiểm tra bắt buộc (mỗi lần nộp PR)

```powershell
# 1. Đồng bộ main từ repo gốc lớp (upstream)
git remote add upstream https://github.com/fossbk-spec/ktpmud-project.git
git fetch upstream
git checkout main
git merge upstream/main

# 2. Tạo nhánh mới (chỉ tạo lần đầu hoặc tạo nhánh mới cho PR tuần tiếp theo sau khi PR cũ đã merge)
git checkout -b submit/<case_study_slug>-173820_n04

# 3. Nếu là lần đầu: copy _TEMPLATE sang thư mục của nhóm
# (Nếu thư mục đã được merge lên main từ tuần trước: KHÔNG copy _TEMPLATE nữa, chỉ sửa trong thư mục đã có)
cp -r submissions/_TEMPLATE submissions/<case_study_slug>_173820_n04

# 4. BẮT BUỘC chạy validator cục bộ trước khi commit/push
python scripts/validate_submission.py submissions/<case_study_slug>_173820_n04
# Kết quả BẮT BUỘC phải in ra: [PASSED] Nộp bài hợp lệ.

# 5. Kiểm tra chắc chắn git status CHỈ thay đổi bên trong submissions/<case_study_slug>_173820_n04/
git status

# 6. Commit & Push lên fork, sau đó mở Pull Request vào main của fossbk-spec/ktpmud-project
git add submissions/<case_study_slug>_173820_n04
git commit -m "submit(<case_study_slug>): cap nhat bai nop tuan XX nhom 173820_n04"
git push -u origin submit/<case_study_slug>-173820_n04
```

### Checklist tự kiểm tra trước khi bấm "Create Pull Request"
- [ ] Chỉ sửa file bên trong **duy nhất 1 thư mục** `submissions/<case_study_slug>_173820_n04/`?
- [ ] Không có file `.env`, `.env.local`, khóa API, mật khẩu, chuỗi kết nối `DATABASE_URL` thật?
- [ ] Không có họ tên đầy đủ sinh viên trong `submission.json`, `README.md`, code, report đẩy lên repo công khai (chỉ dùng MSSV `202414021`, `20233605`, `202414018`)?
- [ ] Không có file nào nặng **> 10 MB** (nếu lớn hơn phải đẩy lên Drive và dán link trong `README.md`)?
- [ ] `README.md` có đủ **6 mục** khớp từ khóa (`giới thiệu`, `phạm vi`, `kiến trúc`/`công nghệ`, `cài đặt`/`cách sử dụng`, `hướng phát triển`/`tuần 11`, `tuân thủ`/`thành viên`/`nhóm &`), dài **≥ 800 ký tự**, và không còn chữ mẫu `(điền`, `<tên sản phẩm>`, `<case_study_slug>_<ma_nhom>`?
- [ ] Đã chạy `python scripts/validate_submission.py ...` ra `[PASSED]`?

---

## 5. Đối chiếu tài nguyên hiện có trong workspace `D:\2026\2026.1\KTPMUD`

| Thư mục / File hiện tại | Dùng cho mục nào khi nộp PR | Lưu ý trước khi copy vào `submissions/...` |
|---|---|---|
| `frontend/`, `demo_backend/` | `src/` | Xóa `node_modules/`, `dist/`, `.env`; chỉ giữ `.env.example`; rà tên thành viên ở `LandingPage.tsx`, `README.md`, `AuthLayout.tsx`, `AdminTopBar.tsx` chuyển về MSSV/tên nhóm nếu đẩy lên repo công khai |
| `submission/database/` (`V1`, `V2`, `V3`) | `src/database/` | Dữ liệu synthetic, sạch PII — dùng được luôn |
| `submission/README.md` / `submission/` | Tham khảo cho `report/` & `README.md` | Cần viết lại `README.md` gốc bài nộp theo đúng **6 mục mẫu** của `ktpmud-project` |
| `Bao_cao/`, `Bao_cao_cuoi_ky/`, `docs/` | `report/` | Kiểm tra dung lượng ≤ 10 MB/file và xóa/ẩn họ tên nếu up lên repo chung |
| `HUST_PPT_template_2022_RED_4x3 (2).pptx` | `slides/` | Hiện nặng ~3.68 MB (đạt giới hạn < 10 MB), nhớ không chèn quá nhiều ảnh nặng khiến file slide vượt 10 MB |

---

## 6. Nhật ký cập nhật tiến độ của nhóm

- **25/11/2026:** Đọc hướng dẫn `ktpmud-book/nop_bai`, `CONTRIBUTING.md`, `validate_submission.py`; lập timeline Tuần 11 → Tuần 15. Việc tiếp theo: liên hệ giảng viên/TA chốt `case_study_slug` cho nhóm `173820_n04` và chuẩn hóa gói nộp PR #1 (Tuần 11).
