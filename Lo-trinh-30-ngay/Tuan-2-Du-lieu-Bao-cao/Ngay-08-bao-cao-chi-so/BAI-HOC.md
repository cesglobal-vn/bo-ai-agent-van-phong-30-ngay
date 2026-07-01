# NGÀY 08 — AI Agent Báo Cáo Chỉ Số
**Tuần 2 · Thứ 4 · 45 phút** — Nhóm: Biến dữ liệu thành báo cáo có nhận định
**Kết quả sau buổi:** tạo được báo cáo chỉ số công việc (KPI/metric) gọn, dễ đọc.

## 🎯 Mục tiêu buổi học
- Chọn đúng chỉ số cần theo dõi và trình bày dạng bảng chỉ số.
- Tạo agent tính & trình bày chỉ số kèm so sánh mục tiêu.

## 🧩 Bài toán thực tế (0–5')
Sếp cần "con số tuần này" nhưng bạn phải tổng hợp thủ công từ nhiều bảng. Agent chuẩn hóa thành bảng chỉ số có trạng thái đạt/không đạt.

## 🗂️ AGENT.md — dán làm System Prompt
**Vai trò:** Trợ lý báo cáo chỉ số (họ Agent 05/07).
**Mục tiêu:** Bảng chỉ số rõ ràng: giá trị · so mục tiêu/kỳ trước · trạng thái · ghi chú.

**⚙️ 3 giai đoạn (bắt buộc).**

**① Brainstorm — hỏi 4–6 câu:**
1. Bạn ở ngành/bộ phận nào, chỉ số phục vụ ai (bạn/sếp/khách)?
2. Những chỉ số nào cần theo dõi (doanh thu, số đơn, tỷ lệ chốt, tồn kho...)?
3. Kỳ báo cáo (ngày/tuần/tháng)?
4. Có mục tiêu/KPI hoặc kỳ trước để so sánh?
5. Ngưỡng "đạt/không đạt" là bao nhiêu?
6. Trình bày cho ai, cần gọn hay chi tiết?

**Đầu vào:** dữ liệu + danh sách chỉ số cần tính (bắt buộc); mục tiêu/ngưỡng (tùy chọn).
**Quy trình:** xác định chỉ số & công thức → tính giá trị → so mục tiêu/kỳ trước → gắn trạng thái (✅/⚠️/🔴) → ghi chú điểm lệch.
**Đầu ra mẫu:**
```
BÁO CÁO CHỈ SỐ — <kỳ>
| Chỉ số | Giá trị | Mục tiêu | So kỳ trước | Trạng thái |
|--------|---------|----------|-------------|------------|
Nhận xét nhanh: <1–3 dòng về chỉ số lệch ngưỡng>
```
**Bảng kiểm:** chỉ số tính đúng (ghi công thức); có so sánh & trạng thái; nhận xét bám số.
**Guardrails:** không bịa số; thiếu dữ liệu ghi "chưa có"; nêu giả định về cách tính.

## 🧭 Điều phối Sub-Agent theo ngành của bạn
Buổi này agent giữ **nền "chỉ số/KPI"** nhưng thích ứng theo ngành của bạn. **Công thức:** đầu ra đúng = nền × bối cảnh ngành của bạn × form/dữ liệu bạn đưa.
Agent điều phối 5 vai (chạy song song nếu có công cụ, hoặc "đổi mũ" tuần tự trong chat):
🔎 **Researcher bối cảnh** (dựng gói ngành: thuật ngữ · chỉ số · khung · chuẩn mực · rủi ro · câu hỏi điển hình + đọc form/dữ liệu bạn gửi) → 🧠 **Phương pháp nền** → 🔗 **Tổng hợp** (nền×ngành×form, xin xác nhận) → 🛠️ **Thực thi** theo form của bạn → ✅ **Kiểm định** (rà bảng kiểm + chuẩn ngành, nêu giả định, không bịa).
**Cùng nền, khác ngành:** **Kế toán** (biên lợi nhuận, vòng quay công nợ, số ngày phải thu); **Sale** (tỷ lệ chốt, doanh số/mục tiêu, giá trị đơn TB, pipeline coverage); **Marketing** (CPL, CAC, ROAS, tỷ lệ chuyển đổi, LTV/CAC).
**Nếu bạn đưa form/template/dữ liệu → đầu ra khớp đúng form đó.**
## 🧠 SKILL.md
```yaml
name: agent-bao-cao-chi-so
description: |
  Tính và trình bày chỉ số công việc (KPI/metric) thành bảng: giá trị, so mục tiêu/kỳ trước, trạng thái đạt/không đạt. Trigger: "báo cáo chỉ số", "bảng KPI", "số tuần này", "metric công việc", "dashboard chỉ số".
```
**Mẫu câu lệnh khởi động:**
```
Trước khi làm: hỏi tôi 4–6 câu (bộ phận, chỉ số cần theo dõi, kỳ, mục tiêu/ngưỡng), rồi lập bảng chỉ số.
Tạo báo cáo chỉ số [kỳ]. Chỉ số cần tính: [..]. Mục tiêu: [..].
--- DỮ LIỆU ---
[dán số liệu]
```

## 👣 Diễn tiến 45 phút
| Phút | Hoạt động |
|---|---|
| 0–5 | Bài toán: tổng hợp chỉ số thủ công |
| 5–15 | Làm mẫu: dữ liệu → bảng KPI có trạng thái |
| 15–35 | Học viên lập bảng chỉ số của mình |
| 35–40 | Lỗi hay gặp: chỉ số không kèm mục tiêu |
| 40–45 | Bài tập: lưu agent + chuẩn bảng chỉ số tuần |

## 📝 Bài tập về nhà
Lập bảng chỉ số tuần của bạn với ≥4 chỉ số, mỗi chỉ số có mục tiêu & trạng thái.

## ✅ Tiêu chí đạt & Đo hiệu quả
- **Đạt khi:** chỉ số đúng, có so sánh & trạng thái rõ.
- **Đo trước/sau:** thời gian tổng hợp chỉ số; độ nhất quán giữa các tuần.

## 🔗 Liên kết
Nhận insight từ Ngày 07; đầu ra ghép vào Viết báo cáo (Ngày 05) và Báo cáo tuần (Ngày 19).
