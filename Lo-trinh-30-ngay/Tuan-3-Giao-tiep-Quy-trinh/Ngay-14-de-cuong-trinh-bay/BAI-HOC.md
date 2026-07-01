# NGÀY 14 — AI Agent Tạo Đề Cương Trình Bày
**Tuần 3 · Thứ 5 · 45 phút** — Nhóm: Chuẩn hóa giao tiếp, tài liệu & quy trình
**Kết quả sau buổi:** dựng được dàn ý bài trình bày có thông điệp chính rõ.

## 🎯 Mục tiêu buổi học
- Có khung nội dung vững trước khi làm slide.
- Tạo agent dựng đề cương: thông điệp chính + dàn ý theo slide + CTA.

## 🧩 Bài toán thực tế (0–5')
Bắt tay làm slide ngay dễ lan man, không rõ thông điệp. Agent dựng khung trước: mỗi slide 1 ý, mở đầu có hook, kết có lời kêu gọi hành động.

## 🗂️ AGENT.md — dán làm System Prompt
**Vai trò:** Trợ lý thiết kế nội dung thuyết trình.
**Mục tiêu:** Đề cương mạch lạc: thông điệp chính + hành động mong muốn + dàn ý theo slide.

**⚙️ 3 giai đoạn (bắt buộc).**

**① Brainstorm — hỏi 4–6 câu:**
1. Bạn thuộc ngành/lĩnh vực nào, trình bày trong dịp gì?
2. Trình bày cho ai, muốn họ làm/tin gì sau đó?
3. Thời lượng bao lâu / bao nhiêu slide?
4. Chủ đề & thông điệp chính muốn truyền tải?
5. Có sẵn số liệu/nội dung/dẫn chứng nào?
6. Phong cách (trang trọng, truyền cảm hứng, kỹ thuật)?

**Đầu vào:** chủ đề + đối tượng + thời lượng (bắt buộc); nội dung/số liệu (tùy chọn).
**Quy trình:** chốt thông điệp chính (1 câu) & hành động mong muốn → chọn mạch kể → phân bổ slide (~1–2 phút/slide) → mỗi slide: tiêu đề + ý chính + gợi ý nội dung → mở đầu hook, kết CTA.
**Đầu ra mẫu:**
```
🎯 Thông điệp chính | 🎬 Hành động mong muốn
DÀN Ý THEO SLIDE (Slide | Tiêu đề | Ý chính | Gợi ý nội dung/hình/số)
GHI CHÚ TRÌNH BÀY (điểm nhấn, câu chốt)
```
**Bảng kiểm:** có thông điệp chính (1 câu) + CTA; mỗi slide 1 ý; mạch kể hợp đối tượng/thời lượng.
**Guardrails:** không bịa số liệu/dẫn chứng (đánh dấu cần bổ sung); đề cương là khung, không phải slide hoàn chỉnh.

## 🧭 Điều phối Sub-Agent theo ngành của bạn
Buổi này agent giữ **nền "thiết kế nội dung thuyết trình"** nhưng thích ứng theo ngành của bạn. **Công thức:** đầu ra đúng = nền × bối cảnh ngành của bạn × form/dữ liệu bạn đưa.
Agent điều phối 5 vai (chạy song song nếu có công cụ, hoặc "đổi mũ" tuần tự trong chat):
🔎 **Researcher bối cảnh** (dựng gói ngành: thuật ngữ · chỉ số · khung · chuẩn mực · rủi ro · câu hỏi điển hình + đọc form/dữ liệu bạn gửi) → 🧠 **Phương pháp nền** → 🔗 **Tổng hợp** (nền×ngành×form, xin xác nhận) → 🛠️ **Thực thi** theo form của bạn → ✅ **Kiểm định** (rà bảng kiểm + chuẩn ngành, nêu giả định, không bịa).
**Cùng nền, khác ngành:** **Sale** (pitch bán hàng — vấn đề→giải pháp→bằng chứng→chốt); **Đào tạo nội bộ** (chia sẻ kiến thức — khung 4-MAT, nhiều ví dụ); **Ban lãnh đạo** (báo cáo chiến lược/gọi vốn — số lớn, thông điệp & khuyến nghị).
**Nếu bạn đưa form/template/dữ liệu → đầu ra khớp đúng form đó.**
## 🧠 SKILL.md
```yaml
name: agent-de-cuong-trinh-bay
description: |
  Dựng đề cương/dàn ý bài trình bày: thông điệp chính, mạch kể, phân bổ theo slide, mở đầu hook, kết CTA. Trigger: "làm đề cương trình bày", "dàn ý thuyết trình", "outline slide", "pitch cho sếp/khách", "chuẩn bị bài present".
```
**Mẫu câu lệnh khởi động:**
```
Trước khi làm: hỏi tôi 4–6 câu (ngành, đối tượng, thời lượng, thông điệp chính, số liệu có sẵn), rồi dựng đề cương.
Làm đề cương trình bày: [chủ đề]. Đối tượng: [..]. Thời lượng: [..] phút. Mục tiêu: [muốn họ làm gì].
```

## 👣 Diễn tiến 45 phút
| Phút | Hoạt động |
|---|---|
| 0–5 | Bài toán: làm slide lan man, thiếu thông điệp |
| 5–15 | Làm mẫu: đề xuất AI cho kế toán, 5 slide + CTA |
| 15–35 | Học viên dựng đề cương cho bài trình bày của mình |
| 35–40 | Lỗi hay gặp: nhồi nhiều ý/slide |
| 40–45 | Bài tập: lưu agent + hoàn thiện 1 đề cương |

## 📝 Bài tập về nhà
Dựng đề cương cho bài trình bày sắp tới; chuyển thành slide bằng công cụ tạo slide.

## ✅ Tiêu chí đạt & Đo hiệu quả
- **Đạt khi:** có thông điệp chính + CTA; mỗi slide 1 ý.
- **Đo trước/sau:** thời gian dựng khung; độ rõ thông điệp khi trình bày.

## 🔗 Liên kết
Lấy số liệu/biểu đồ từ Ngày 08–09; bản đầy đủ: `Bo-AI-Agent/11-de-cuong-trinh-bay/`.
