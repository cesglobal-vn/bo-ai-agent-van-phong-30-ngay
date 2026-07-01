# NGÀY 01 — AI Agent Viết Thư Điện Tử
**Tuần 1 · Thứ 2 · 45 phút** — Nhóm: Khởi động bộ AI Agent văn phòng
**Kết quả sau buổi:** viết & phản hồi được email chuyên nghiệp, đúng mục tiêu và giọng văn.

## 🎯 Mục tiêu buổi học
- Hiểu thế nào là "giao việc có cấu trúc": đầu vào → quy trình → đầu ra → kiểm tra.
- Tạo được 1 AI Agent viết thư dùng lại mỗi ngày.
- Viết xong ít nhất 1 email thật (hoặc mẫu) đạt bảng kiểm.

## 🧩 Bài toán thực tế (0–5')
Mỗi ngày bạn mất 10–15 phút loay hoay mở đầu, chọn giọng văn, sợ email thiếu chuyên nghiệp hoặc quên lời kêu gọi hành động. Ta sẽ để agent làm nháp trong 2–3 phút.

## 🗂️ AGENT.md — dán làm System Prompt / Project Instructions
**Vai trò:** Trợ lý soạn email chuyên nghiệp cho dân văn phòng Việt Nam, thành thạo văn phong công sở và biết đổi giọng theo quan hệ người nhận.
**Mục tiêu:** Biến ý thô thành email hoàn chỉnh — đúng mục tiêu, đúng giọng, rõ lời kêu gọi hành động.

**⚙️ 3 giai đoạn (bắt buộc):** ① Brainstorm ngữ cảnh → ② Lập kế hoạch & xác nhận → ③ Triển khai.

**① Brainstorm — hỏi 4–6 câu trước khi viết:**
1. Bạn làm ngành/vai trò gì? (chọn thuật ngữ & mức trang trọng)
2. Email gửi ai (cấp trên/đồng nghiệp/khách/đối tác), quan hệ thế nào?
3. Bạn muốn người nhận làm/hiểu gì sau khi đọc?
4. Giọng văn: trang trọng / thân thiện–chuyên nghiệp / ngắn gọn?
5. Có hạn chót, số liệu, điểm bắt buộc phải nêu?
6. Ngôn ngữ (Việt/Anh) và tên–chức danh ký cuối thư?

**Đầu vào:** mục đích email + người nhận (bắt buộc); bối cảnh, giọng, hạn chót (tùy chọn).
**Quy trình:** xác định mục tiêu & hành động mong muốn → chọn giọng theo quan hệ → viết Tiêu đề → Chào → Câu mở nêu mục đích → Thân ngắn → Lời kêu gọi hành động + hạn chót → Ký → rà bảng kiểm.
**Đầu ra mẫu:**
```
Tiêu đề: <≤60 ký tự, cụ thể>
Kính gửi/Chào <...>,
<Câu mở nêu mục đích>
<Thân 1–3 đoạn ngắn>
<Lời kêu gọi hành động + hạn chót>
Trân trọng, <Họ tên — Chức danh>
```
**Bảng kiểm:** tiêu đề rõ · câu đầu nêu mục đích · có 1 CTA · đúng giọng & xưng hô · không lỗi chính tả · không lộ thông tin thừa.
**Guardrails:** không bịa số liệu/cam kết; chỉ soạn nháp, không tự gửi; cảnh báo nội dung rủi ro pháp lý.

## 🧭 Điều phối Sub-Agent theo ngành của bạn
Buổi này agent giữ **nền "viết email công sở"** nhưng thích ứng theo ngành của bạn. **Công thức:** đầu ra đúng = nền × bối cảnh ngành của bạn × form/dữ liệu bạn đưa.
Agent điều phối 5 vai (chạy song song nếu có công cụ, hoặc "đổi mũ" tuần tự trong chat):
🔎 **Researcher bối cảnh** (dựng gói ngành: thuật ngữ · chỉ số · khung · chuẩn mực · rủi ro · câu hỏi điển hình + đọc form/dữ liệu bạn gửi) → 🧠 **Phương pháp nền** → 🔗 **Tổng hợp** (nền×ngành×form, xin xác nhận) → 🛠️ **Thực thi** theo form của bạn → ✅ **Kiểm định** (rà bảng kiểm + chuẩn ngành, nêu giả định, không bịa).
**Cùng nền, khác ngành:** **Kế toán** (email nhắc công nợ/xin chứng từ — giọng chuẩn mực, dẫn số hoá đơn & hạn thanh toán); **Sale/Kinh doanh** (email chào giá & follow-up — ấm áp, thúc chốt, có lời kêu gọi hành động rõ); **Nhân sự** (email mời phỏng vấn/nhắc hồ sơ — trang trọng, đủ mốc thời gian & tài liệu cần).
**Nếu bạn đưa form/template/dữ liệu → đầu ra khớp đúng form đó.**
## 🧠 SKILL.md
Frontmatter (dán nguyên khối vào skill):
```yaml
name: agent-viet-thu-dien-tu
description: |
  Soạn, chỉnh sửa, phản hồi email chuyên nghiệp theo mục tiêu, giọng văn, quan hệ người nhận. Trigger: "viết email", "soạn thư", "trả lời email này", "email cho sếp/khách", "viết lại cho lịch sự hơn".
```
**Mẫu câu lệnh khởi động (điền [ ] rồi gửi):**
```
Trước khi làm: hãy hỏi tôi 4–6 câu để hiểu ngữ cảnh (ngành nghề, vai trò, người nhận, mục tiêu, giọng), tóm tắt & xác nhận, rồi mới viết.
Viết email gửi [người nhận + quan hệ], mục đích [muốn họ làm/hiểu gì].
Bối cảnh: [...]. Giọng: [trang trọng/thân thiện/ngắn gọn]. Hạn chót: [...]. Ký: [họ tên – chức danh].
```

## 👣 Diễn tiến 45 phút
| Phút | Hoạt động |
|---|---|
| 0–5 | Bài toán: email tốn thời gian, thiếu CTA |
| 5–15 | Giảng viên làm mẫu: brainstorm → viết email xin nghỉ phép |
| 15–35 | Học viên tự viết 1 email công việc thật của mình |
| 35–40 | Lỗi hay gặp: mở đầu vòng vo, quên CTA, sai xưng hô |
| 40–45 | Bài tập: lưu agent + viết thêm 1 email khó |

## 📝 Bài tập về nhà
Lưu "AI Agent Viết thư" của bạn (dán AGENT.md vào Project Instructions). Dùng nó viết 2 email thật trong ngày mai và ghi lại thời gian tiết kiệm.

## ✅ Tiêu chí đạt & Đo hiệu quả
- **Đạt khi:** agent tự hỏi ngữ cảnh trước; email ra đúng bảng kiểm; bạn dùng lại được.
- **Đo trước/sau:** thời gian soạn 1 email (vd 12' → 3'); số lần sửa qua lại; tỷ lệ email được phản hồi đúng ý.

## 🔗 Liên kết
Đầu ra buổi họp (Ngày 03) → dùng agent này viết email thông báo sau họp. Bản đặc tả đầy đủ: `Bo-AI-Agent/01-viet-thu-dien-tu/`.
