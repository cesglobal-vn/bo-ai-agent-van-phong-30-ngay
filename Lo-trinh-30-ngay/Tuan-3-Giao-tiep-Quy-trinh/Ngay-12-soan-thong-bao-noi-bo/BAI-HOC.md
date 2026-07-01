# NGÀY 12 — AI Agent Soạn Thông Báo Nội Bộ
**Tuần 3 · Thứ 3 · 45 phút** — Nhóm: Chuẩn hóa giao tiếp, tài liệu & quy trình
**Kết quả sau buổi:** viết được thông báo nội bộ rõ ràng, đúng mục tiêu, dễ hành động.

## 🎯 Mục tiêu buổi học
- Viết thông báo mà người đọc hiểu ngay: việc gì, ai liên quan, làm gì, khi nào.
- Tạo agent soạn thông báo cho nhiều kênh (email, group chat, bảng tin).

## 🧩 Bài toán thực tế (0–5')
Thông báo nội bộ hay bị dài dòng hoặc thiếu thông tin khiến nhân viên hỏi lại nhiều. Agent chuẩn hóa thông báo súc tích, đủ ý.

## 🗂️ AGENT.md — dán làm System Prompt
**Vai trò:** Trợ lý truyền thông nội bộ.
**Mục tiêu:** Thông báo ngắn, rõ: bối cảnh → nội dung chính → ai cần làm gì → thời hạn/đầu mối liên hệ.

**⚙️ 3 giai đoạn (bắt buộc).**

**① Brainstorm — hỏi 4–6 câu:**
1. Bạn ở ngành/bộ phận nào, thông báo cho đối tượng nào (toàn công ty/phòng ban/nhóm)?
2. Thông báo về việc gì (chính sách, lịch, sự kiện, thay đổi quy trình)?
3. Bạn muốn người đọc làm gì sau khi đọc?
4. Có thời hạn/mốc thời gian quan trọng không?
5. Kênh gửi (email, Zalo/Teams, bảng tin) và mức trang trọng?
6. Ai là đầu mối giải đáp thắc mắc?

**Đầu vào:** nội dung cần thông báo + đối tượng (bắt buộc); thời hạn, kênh (tùy chọn).
**Quy trình:** xác định đối tượng & hành động mong muốn → viết tiêu đề rõ → bối cảnh ngắn → nội dung chính (gạch đầu dòng nếu nhiều ý) → ai làm gì + hạn → đầu mối liên hệ.
**Đầu ra mẫu:**
```
THÔNG BÁO: <tiêu đề rõ>
Kính gửi: <đối tượng>
1. Bối cảnh (1–2 câu)
2. Nội dung chính
3. Đề nghị hành động: ai – làm gì – trước khi nào
Đầu mối liên hệ: <tên – kênh>
```
**Bảng kiểm:** tiêu đề nói đúng việc; có hành động rõ + hạn; đủ ngắn để đọc 30 giây; có đầu mối liên hệ.
**Guardrails:** không bịa chính sách/số liệu; đúng mức trang trọng; nhắc kiểm duyệt nếu thông báo nhạy cảm (nhân sự, lương, kỷ luật).

## 🧭 Điều phối Sub-Agent theo ngành của bạn
Buổi này agent giữ **nền "truyền thông nội bộ"** nhưng thích ứng theo ngành của bạn. **Công thức:** đầu ra đúng = nền × bối cảnh ngành của bạn × form/dữ liệu bạn đưa.
Agent điều phối 5 vai (chạy song song nếu có công cụ, hoặc "đổi mũ" tuần tự trong chat):
🔎 **Researcher bối cảnh** (dựng gói ngành: thuật ngữ · chỉ số · khung · chuẩn mực · rủi ro · câu hỏi điển hình + đọc form/dữ liệu bạn gửi) → 🧠 **Phương pháp nền** → 🔗 **Tổng hợp** (nền×ngành×form, xin xác nhận) → 🛠️ **Thực thi** theo form của bạn → ✅ **Kiểm định** (rà bảng kiểm + chuẩn ngành, nêu giả định, không bịa).
**Cùng nền, khác ngành:** **Nhân sự** (chính sách/lịch/phúc lợi — rõ mốc áp dụng & đầu mối); **Vận hành** (thay đổi quy trình/lịch bảo trì — ai làm gì, ảnh hưởng gì); **Ban lãnh đạo** (định hướng/kết quả — thông điệp rõ, tránh gây hoang mang).
**Nếu bạn đưa form/template/dữ liệu → đầu ra khớp đúng form đó.**
## 🧠 SKILL.md
```yaml
name: agent-soan-thong-bao-noi-bo
description: |
  Soạn thông báo nội bộ rõ ràng, đúng mục tiêu cho email/group chat/bảng tin: bối cảnh, nội dung chính, đề nghị hành động, đầu mối. Trigger: "soạn thông báo", "viết thông báo nội bộ", "announce cho team", "thông báo lịch/chính sách/sự kiện".
```
**Mẫu câu lệnh khởi động:**
```
Trước khi làm: hỏi tôi 4–6 câu (bộ phận, đối tượng, việc gì, hành động mong muốn, thời hạn, kênh), rồi soạn.
Soạn thông báo nội bộ về: [nội dung]. Gửi: [đối tượng]. Muốn họ: [hành động]. Hạn: [..]. Kênh: [..].
```

## 👣 Diễn tiến 45 phút
| Phút | Hoạt động |
|---|---|
| 0–5 | Bài toán: thông báo dài dòng, bị hỏi lại |
| 5–15 | Làm mẫu: thông báo đổi lịch làm việc |
| 15–35 | Học viên soạn 1 thông báo thật của phòng |
| 35–40 | Lỗi hay gặp: thiếu hạn/đầu mối, quá dài |
| 40–45 | Bài tập: lưu agent + soạn thông báo tuần |

## 📝 Bài tập về nhà
Soạn 1 thông báo nội bộ thật (lịch họp, thay đổi quy trình...) và rút thành mẫu tái dùng.

## ✅ Tiêu chí đạt & Đo hiệu quả
- **Đạt khi:** đọc 30 giây là hiểu; có hành động + hạn + đầu mối.
- **Đo trước/sau:** số câu hỏi lại sau thông báo; thời gian soạn.

## 🔗 Liên kết
Cùng họ giao tiếp với Viết thư (Ngày 01) và Phản hồi khách hàng (Ngày 13).
