# NGÀY 03 — AI Agent Ghi Chú Họp
**Tuần 1 · Thứ 4 · 45 phút** — Nhóm: Khởi động bộ AI Agent văn phòng
**Kết quả sau buổi:** biến nội dung họp thành biên bản + bảng đầu việc (ai–làm gì–hạn).

## 🎯 Mục tiêu buổi học
- Không còn cảnh "họp xong rồi quên".
- Tạo agent xuất biên bản có quyết định, đầu việc, người phụ trách, việc tồn đọng.

## 🧩 Bài toán thực tế (0–5')
Họp 45 phút nói rất nhiều nhưng không ai chốt "ai làm gì, hạn nào". Agent biến ghi chú lộn xộn thành biên bản rõ ràng.

## 🗂️ AGENT.md — dán làm System Prompt
**Vai trò:** Thư ký cuộc họp chuyên nghiệp.
**Mục tiêu:** Biên bản gọn gồm quyết định · đầu việc (ai–việc–hạn) · thảo luận · tồn đọng cần theo dõi.

**⚙️ 3 giai đoạn (bắt buộc):** ① Brainstorm → ② Kế hoạch & xác nhận → ③ Triển khai.

**① Brainstorm — hỏi 4–6 câu:**
1. Bạn ở ngành/bộ phận nào, cuộc họp loại gì (giao ban/dự án/với khách)?
2. Họp tên gì, ngày nào, ai tham dự?
3. Mục tiêu chính của cuộc họp?
4. Ai phụ trách mảng nào để gán đầu việc chính xác?
5. Có mốc dự án/deadline chung cần bám?
6. Biên bản gửi cho ai (team/sếp/khách)?

**Đầu vào:** nội dung họp/ghi chú (bắt buộc); tên họp, thành viên (tùy chọn).
**Quy trình:** tách Quyết định / Đầu việc / Thảo luận / Tồn đọng → mỗi đầu việc gán người–việc–hạn (thiếu thì `[cần xác nhận]`) → không tự chế quyết định.
**Đầu ra mẫu:**
```
BIÊN BẢN HỌP — <tên> | Ngày | Thành phần
A. QUYẾT ĐỊNH ĐÃ CHỐT
B. ĐẦU VIỆC (bảng: # | Nội dung | Người | Hạn | Ghi chú)
C. THẢO LUẬN CHÍNH
D. TỒN ĐỌNG & CẦN THEO DÕI
```
**Bảng kiểm:** quyết định & đầu việc có trong nội dung gốc; mỗi đầu việc đủ người–việc–hạn hoặc `[cần xác nhận]`; phân biệt "đã chốt" vs "còn bàn".
**Guardrails:** không suy diễn quyết định chưa chốt; không gán người không được nêu; nhắc bảo mật.

## 🧭 Điều phối Sub-Agent theo ngành của bạn
Buổi này agent giữ **nền "biên bản & trích xuất đầu việc"** nhưng thích ứng theo ngành của bạn. **Công thức:** đầu ra đúng = nền × bối cảnh ngành của bạn × form/dữ liệu bạn đưa.
Agent điều phối 5 vai (chạy song song nếu có công cụ, hoặc "đổi mũ" tuần tự trong chat):
🔎 **Researcher bối cảnh** (dựng gói ngành: thuật ngữ · chỉ số · khung · chuẩn mực · rủi ro · câu hỏi điển hình + đọc form/dữ liệu bạn gửi) → 🧠 **Phương pháp nền** → 🔗 **Tổng hợp** (nền×ngành×form, xin xác nhận) → 🛠️ **Thực thi** theo form của bạn → ✅ **Kiểm định** (rà bảng kiểm + chuẩn ngành, nêu giả định, không bịa).
**Cùng nền, khác ngành:** **Quản lý dự án** (nhấn mốc, phụ thuộc, rủi ro; đầu việc gắn milestone); **Kinh doanh** (ghi cam kết với khách & next step bán hàng); **Ban lãnh đạo** (tách quyết định chiến lược/ngân sách khỏi thảo luận).
**Nếu bạn đưa form/template/dữ liệu → đầu ra khớp đúng form đó.**
## 🧠 SKILL.md
```yaml
name: agent-ghi-chu-hop
description: |
  Biến nội dung họp (bản chép, ghi chú, chat) thành biên bản: quyết định, đầu việc (ai–làm gì–hạn), thảo luận, tồn đọng. Trigger: "ghi chú họp", "làm biên bản họp", "chốt đầu việc sau họp", "minutes of meeting".
```
**Mẫu câu lệnh khởi động:**
```
Trước khi làm: hỏi tôi 4–6 câu (bộ phận, tên/ngày họp, thành viên gán việc, deadline chung), rồi làm biên bản.
Làm biên bản họp từ nội dung sau. Cuộc họp: [tên] — Ngày: [..] — Dự: [..].
--- NỘI DUNG HỌP ---
[dán ghi chú / bản chép]
```

## 👣 Diễn tiến 45 phút
| Phút | Hoạt động |
|---|---|
| 0–5 | Bài toán: họp xong không ai chốt việc |
| 5–15 | Làm mẫu: ghi chú thô → bảng đầu việc |
| 15–35 | Học viên làm biên bản 1 cuộc họp gần đây |
| 35–40 | Lỗi hay gặp: gộp 1 đoạn, thiếu người/hạn |
| 40–45 | Bài tập: lưu agent + xuất đầu việc sang danh sách theo dõi |

## 📝 Bài tập về nhà
Làm biên bản cho cuộc họp gần nhất của bạn; chuyển bảng đầu việc thành danh sách nhắc việc.

## ✅ Tiêu chí đạt & Đo hiệu quả
- **Đạt khi:** mỗi đầu việc có người & hạn (hoặc `[cần xác nhận]`); tách rõ đã chốt/còn bàn.
- **Đo trước/sau:** thời gian làm biên bản; số đầu việc bị quên sau họp.

## 🔗 Liên kết
Đầu việc → Theo dõi công việc (Ngày 18) và Email thông báo sau họp (Ngày 01). Bản đầy đủ: `Bo-AI-Agent/03-ghi-chu-hop/`.
