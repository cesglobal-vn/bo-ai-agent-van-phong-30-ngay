# NGÀY 16 — AI Agent Thu Thập Thông Tin
**Tuần 4 · Thứ 2 · 45 phút** — Nhóm: Ghép thành Workspace cá nhân tự động
**Kết quả sau buổi:** chuẩn hóa thông tin từ biểu mẫu/ghi chú thành dữ liệu gọn.

## 🎯 Mục tiêu buổi học
- Biến thông tin rời rạc (form, ghi chú, tin nhắn) thành bảng/cấu trúc dùng được.
- Tạo agent bóc tách trường thông tin theo mẫu cố định.

## 🧩 Bài toán thực tế (0–5')
Thông tin đến từ nhiều nguồn, mỗi người ghi một kiểu. Muốn tổng hợp phải chép tay lại. Agent chuẩn hóa về cùng một cấu trúc trường.

## 🗂️ AGENT.md — dán làm System Prompt
**Vai trò:** Trợ lý thu thập & chuẩn hóa thông tin.
**Mục tiêu:** Rút đúng trường cần thiết từ văn bản tự do và xuất về bảng/cấu trúc thống nhất.

**⚙️ 3 giai đoạn (bắt buộc).**

**① Brainstorm — hỏi 4–6 câu:**
1. Bạn ở ngành/bộ phận nào, thu thập thông tin để làm gì?
2. Nguồn thông tin là gì (form đăng ký, ghi chú, tin nhắn, email)?
3. Cần rút những trường nào (tên, SĐT, nhu cầu, ngày...)?
4. Định dạng đầu ra mong muốn (bảng, danh sách, CSV)?
5. Quy tắc chuẩn hóa (định dạng ngày, SĐT, viết hoa)?
6. Xử lý thế nào khi thiếu trường (bỏ trống, đánh dấu)?

**Đầu vào:** văn bản nguồn + danh sách trường cần lấy (bắt buộc).
**Quy trình:** xác định trường & quy tắc → bóc tách từng bản ghi → chuẩn hóa định dạng → đánh dấu trường thiếu `[trống]` → xuất bảng.
**Đầu ra mẫu:**
```
DỮ LIỆU CHUẨN HÓA — <nguồn>
| # | Trường 1 | Trường 2 | Trường 3 | Ghi chú |
|---|----------|----------|----------|---------|
Bản ghi thiếu thông tin: <liệt kê để bổ sung>
```
**Bảng kiểm:** đúng trường yêu cầu; định dạng thống nhất; đánh dấu chỗ thiếu; không bịa dữ liệu.
**Guardrails:** không tự suy đoán giá trị thiếu; nhắc bảo mật thông tin cá nhân (SĐT, email, CMND).

## 🧭 Điều phối Sub-Agent theo ngành của bạn
Buổi này agent giữ **nền "thu thập & chuẩn hóa thông tin"** nhưng thích ứng theo ngành của bạn. **Công thức:** đầu ra đúng = nền × bối cảnh ngành của bạn × form/dữ liệu bạn đưa.
Agent điều phối 5 vai (chạy song song nếu có công cụ, hoặc "đổi mũ" tuần tự trong chat):
🔎 **Researcher bối cảnh** (dựng gói ngành: thuật ngữ · chỉ số · khung · chuẩn mực · rủi ro · câu hỏi điển hình + đọc form/dữ liệu bạn gửi) → 🧠 **Phương pháp nền** → 🔗 **Tổng hợp** (nền×ngành×form, xin xác nhận) → 🛠️ **Thực thi** theo form của bạn → ✅ **Kiểm định** (rà bảng kiểm + chuẩn ngành, nêu giả định, không bịa).
**Cùng nền, khác ngành:** **Sale** (gom thông tin lead từ nhiều kênh về một bảng CRM); **Nhân sự** (chuẩn hóa hồ sơ ứng viên từ email/form); **Sự kiện/Đào tạo** (chuẩn hóa danh sách đăng ký học viên).
**Nếu bạn đưa form/template/dữ liệu → đầu ra khớp đúng form đó.**
## 🧠 SKILL.md
```yaml
name: agent-thu-thap-thong-tin
description: |
  Bóc tách và chuẩn hóa thông tin từ văn bản tự do (form, ghi chú, tin nhắn) thành bảng/cấu trúc thống nhất theo trường yêu cầu. Trigger: "thu thập thông tin", "chuẩn hóa dữ liệu từ ghi chú", "bóc trường từ form", "gom thông tin thành bảng".
```
**Mẫu câu lệnh khởi động:**
```
Trước khi làm: hỏi tôi 4–6 câu (bộ phận, nguồn, trường cần lấy, định dạng ra, quy tắc chuẩn hóa), rồi bóc tách.
Chuẩn hóa thông tin sau thành bảng. Trường cần lấy: [Tên, SĐT, Nhu cầu, Ngày]. Định dạng: [bảng/CSV].
--- NGUỒN ---
[dán văn bản/ghi chú]
```

## 👣 Diễn tiến 45 phút
| Phút | Hoạt động |
|---|---|
| 0–5 | Bài toán: thông tin mỗi người ghi một kiểu |
| 5–15 | Làm mẫu: 5 tin nhắn đăng ký → bảng chuẩn |
| 15–35 | Học viên chuẩn hóa nguồn thông tin của mình |
| 35–40 | Lỗi hay gặp: tự đoán trường thiếu |
| 40–45 | Bài tập: lưu agent + chuẩn hóa 1 nguồn thật |

## 📝 Bài tập về nhà
Chuẩn hóa một tập ghi chú/tin nhắn thành bảng; giữ mẫu trường để tái dùng.

## ✅ Tiêu chí đạt & Đo hiệu quả
- **Đạt khi:** đúng trường, định dạng thống nhất, đánh dấu chỗ thiếu.
- **Đo trước/sau:** thời gian tổng hợp thông tin; số bản ghi sai định dạng.

## 🔗 Liên kết
Đầu ra → Phân loại nội dung (Ngày 17) và Xử lý bảng tính (Ngày 06). Là bước "đầu vào" của Workspace.
