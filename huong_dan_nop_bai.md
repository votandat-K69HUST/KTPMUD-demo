# 📋 Hướng Dẫn & Timeline Nộp Bài Đồ Án KTPMUD — Nhóm N04 (`173820_n04`)

> **Nguồn SSoT (cập nhật theo quy định hiệu lực từ `25/11/2026`):**
> - Trang tóm tắt môn học: https://fossbk-spec.github.io/ktpmud-book/nop_bai
> - Repo nộp bài chung của lớp: https://github.com/fossbk-spec/ktpmud-project
> - Hướng dẫn chi tiết chuẩn (ưu tiên đọc trước mỗi lần PR): `CONTRIBUTING.md` và `scripts/validate_submission.py` trong repo `ktpmud-project`.

---

## ✅ Trạng thái mới nhất trên Repo chung của lớp (`fossbk-spec/ktpmud-project`)

1. **Đã được cấp `case_study_slug` và `case_study_id` chính thức:**
   - Ở commit `591fe77` (`PR #77`), giảng viên đã thêm đề tài của nhóm vào `VALID_CASE_STUDY_SLUGS` và `_TEMPLATE`:
     - **`case_study_slug`:** `dat_san_bong_da`
     - **`case_study_id`:** `CS-18`
     - **Thư mục nộp chuẩn:** `submissions/dat_san_bong_da_173820_n04/`
     - **Nhánh Git chuẩn:** `submit/dat_san_bong_da-173820_n04`
   - Hiện trên `main` của `fossbk-spec/ktpmud-project`, nhóm `173820_n04` mới có thư mục BKT (`hoang_mai_toan_173820_n04`), chưa có thư mục đồ án `dat_san_bong_da_173820_n04/` (chờ mở **PR #1**).
2. **Quy định bắt buộc hiệu lực từ 23/11 – 25/11:**
   - **`README.md` bắt buộc đủ 6 mục** theo mẫu `submissions/_TEMPLATE/README.md`:
     1. `Giới thiệu sản phẩm`
     2. `Phạm vi MVP`
     3. `Kiến trúc & công nghệ`
     4. `Cài đặt & cách sử dụng`
     5. `Hướng phát triển Tuần 11–15`
     6. `Nhóm & tuân thủ`
   - CI kiểm tra: đủ 6 mục, **≥ 800 ký tự**, không còn nội dung mẫu `(điền ...)`, đúng thư mục/slug, đủ `submission.json`, mọi file `≤ 10 MB`, không có `.env`/khóa bí mật.
   - **Cập nhật sau khi đã merge:** Mỗi tuần nộp tiếp bằng **PR mới** chỉ thêm/sửa file trong đúng thư mục của nhóm, **không cần hỏi giảng viên trước** cho cập nhật thường kỳ. Chỉ liên hệ giảng viên khi: đổi case study/mã nhóm, xóa file đã merge, nộp muộn, hoặc xung đột không tự xử lý được.
   - **Quyền riêng tư (tất cả 19 case study):** Chỉ dùng dữ liệu synthetic, **chỉ dùng MSSV (`202414021`, `20233605`, `202414018`)** — không ghi họ tên đầy đủ trong bất kỳ file nào nộp lên repo chung. *(Hack Marathon / BKT nộp riêng theo đề thi).*

---

## 1. Thông tin định danh nộp bài của nhóm

| Thuộc tính | Giá trị chuẩn khi nộp trên `ktpmud-project` | Ghi chú |
|---|---|---|
| **Case Study ID** | `CS-18` | Đề tài đặt sân bóng đá trực tuyến |
| **Case Study Slug** | `dat_san_bong_da` | Đã có trong `VALID_CASE_STUDY_SLUGS` |
| **Mã nhóm (`group_code`)** | `173820_n04` | Lớp `173820`, nhóm `N04` |
| **Danh sách MSSV (`members`)** | `["202414021", "20233605", "202414018"]` | Tuyệt đối không ghi họ tên đầy đủ trên repo chung |
| **Tên nhánh Git (branch)** | `submit/dat_san_bong_da-173820_n04` | Đúng quy ước `submit/<slug>-<mã lớp>_<số nhóm>` |
| **Thư mục nộp bài** | `submissions/dat_san_bong_da_173820_n04/` | `1 PR = 1 thư mục`, không sửa file ngoài thư mục này |
| **`scenario`** | `"khong_ap_dung"` | Chỉ CS-1 (Dr May Day) mới dùng giá trị khác |

---

## 2. Hạn nộp chính thức (cập nhật 25/11/2026)

> Mọi hạn nộp tính tới **`23:59`** của ngày mốc. **Bảo vệ đồ án diễn ra trong tuần 12–15 (`25/11 – 21/12/2026`).**

| Đợt / Tuần | Hạn nộp (`23:59`) | Sản phẩm bắt buộc phải nộp trong PR | Trạng thái |
|---|---|---|---|:---:|
| **Tuần 12 — PR #1** | **Thứ Tư 25/11/2026** | `README.md` bản đầu đủ 6 mục + `submission.json` + mã nguồn MVP + tài liệu SRS/C4 ban đầu + CI `[PASSED]` | 🚧 Sẵn sàng mở PR #1 *(vừa cập nhật slug `dat_san_bong_da`)* |
| **Tuần 13** | **Thứ Hai 30/11/2026** | `Test_Report_v1.md` (hoặc PDF) trong `report/` + bộ test tự động chạy 1 lệnh (`npm test`) + test máy sạch ≤ 15 phút + cập nhật Mục 5 `README.md` | ⬜ Chưa làm |
| **Tuần 14** | **Thứ Hai 07/12/2026** | Báo cáo bảo mật (RBAC, input validation, Zero PII/PHI, secret scan) & đánh giá AI (Ch.9–10) trong `report/` + cập nhật Mục 5 `README.md` | ⬜ Chưa làm |
| **Tuần 15** | **Thứ Hai 14/12/2026** | Review chéo 1 nhóm khác (comment trên PR/Issue nhóm bạn) + sửa góp ý + **Code Freeze** + **Video demo 3–5 phút** + cập nhật `README.md` | ⬜ Chưa làm |
| **Tuần 16 — Bản cuối** | **Chủ nhật 20/12/2026** | **PR cuối (`tag v1.0`)**: mã nguồn hoàn chỉnh + báo cáo cuối kỳ (`report/`) + slide (`slides/`, ≤ 10MB) + video demo + `README.md` bản cuối | ⬜ Chưa làm |

---

## 3. Kế hoạch công việc chi tiết từng đợt

### 📌 ĐỢT 1 — TUẦN 12, PR #1 (Mốc `25/11/2026 23:59`)
- [x] Đồng bộ `upstream/main` (`591fe77`) có slug `dat_san_bong_da` (`CS-18`).
- [x] Chuẩn hóa thư mục `submissions/dat_san_bong_da_173820_n04/` với `submission.json`, `README.md` đủ 6 mục, `src/frontend/` (Static SPA GitHub Pages + `localMockAdapter`), `report/`.
- [x] Đảm bảo `0` họ tên thật, `0` `.env`/secret, `0` file > 10 MB, `validate_submission.py` ra `[PASSED]`.
- [ ] **Mở PR #1** từ `votandat-K69HUST:submit/dat_san_bong_da-173820_n04` vào `fossbk-spec:main`, kiểm tra CI xanh ✅. *(Lưu ý: nếu nộp sau `25/11 23:59`, ghi rõ trong mô tả PR là vừa cập nhật theo `PR #77` mới thêm slug `dat_san_bong_da` để thầy/TA nắm).*

### 📌 ĐỢT 2 — TUẦN 13 (Hạn `30/11/2026 23:59`) — Test Report v1
- [ ] Bổ sung integration test cho các luồng `localMockAdapter` (đặt sân giữ chỗ 4h, chống trùng slot, hết hạn 4h, báo cọc, chủ sân duyệt/từ chối/hoàn tất, doanh thu).
- [ ] 1 thành viên test sạch theo `README.md` trên máy khác (≤ 15 phút).
- [ ] Tạo `report/Test_Report_v1.md` (thống kê unit/integration test, coverage, kịch bản kiểm thử thủ công, lỗi phát hiện & sửa).
- [ ] Cập nhật `README.md` và mở **PR mới** (sau khi PR #1 đã merge).

### 📌 ĐỢT 3 — TUẦN 14 (Hạn `07/12/2026 23:59`) — Bảo mật & Đánh giá AI
- [ ] Kiểm tra bảo mật & an toàn dữ liệu (phân quyền `CLIENT` / `PITCH_OWNER` trên UI & adapter, Zod validation, rà soát Zero PII/PHI, quét secret, tối ưu bundle/render).
- [ ] Viết báo cáo bảo mật, hiệu năng & đánh giá sử dụng AI (Ch.9–10) trong `report/`.
- [ ] Cập nhật `README.md` và mở **PR mới**.

### 📌 ĐỢT 4 — TUẦN 15 (Hạn `14/12/2026 23:59`) — Review chéo, Code Freeze & Video Demo
- [ ] Peer review 1 nhóm khác trên `fossbk-spec/ktpmud-project` và lưu lại link/nội dung nhận xét.
- [ ] Xử lý góp ý nhận được từ Peer Review / TA.
- [ ] Quay **video demo 3–5 phút** trên link GitHub Pages live (`https://votandat-k69hust.github.io/KTPMUD-demo/#/`), gắn link vào `README.md` + chụp 2–3 ảnh giao diện lưu vào `report/`.
- [ ] **Code Freeze** và mở **PR mới**.

### 📌 ĐỢT 5 — TUẦN 16, BẢN CUỐI (Hạn `20/12/2026 23:59`) — PR cuối (`tag v1.0`) & Bảo vệ (`25/11–21/12`)
- [ ] Hoàn thiện báo cáo kỹ thuật cuối kỳ (`report/`) và slide thuyết trình (`slides/`, dùng `HUST_PPT_template_2022_RED_4x3 (2).pptx`, kiểm tra ≤ 10 MB).
- [ ] Cập nhật `README.md` bản cuối (đầy đủ link demo, video, bảng Đã làm / Chưa làm, lộ trình hoàn thành) và gắn tag `v1.0`.
- [ ] Chạy `validate_submission.py` → mở **PR cuối** trước `20/12/2026 23:59` → CI xanh ✅.
- [ ] Bảo vệ trực tiếp bằng link GitHub Pages live (`https://votandat-k69hust.github.io/KTPMUD-demo/#/`).

---

## 4. Quy trình thao tác Git & Lệnh kiểm tra bắt buộc (mỗi lần nộp PR)

```powershell
# 1. Đồng bộ main từ repo gốc lớp (upstream)
git fetch upstream
git checkout main
git merge upstream/main

# 2. Tạo nhánh chuẩn (hoặc nhánh mới từ main cho các tuần sau khi PR cũ đã merge)
git checkout -b submit/dat_san_bong_da-173820_n04

# 3. Kiểm tra cục bộ trước khi commit/push
python scripts/validate_submission.py submissions/dat_san_bong_da_173820_n04
# Bắt buộc ra: [PASSED] Nộp bài hợp lệ.

# 4. Kiểm tra git status CHỈ thay đổi bên trong submissions/dat_san_bong_da_173820_n04/
git status

# 5. Commit & Push lên fork, sau đó mở Pull Request vào main của fossbk-spec/ktpmud-project
git add submissions/dat_san_bong_da_173820_n04
git commit -m "submit(dat_san_bong_da): nop bai nhom 173820_n04"
git push -u origin submit/dat_san_bong_da-173820_n04
```

### Checklist tự kiểm tra trước khi bấm "Create Pull Request"
- [ ] Chỉ sửa file bên trong **duy nhất 1 thư mục** `submissions/dat_san_bong_da_173820_n04/`?
- [ ] `submission.json` dùng đúng `"case_study_slug": "dat_san_bong_da"` và `"case_study_id": "CS-18"`?
- [ ] Không có `.env`, khóa API, mật khẩu, họ tên đầy đủ sinh viên (chỉ dùng MSSV `202414021`, `20233605`, `202414018`)?
- [ ] Không có file nào nặng **> 10 MB**?
- [ ] `README.md` đủ 6 mục, ≥ 800 ký tự, không còn chữ mẫu `(điền ...)`?
- [ ] Đã chạy `python scripts/validate_submission.py submissions/dat_san_bong_da_173820_n04` ra `[PASSED]`?

---

## 5. Nhật ký cập nhật tiến độ của nhóm

- **25/11/2026:** Chuyển toàn bộ sản phẩm sang Static SPA trên GitHub Pages (`HashRouter` + `localMockAdapter`), đẩy gói nộp đầu tiên lên fork.
- **26/11/2026:** Cập nhật theo quy định mới hiệu lực 25/11 và đồng bộ `upstream/main` (`591fe77`) — xác nhận giảng viên đã cấp slug chính thức `dat_san_bong_da` (`CS-18`); chuẩn hóa lại tên thư mục, nhánh và hạn nộp các tuần `25/11`, `30/11`, `07/12`, `14/12`, `20/12`.
