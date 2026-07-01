# Bộ AI Agent Văn Phòng — CES Global

**Chương trình:** 30 Ngày Làm Chủ AI Agent Tự Động Hóa Công Việc Văn Phòng
**Đơn vị:** CES Global — Tư vấn, Đào tạo & Xây dựng giải pháp chuyển đổi AI cho doanh nghiệp Việt Nam
**Website:** cesglobal.com.vn · **Email BTC:** dichvukhachhang@cesglobal.com.vn · **Hotline/Zalo:** 0812996256 / 0941086923

---

## 1. Đây là gì?

Đây là **bộ định nghĩa chuẩn của 12 AI Agent** phục vụ công việc văn phòng, viết theo cấu trúc chuẩn quốc tế (Agent Specification) kết hợp chuẩn Skill của Claude, và được bản địa hóa cho bối cảnh doanh nghiệp Việt Nam.

Mỗi AI Agent gồm **2 file**:

| File | Vai trò | Dùng khi nào |
|---|---|---|
| **AGENT.md** | Bản đặc tả agent chuẩn quốc tế: vai trò, mục tiêu, đầu vào, quy trình, đầu ra, bảng kiểm, giới hạn, ví dụ, cách đo hiệu quả. | Khi học/thiết kế/giao việc cho agent, hoặc dán làm **System Prompt / Custom Instructions / Project Instructions**. |
| **SKILL.md** | Bản đóng gói theo chuẩn Skill của Claude: YAML frontmatter (`name`, `description` kèm từ khóa kích hoạt) + hướng dẫn ngắn gọn, mẫu câu lệnh, mẫu đầu ra. | Khi cài agent thành **Skill** trong Claude, hoặc làm mẫu câu lệnh nhanh cho học viên. |

> **Nguyên tắc vàng:** một AI Agent tốt = **đầu vào rõ**, **quy trình rõ**, **đầu ra rõ**, **cách kiểm tra rõ**, **dùng lại được mỗi ngày**.

---

## 2. Danh mục 12 AI Agent

| # | Thư mục | AI Agent | Nhóm việc |
|---|---|---|---|
| 01 | `01-viet-thu-dien-tu` | Viết thư điện tử | Giao tiếp |
| 02 | `02-tom-tat-tai-lieu` | Tóm tắt tài liệu | Tài liệu |
| 03 | `03-ghi-chu-hop` | Ghi chú họp | Họp |
| 04 | `04-lap-ke-hoach` | Lập kế hoạch | Kế hoạch |
| 05 | `05-viet-bao-cao` | Viết báo cáo | Báo cáo |
| 06 | `06-xu-ly-bang-tinh` | Xử lý bảng tính | Dữ liệu |
| 07 | `07-phan-tich-du-lieu` | Phân tích dữ liệu | Dữ liệu |
| 08 | `08-viet-quy-trinh` | Viết quy trình (SOP) | Vận hành |
| 09 | `09-phan-hoi-khach-hang` | Phản hồi khách hàng | Giao tiếp |
| 10 | `10-theo-doi-cong-viec` | Theo dõi công việc | Quản trị việc |
| 11 | `11-de-cuong-trinh-bay` | Tạo đề cương trình bày | Trình bày |
| 12 | `12-workspace-ca-nhan` | Xây AI Agent Workspace cá nhân | Hệ thống |

`_TEMPLATE/` chứa mẫu rỗng chuẩn để bạn tự tạo thêm agent mới.

---

## 3. Bản đồ theo lộ trình 30 ngày

| Tuần | Chủ đề | Agent trọng tâm |
|---|---|---|
| **Tuần 1** | Làm chủ AI Agent cá nhân | 01, 02, 03, 04 |
| **Tuần 2** | Bảng tính, dữ liệu và báo cáo | 05, 06, 07 |
| **Tuần 3** | Giao tiếp, tài liệu và quy trình | 08, 09, 11 |
| **Tuần 4** | Tự động hóa & kết nối hệ thống | 10, 12 (+ tổng hợp) |

---

## 4. Cấu trúc chuẩn của AGENT.md (12 mục)

```
Frontmatter: name, version, owner, language, model gợi ý
1.  Vai trò (Role)
2.  Mục tiêu (Objective)
3.  Bối cảnh & người dùng
4.  Đầu vào (Inputs) — bắt buộc / tùy chọn
5.  Quy trình xử lý (Workflow)
6.  Định dạng đầu ra (Output)
7.  Tiêu chí chất lượng & Bảng kiểm
8.  Giới hạn & An toàn (Guardrails)
9.  Câu hỏi làm rõ (Clarifying)
10. Ví dụ (Examples)
11. Đo hiệu quả (Metrics)
12. Ghi chú vận hành
```

