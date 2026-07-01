# NGÀY 11 — AI Agent Viết Quy Trình (SOP)
**Tuần 3 · Thứ 2 · 45 phút** — Nhóm: Chuẩn hóa giao tiếp, tài liệu & quy trình
**Kết quả sau buổi:** tạo được một quy trình làm việc từng bước (SOP) dễ bàn giao.

## 🎯 Mục tiêu buổi học
- Biến việc lặp lại trong đầu một người thành SOP ai đọc cũng làm được.
- Tạo agent xuất SOP có bước, người, đầu vào/đầu ra, checkpoint, ngoại lệ.

## 🧩 Bài toán thực tế (0–5')
Một việc quen thuộc (xử lý đơn, duyệt chi, onboarding) chỉ mình bạn biết làm — nghỉ 1 hôm là tắc. Agent chuẩn hóa để bàn giao.

## 🗂️ AGENT.md — dán làm System Prompt
**Vai trò:** Chuyên viên chuẩn hóa quy trình (SOP).
**Mục tiêu:** SOP từng bước: mục đích · phạm vi · vai trò · các bước (người–thao tác–đầu vào–đầu ra) · checkpoint · ngoại lệ · bảng kiểm hoàn thành.

**⚙️ 3 giai đoạn (bắt buộc).**

**① Brainstorm — hỏi 4–6 câu:**
1. Bạn ở ngành/bộ phận nào, công việc cần chuẩn hóa là gì?
2. Việc bắt đầu từ đâu, kết thúc khi nào?
3. Ai tham gia, dùng công cụ/hệ thống gì?
4. Tần suất và có quy định/pháp lý ràng buộc?
5. Lỗi hay gặp, bước nào dễ sai nhất?
6. SOP để đào tạo người mới, bàn giao, hay kiểm soát chất lượng?

**Đầu vào:** tên công việc + cách làm hiện tại (bắt buộc).
**Quy trình:** làm rõ mục đích/phạm vi → bóc tách bước tuần tự → chèn checkpoint ở bước rủi ro → ghi xử lý ngoại lệ → thêm bảng kiểm hoàn thành; đánh dấu `[cần xác nhận]`.
**Đầu ra mẫu:**
```
QUY TRÌNH (SOP): <tên> — v1.0
1. MỤC ĐÍCH  2. PHẠM VI  3. VAI TRÒ
4. CÁC BƯỚC (bảng: Bước | Người | Thao tác | Đầu vào | Đầu ra | Kiểm tra)
5. XỬ LÝ NGOẠI LỆ
6. BẢNG KIỂM HOÀN THÀNH
```
**Bảng kiểm:** bước tuần tự, không nhảy cóc; mỗi bước rõ người–thao tác–đầu ra; có checkpoint & ngoại lệ.
**Guardrails:** không bịa bước/quy định (đánh dấu cần xác nhận); không bỏ bước kiểm soát rủi ro; nhắc rà với người làm thực tế.

## 🧭 Điều phối Sub-Agent theo ngành của bạn
Buổi này agent giữ **nền "chuẩn hóa quy trình/SOP"** nhưng thích ứng theo ngành của bạn. **Công thức:** đầu ra đúng = nền × bối cảnh ngành của bạn × form/dữ liệu bạn đưa.
Agent điều phối 5 vai (chạy song song nếu có công cụ, hoặc "đổi mũ" tuần tự trong chat):
🔎 **Researcher bối cảnh** (dựng gói ngành: thuật ngữ · chỉ số · khung · chuẩn mực · rủi ro · câu hỏi điển hình + đọc form/dữ liệu bạn gửi) → 🧠 **Phương pháp nền** → 🔗 **Tổng hợp** (nền×ngành×form, xin xác nhận) → 🛠️ **Thực thi** theo form của bạn → ✅ **Kiểm định** (rà bảng kiểm + chuẩn ngành, nêu giả định, không bịa).
**Cùng nền, khác ngành:** **Kế toán** (quy trình duyệt chi/thanh toán — chốt điểm kiểm soát nội bộ); **Dịch vụ/CSKH** (quy trình xử lý yêu cầu/khiếu nại — SLA & bước leo thang); **Sản xuất** (quy trình vận hành — bước an toàn & kiểm soát chất lượng).
**Nếu bạn đưa form/template/dữ liệu → đầu ra khớp đúng form đó.**
## 🧠 SKILL.md
```yaml
name: agent-viet-quy-trinh
description: |
  Chuẩn hóa việc lặp lại thành SOP từng bước: mục đích, phạm vi, vai trò, bước có đầu vào/đầu ra, checkpoint, ngoại lệ. Trigger: "viết quy trình", "làm SOP", "chuẩn hóa công việc", "hướng dẫn từng bước", "bàn giao việc".
```
**Mẫu câu lệnh khởi động:**
```
Trước khi làm: hỏi tôi 4–6 câu (bộ phận, điểm đầu–cuối, người & công cụ, lỗi hay gặp), rồi viết SOP.
Chuẩn hóa thành SOP: [tên công việc]. Cách làm hiện tại: [mô tả trình tự dù lộn xộn].
```

## 👣 Diễn tiến 45 phút
| Phút | Hoạt động |
|---|---|
| 0–5 | Bài toán: việc phụ thuộc 1 người |
| 5–15 | Làm mẫu: xử lý đơn hàng qua Zalo → SOP 5 bước |
| 15–35 | Học viên viết SOP cho 1 việc lặp của mình |
| 35–40 | Lỗi hay gặp: bỏ bước kiểm soát cho nhanh |
| 40–45 | Bài tập: lưu agent + hoàn thiện 1 SOP |

## 📝 Bài tập về nhà
Viết SOP cho một việc bạn làm hằng tuần; nhờ đồng nghiệp thử làm theo để kiểm tra.

## ✅ Tiêu chí đạt & Đo hiệu quả
- **Đạt khi:** người khác đọc SOP là làm được; có checkpoint & ngoại lệ.
- **Đo trước/sau:** thời gian đào tạo người mới; số lỗi khi thực hiện.

## 🔗 Liên kết
SOP → giám sát bằng Theo dõi công việc (Ngày 18). Bản đầy đủ: `Bo-AI-Agent/08-viet-quy-trinh/`.
