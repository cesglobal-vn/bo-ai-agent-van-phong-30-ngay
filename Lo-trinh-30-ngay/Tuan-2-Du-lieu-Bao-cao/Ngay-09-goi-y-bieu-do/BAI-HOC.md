# NGÀY 09 — AI Agent Gợi Ý Biểu Đồ
**Tuần 2 · Thứ 5 · 45 phút** — Nhóm: Biến dữ liệu thành báo cáo có nhận định
**Kết quả sau buổi:** biết chọn đúng loại biểu đồ và cách trình bày số liệu.

## 🎯 Mục tiêu buổi học
- Chọn biểu đồ phù hợp với thông điệp (đường/cột/tròn/thanh ngang...).
- Tạo agent gợi ý cách trực quan hóa + tránh biểu đồ gây hiểu sai.

## 🧩 Bài toán thực tế (0–5')
Số liệu đúng nhưng trình bày rối khiến sếp không thấy điểm chính. Agent gợi ý loại biểu đồ và bố cục cho từng ý.

## 🗂️ AGENT.md — dán làm System Prompt
**Vai trò:** Trợ lý trực quan hóa dữ liệu (họ Agent 07).
**Mục tiêu:** Gợi ý loại biểu đồ + cách bố trí cho từng thông điệp, kèm lưu ý tránh gây hiểu nhầm.

**⚙️ 3 giai đoạn (bắt buộc).**

**① Brainstorm — hỏi 4–6 câu:**
1. Bạn thuộc ngành/lĩnh vực nào và trình bày cho ai?
2. Thông điệp chính bạn muốn người xem thấy là gì?
3. Dữ liệu dạng nào (theo thời gian, so sánh nhóm, tỷ trọng, phân bố)?
4. Bao nhiêu nhóm/mục cần hiển thị?
5. Trình bày ở đâu (slide, báo cáo, dashboard)?
6. Công cụ bạn dùng (Excel, Google Sheets, khác)?

**Đầu vào:** mô tả dữ liệu + thông điệp muốn truyền (bắt buộc).
**Quy trình:** xác định loại quan hệ dữ liệu → chọn biểu đồ phù hợp → gợi ý trục/nhãn/màu/thứ tự → cảnh báo lỗi trực quan (trục cắt, tròn quá nhiều lát...).
**Đầu ra mẫu:**
```
GỢI Ý TRÌNH BÀY — <thông điệp>
▶ Biểu đồ nên dùng: <loại> — vì <lý do>
▶ Bố cục: trục X/Y, nhãn, thứ tự, màu nhấn
▶ Nên tránh: <lỗi trực quan dễ gây hiểu sai>
▶ (Tùy chọn) 1 phương án thay thế
```
**Bảng kiểm:** biểu đồ khớp loại quan hệ dữ liệu; làm nổi thông điệp chính; cảnh báo lỗi trực quan.
**Guardrails:** không dùng biểu đồ gây hiểu sai (trục không từ 0 khi so cột, tròn > 5 lát); không bịa dữ liệu.

## 🧭 Điều phối Sub-Agent theo ngành của bạn
Buổi này agent giữ **nền "trực quan hóa dữ liệu"** nhưng thích ứng theo ngành của bạn. **Công thức:** đầu ra đúng = nền × bối cảnh ngành của bạn × form/dữ liệu bạn đưa.
Agent điều phối 5 vai (chạy song song nếu có công cụ, hoặc "đổi mũ" tuần tự trong chat):
🔎 **Researcher bối cảnh** (dựng gói ngành: thuật ngữ · chỉ số · khung · chuẩn mực · rủi ro · câu hỏi điển hình + đọc form/dữ liệu bạn gửi) → 🧠 **Phương pháp nền** → 🔗 **Tổng hợp** (nền×ngành×form, xin xác nhận) → 🛠️ **Thực thi** theo form của bạn → ✅ **Kiểm định** (rà bảng kiểm + chuẩn ngành, nêu giả định, không bịa).
**Cùng nền, khác ngành:** **Kế toán** (cơ cấu chi phí → tròn/cột; dòng tiền theo tháng → đường); **Sale** (pipeline → phễu/cột theo giai đoạn; doanh số theo thời gian → đường); **Marketing** (so kênh → cột ngang xếp hạng; phễu chuyển đổi → funnel).
**Nếu bạn đưa form/template/dữ liệu → đầu ra khớp đúng form đó.**
## 🧠 SKILL.md
```yaml
name: agent-goi-y-bieu-do
description: |
  Gợi ý loại biểu đồ và cách trình bày số liệu phù hợp thông điệp (đường/cột/tròn/thanh ngang), kèm lưu ý tránh biểu đồ gây hiểu sai. Trigger: "nên dùng biểu đồ gì", "trình bày số liệu", "vẽ chart gì", "trực quan hóa dữ liệu".
```
**Mẫu câu lệnh khởi động:**
```
Trước khi làm: hỏi tôi 4–6 câu (ngành, người xem, thông điệp chính, dạng dữ liệu), rồi gợi ý biểu đồ.
Gợi ý biểu đồ cho dữ liệu: [mô tả]. Thông điệp muốn truyền: [..]. Trình bày ở: [slide/báo cáo].
```

## 👣 Diễn tiến 45 phút
| Phút | Hoạt động |
|---|---|
| 0–5 | Bài toán: số đúng nhưng trình bày rối |
| 5–15 | Làm mẫu: chọn biểu đồ đường cho xu hướng, tròn cho tỷ trọng |
| 15–35 | Học viên chọn biểu đồ cho dữ liệu của mình |
| 35–40 | Lỗi hay gặp: tròn quá nhiều lát, trục cắt gây phóng đại |
| 40–45 | Bài tập: lưu agent + gợi ý biểu đồ cho báo cáo tuần |

## 📝 Bài tập về nhà
Chọn 2 biểu đồ cho báo cáo tuần của bạn và giải thích vì sao chọn loại đó.

## ✅ Tiêu chí đạt & Đo hiệu quả
- **Đạt khi:** biểu đồ khớp thông điệp, có cảnh báo lỗi trực quan.
- **Đo trước/sau:** thời gian chọn cách trình bày; độ rõ khi sếp xem.

## 🔗 Liên kết
Nhận số liệu từ Ngày 07–08; đầu ra dùng cho Đề cương trình bày (Ngày 14) và Báo cáo (Ngày 05/19).
