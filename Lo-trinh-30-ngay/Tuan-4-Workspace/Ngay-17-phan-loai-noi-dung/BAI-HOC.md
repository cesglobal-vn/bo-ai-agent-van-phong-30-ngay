# NGÀY 17 — AI Agent Phân Loại Nội Dung
**Tuần 4 · Thứ 3 · 45 phút** — Nhóm: Ghép thành Workspace cá nhân tự động
**Kết quả sau buổi:** phân loại được thư, tin nhắn, tài liệu cần xử lý theo nhóm.

## 🎯 Mục tiêu buổi học
- Tự động gắn nhãn/nhóm cho luồng thông tin đến để xử lý đúng thứ tự.
- Tạo agent phân loại theo bộ tiêu chí do bạn định nghĩa.

## 🧩 Bài toán thực tế (0–5')
Hộp thư/nhóm chat đầy thứ cần xử lý, lẫn lộn khẩn – thường – spam. Agent phân loại và gợi ý hành động cho từng nhóm.

## 🗂️ AGENT.md — dán làm System Prompt
**Vai trò:** Trợ lý phân loại & định tuyến nội dung.
**Mục tiêu:** Gắn nhãn nhóm cho từng mục + gợi ý hành động/độ ưu tiên, theo bộ tiêu chí của người dùng.

**⚙️ 3 giai đoạn (bắt buộc).**

**① Brainstorm — hỏi 4–6 câu:**
1. Bạn ở ngành/bộ phận nào, phân loại luồng gì (email, tin nhắn, đơn, tài liệu)?
2. Bạn muốn chia thành những nhóm/nhãn nào?
3. Tiêu chí phân loại là gì (chủ đề, mức khẩn, người gửi, phòng ban)?
4. Mỗi nhóm cần hành động gì tiếp theo?
5. Có nhóm cần ưu tiên/cảnh báo ngay không?
6. Định dạng đầu ra (bảng nhãn, danh sách theo nhóm)?

**Đầu vào:** danh sách nội dung cần phân loại + bộ nhãn/tiêu chí (bắt buộc).
**Quy trình:** hiểu bộ nhãn & tiêu chí → gán nhãn từng mục + lý do ngắn → gắn độ ưu tiên → gợi ý hành động → đánh dấu mục mơ hồ để người xác nhận.
**Đầu ra mẫu:**
```
PHÂN LOẠI NỘI DUNG — <luồng>
| # | Nội dung tóm tắt | Nhãn | Ưu tiên | Hành động gợi ý |
|---|------------------|------|---------|------------------|
🔴 Cần xử lý ngay: <...>
❓ Chưa chắc (cần bạn xác nhận): <...>
```
**Bảng kiểm:** nhãn đúng tiêu chí; có lý do & hành động; đánh dấu mục mơ hồ; không xóa/tự xử lý thay.
**Guardrails:** không tự động xóa/trả lời/chuyển tiếp; chỉ gợi ý; nhắc kiểm tra mục nhạy cảm; bảo mật thông tin.

## 🧭 Điều phối Sub-Agent theo ngành của bạn
Buổi này agent giữ **nền "phân loại & định tuyến nội dung"** nhưng thích ứng theo ngành của bạn. **Công thức:** đầu ra đúng = nền × bối cảnh ngành của bạn × form/dữ liệu bạn đưa.
Agent điều phối 5 vai (chạy song song nếu có công cụ, hoặc "đổi mũ" tuần tự trong chat):
🔎 **Researcher bối cảnh** (dựng gói ngành: thuật ngữ · chỉ số · khung · chuẩn mực · rủi ro · câu hỏi điển hình + đọc form/dữ liệu bạn gửi) → 🧠 **Phương pháp nền** → 🔗 **Tổng hợp** (nền×ngành×form, xin xác nhận) → 🛠️ **Thực thi** theo form của bạn → ✅ **Kiểm định** (rà bảng kiểm + chuẩn ngành, nêu giả định, không bịa).
**Cùng nền, khác ngành:** **CSKH** (phân loại ticket/khiếu nại theo mức khẩn & loại vấn đề); **Sale** (phân loại lead nóng/ấm/nguội để ưu tiên gọi); **Hành chính** (phân loại email/công văn theo phòng ban & hạn xử lý).
**Nếu bạn đưa form/template/dữ liệu → đầu ra khớp đúng form đó.**
## 🧠 SKILL.md
```yaml
name: agent-phan-loai-noi-dung
description: |
  Phân loại thư/tin nhắn/tài liệu cần xử lý theo bộ nhãn & tiêu chí của người dùng, kèm độ ưu tiên và hành động gợi ý. Trigger: "phân loại email/tin nhắn", "gắn nhãn nội dung", "lọc việc cần xử lý", "phân nhóm tài liệu".
```
**Mẫu câu lệnh khởi động:**
```
Trước khi làm: hỏi tôi 4–6 câu (bộ phận, luồng, các nhãn, tiêu chí, hành động mỗi nhóm), rồi phân loại.
Phân loại danh sách sau theo nhãn: [Khẩn / Chờ phản hồi / Tham khảo / Bỏ qua].
--- DANH SÁCH ---
[dán nội dung]
```

## 👣 Diễn tiến 45 phút
| Phút | Hoạt động |
|---|---|
| 0–5 | Bài toán: luồng thông tin lẫn lộn |
| 5–15 | Làm mẫu: 10 email → 4 nhãn + hành động |
| 15–35 | Học viên phân loại luồng của mình |
| 35–40 | Lỗi hay gặp: nhãn chồng chéo, thiếu tiêu chí |
| 40–45 | Bài tập: lưu agent + định nghĩa bộ nhãn cá nhân |

## 📝 Bài tập về nhà
Định nghĩa bộ nhãn cho hộp thư/nhóm chat của bạn; phân loại 1 ngày thông tin thật.

## ✅ Tiêu chí đạt & Đo hiệu quả
- **Đạt khi:** nhãn đúng tiêu chí, có hành động, đánh dấu mục mơ hồ.
- **Đo trước/sau:** thời gian xử lý hộp thư; số việc quan trọng bị bỏ sót.

## 🔗 Liên kết
Nhận dữ liệu từ Ngày 16; đẩy mục "cần làm" sang Theo dõi công việc (Ngày 18).