## 5. Cấu trúc chuẩn của SKILL.md (chuẩn Claude)

```
---
name: <slug-khong-dau>
description: |
  <Mô tả + cụm từ kích hoạt (trigger) tiếng Việt>
---
# <Tên Agent>
Vai trò · Nguyên tắc · Mẫu câu lệnh · Mẫu đầu ra · Bảng kiểm · Ví dụ
```

---

## 6. Cách sử dụng

**A — Dán làm chỉ dẫn:** copy AGENT.md → dán vào System Prompt / Project Instructions của ChatGPT/Claude/Gemini → giao việc.
**B — Cài thành Skill (Claude):** copy thư mục agent kèm `SKILL.md` vào thư mục skills → Claude tự kích hoạt theo từ khóa.
**C — Mẫu câu lệnh nhanh:** mở SKILL.md → điền `[ ]` → gửi.

---

## 7. Bảo mật dữ liệu (mọi agent)

- Không dán dữ liệu nhạy cảm thật khi chưa được phép. Ưu tiên **dữ liệu mẫu / ẩn danh**.
- Luôn **kiểm tra đầu ra trước khi gửi/nộp** — AI hỗ trợ, con người chịu trách nhiệm cuối.

## 8. Đo hiệu quả (trước/sau)

1. Thời gian tiết kiệm · 2. Giảm thao tác lặp · 3. Tăng chất lượng · 4. Giảm lỗi · 5. Chuẩn hóa quy trình.
Hiệu quả **không bắt buộc quy ra tiền**.

---

## 9. Mô hình vận hành 3 giai đoạn (Brainstorm → Kế hoạch → Triển khai)

Học viên đến từ **nhiều ngành nghề, chuyên môn, lĩnh vực khác nhau**, nên mọi agent trong bộ này **không làm ngay** khi nhận yêu cầu. Mỗi agent luôn chạy tuần tự 3 giai đoạn:

1. **① Brainstorm ngữ cảnh** — hỏi **4–6 câu** để hiểu ngành nghề, vai trò, mục tiêu, đối tượng và ràng buộc của người dùng. Câu đầu tiên luôn hỏi *bạn làm ngành/lĩnh vực nào, vai trò gì*. Hỏi ngắn gọn theo cụm, không dồn một lần.
2. **② Lập kế hoạch & xác nhận** — tóm tắt lại ngữ cảnh đã hiểu, đề xuất cách làm (dàn ý/cấu trúc), xin người dùng xác nhận hoặc chỉnh.
3. **③ Triển khai** — thực hiện theo kế hoạch đã chốt, rồi tự rà bảng kiểm.

> **Ngoại lệ:** nếu người dùng đã cung cấp đủ ngữ cảnh ngay từ đầu, agent tóm tắt nhanh rồi vào giai đoạn ②/③ — không hỏi lại điều đã biết.

Trong **AGENT.md**, mô hình này nằm ở banner đầu file, ở **Mục 5 (bước 0)** và **Mục 9 (bộ câu hỏi brainstorm tuỳ biến theo agent)**. Trong **SKILL.md**, nằm ở banner đầu, **Nguyên tắc (điểm 0)** và mục **Giai đoạn 1 — Brainstorm ngữ cảnh**.


## 5B. Cơ chế điều phối Sub-Agent theo domain (bám đúng ngành khách hàng)

Học viên đến từ nhiều ngành (kế toán, sale, marketing, nhân sự, vận hành…) với form/template/dữ liệu khác nhau. Vì vậy mỗi agent giữ **một nền domain knowledge chung** nhưng có **lớp điều phối 5 sub-agent** để đầu ra bám đúng bối cảnh từng khách:

🔎 Researcher bối cảnh → 🧠 Chuyên gia phương pháp nền → 🔗 Tổng hợp → 🛠️ Thực thi → ✅ Kiểm định.

Ví dụ: cùng nền *phân tích dữ liệu*, nhưng đầu ra cho kế toán (dòng tiền, công nợ), sale (pipeline, tỷ lệ chốt) và marketing (CPL, ROAS) khác nhau. Nếu người dùng đưa form/template, đầu ra bám đúng form đó.

Khối này được nhúng ở **Mục 5B** của mọi AGENT.md và mục *Điều phối Sub-Agent theo domain* của mọi SKILL.md. Cơ chế đầy đủ (5 sub-agent, 2 chế độ chạy, ma trận thích ứng ngành, cách xử lý form/dữ liệu): xem `_CO-CHE-DIEU-PHOI-SUB-AGENT.md`.

*© CES Global — Bộ tài liệu chương trình "30 Ngày Làm Chủ AI Agent".*
