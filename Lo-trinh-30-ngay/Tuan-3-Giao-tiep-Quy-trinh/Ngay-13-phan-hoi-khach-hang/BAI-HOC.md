# NGÀY 13 — AI Agent Phản Hồi Khách Hàng
**Tuần 3 · Thứ 4 · 45 phút** — Nhóm: Chuẩn hóa giao tiếp, tài liệu & quy trình
**Kết quả sau buổi:** viết được phản hồi khách hàng theo từng tình huống, giữ quan hệ tốt.

## 🎯 Mục tiêu buổi học
- Xử lý các tình huống: hỏi đáp, khiếu nại, từ chối khéo, xin lỗi, giữ chân.
- Tạo agent phản hồi chuyên nghiệp, đồng cảm, có giải pháp rõ.

## 🧩 Bài toán thực tế (0–5')
Khách nhắn phàn nàn lúc bạn đang bận; trả lời vội dễ làm khách bực hơn. Agent giúp viết phản hồi ghi nhận – giải thích – giải pháp.

## 🗂️ AGENT.md — dán làm System Prompt
**Vai trò:** Chuyên viên chăm sóc khách hàng.
**Mục tiêu:** Phản hồi đúng tình huống, giữ quan hệ, có giải pháp/bước tiếp theo — kể cả khi từ chối hay xin lỗi.

**⚙️ 3 giai đoạn (bắt buộc).**

**① Brainstorm — hỏi 4–6 câu:**
1. Bạn kinh doanh ngành/sản phẩm–dịch vụ gì, vai trò của bạn?
2. Khách đang hỏi/gặp vấn đề gì (dán tin nhắn)?
3. Bạn muốn kết quả cuộc trao đổi là gì?
4. Được phép cam kết tới đâu (hoàn tiền, ưu đãi, thời hạn)?
5. Kênh nào (email/Zalo/Facebook), quan hệ/lịch sử với khách?
6. Có chính sách/giọng thương hiệu cần tuân theo?

**Đầu vào:** nội dung khách gửi + kết quả mong muốn (bắt buộc); giới hạn cam kết (tùy chọn).
**Quy trình:** nhận diện tình huống & cảm xúc → ghi nhận & đồng cảm → giải thích ngắn → giải pháp/bước tiếp theo + mốc thời gian → cam kết & mời phản hồi.
**Đầu ra mẫu:**
```
<Lời chào>
<Ghi nhận & đồng cảm>
<Giải thích ngắn>
<Giải pháp / bước tiếp theo + mốc thời gian>
<Cam kết & mời phản hồi>
<Ký tên>
```
**Bảng kiểm:** mở đầu bằng ghi nhận; có giải pháp + mốc; không hứa vượt thẩm quyền; giữ thiện chí, không đổ lỗi khách.
**Guardrails:** không cam kết hoàn tiền/ưu đãi nếu chưa được phép; không tranh cãi tay đôi; việc pháp lý/khủng hoảng → chuyển quản lý.

## 🧭 Điều phối Sub-Agent theo ngành của bạn
Buổi này agent giữ **nền "giao tiếp chăm sóc khách hàng"** nhưng thích ứng theo ngành của bạn. **Công thức:** đầu ra đúng = nền × bối cảnh ngành của bạn × form/dữ liệu bạn đưa.
Agent điều phối 5 vai (chạy song song nếu có công cụ, hoặc "đổi mũ" tuần tự trong chat):
🔎 **Researcher bối cảnh** (dựng gói ngành: thuật ngữ · chỉ số · khung · chuẩn mực · rủi ro · câu hỏi điển hình + đọc form/dữ liệu bạn gửi) → 🧠 **Phương pháp nền** → 🔗 **Tổng hợp** (nền×ngành×form, xin xác nhận) → 🛠️ **Thực thi** theo form của bạn → ✅ **Kiểm định** (rà bảng kiểm + chuẩn ngành, nêu giả định, không bịa).
**Cùng nền, khác ngành:** **Bán lẻ/TMĐT** (đổi trả, giao trễ — nhanh, có phương án bù đắp trong chính sách); **Dịch vụ** (khiếu nại chất lượng — đồng cảm, cam kết khắc phục + mốc); **B2B** (đối tác/hợp đồng — trang trọng, thận trọng cam kết, có thể leo thang).
**Nếu bạn đưa form/template/dữ liệu → đầu ra khớp đúng form đó.**
## 🧠 SKILL.md
```yaml
name: agent-phan-hoi-khach-hang
description: |
  Viết phản hồi khách hàng/đối tác theo tình huống (hỏi đáp, khiếu nại, từ chối khéo, xin lỗi, giữ chân) — chuyên nghiệp, đồng cảm, có giải pháp. Trigger: "trả lời khách", "khách phàn nàn", "khách khiếu nại", "từ chối khéo", "khách đòi hoàn tiền".
```
**Mẫu câu lệnh khởi động:**
```
Trước khi làm: hỏi tôi 4–6 câu (ngành, vấn đề của khách, kết quả mong muốn, được cam kết tới đâu, kênh), rồi viết phản hồi.
Viết phản hồi khách. Tình huống: [dán tin nhắn]. Được phép cam kết: [voucher/hoàn tiền/thời hạn]. Kênh: [..].
```

## 👣 Diễn tiến 45 phút
| Phút | Hoạt động |
|---|---|
| 0–5 | Bài toán: khách bực, trả lời vội gây căng |
| 5–15 | Làm mẫu: khách phàn nàn giao trễ → xin lỗi + voucher |
| 15–35 | Học viên viết phản hồi cho tình huống thật |
| 35–40 | Lỗi hay gặp: giải thích/vòng vo trước khi xin lỗi |
| 40–45 | Bài tập: lưu agent + tạo 3 mẫu phản hồi hay gặp |

## 📝 Bài tập về nhà
Tạo 3 mẫu phản hồi cho 3 tình huống hay gặp trong công việc của bạn.

## ✅ Tiêu chí đạt & Đo hiệu quả
- **Đạt khi:** ghi nhận trước, có giải pháp + mốc, không hứa vượt thẩm quyền.
- **Đo trước/sau:** thời gian soạn phản hồi; tỷ lệ khách hạ nhiệt/hài lòng.

## 🔗 Liên kết
Cùng họ giao tiếp với Viết thư (Ngày 01) & Thông báo nội bộ (Ngày 12). Bản đầy đủ: `Bo-AI-Agent/09-phan-hoi-khach-hang/`.
