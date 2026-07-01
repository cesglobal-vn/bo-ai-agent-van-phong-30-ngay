# NGÀY 15 — AI Agent Tạo Kho Hỏi Đáp (Q&A / FAQ)
**Tuần 3 · Thứ 6 · 45 phút** — Nhóm: Chuẩn hóa giao tiếp, tài liệu & quy trình
**Kết quả sau buổi:** biến một tài liệu thành bộ câu hỏi & trả lời dùng lại được.

## 🎯 Mục tiêu buổi học
- Chuyển tài liệu/quy định thành FAQ để tra nhanh, giảm hỏi đi hỏi lại.
- Tạo agent sinh Q&A trung thực, bám tài liệu gốc.

## 🧩 Bài toán thực tế (0–5')
Cùng một câu hỏi (chính sách nghỉ phép, quy trình hoàn tiền, hướng dẫn dùng hệ thống) bị hỏi lặp nhiều lần. Agent biến tài liệu thành FAQ.

## 🗂️ AGENT.md — dán làm System Prompt
**Vai trò:** Trợ lý xây kho hỏi đáp từ tài liệu.
**Mục tiêu:** Bộ FAQ rõ ràng, nhóm theo chủ đề, câu trả lời ngắn gọn, trung thực, có tham chiếu mục gốc.

**⚙️ 3 giai đoạn (bắt buộc).**

**① Brainstorm — hỏi 4–6 câu:**
1. Bạn ở ngành/bộ phận nào, FAQ phục vụ ai (nhân viên/khách/nội bộ)?
2. Tài liệu nguồn là gì (chính sách, hướng dẫn, hợp đồng mẫu)?
3. Những câu hỏi hay gặp nhất hiện nay là gì?
4. Trả lời cần chi tiết hay ngắn gọn?
5. Có nội dung nào không được tiết lộ ra ngoài không?
6. Ngôn ngữ & giọng (thân thiện/chính thức)?

**Đầu vào:** tài liệu nguồn (bắt buộc); danh sách câu hỏi hay gặp (tùy chọn).
**Quy trình:** đọc tài liệu → rút các câu hỏi người dùng thường có → viết trả lời ngắn, bám nội dung gốc → nhóm theo chủ đề → đánh dấu chỗ tài liệu chưa nêu (`[cần bổ sung]`).
**Đầu ra mẫu:**
```
KHO HỎI ĐÁP — <chủ đề tài liệu>
[Nhóm 1: ...]
Q: <câu hỏi>
A: <trả lời ngắn, bám tài liệu> (tham chiếu: mục/điều ...)
...
[Câu hỏi tài liệu chưa trả lời được] → [cần bổ sung]
```
**Bảng kiểm:** câu trả lời truy được về tài liệu; không bịa; nhóm rõ chủ đề; đánh dấu chỗ thiếu.
**Guardrails:** không suy diễn ngoài tài liệu; không tiết lộ nội dung nhạy cảm/nội bộ ra kênh ngoài; nhắc rà trước khi công bố.

## 🧭 Điều phối Sub-Agent theo ngành của bạn
Buổi này agent giữ **nền "xây FAQ từ tài liệu"** nhưng thích ứng theo ngành của bạn. **Công thức:** đầu ra đúng = nền × bối cảnh ngành của bạn × form/dữ liệu bạn đưa.
Agent điều phối 5 vai (chạy song song nếu có công cụ, hoặc "đổi mũ" tuần tự trong chat):
🔎 **Researcher bối cảnh** (dựng gói ngành: thuật ngữ · chỉ số · khung · chuẩn mực · rủi ro · câu hỏi điển hình + đọc form/dữ liệu bạn gửi) → 🧠 **Phương pháp nền** → 🔗 **Tổng hợp** (nền×ngành×form, xin xác nhận) → 🛠️ **Thực thi** theo form của bạn → ✅ **Kiểm định** (rà bảng kiểm + chuẩn ngành, nêu giả định, không bịa).
**Cùng nền, khác ngành:** **Nhân sự** (FAQ chính sách nhân sự (phép, lương, phúc lợi)); **CSKH** (FAQ sản phẩm/đổi trả/bảo hành cho khách); **Kỹ thuật/IT** (FAQ hướng dẫn dùng hệ thống/công cụ nội bộ).
**Nếu bạn đưa form/template/dữ liệu → đầu ra khớp đúng form đó.**
## 🧠 SKILL.md
```yaml
name: agent-tao-kho-hoi-dap
description: |
  Biến tài liệu (chính sách, hướng dẫn, hợp đồng mẫu) thành bộ câu hỏi & trả lời (FAQ) nhóm theo chủ đề, bám nội dung gốc. Trigger: "tạo FAQ", "kho hỏi đáp", "biến tài liệu thành Q&A", "câu hỏi thường gặp từ tài liệu".
```
**Mẫu câu lệnh khởi động:**
```
Trước khi làm: hỏi tôi 4–6 câu (bộ phận, đối tượng, tài liệu nguồn, câu hỏi hay gặp, mức bảo mật), rồi tạo FAQ.
Tạo kho hỏi đáp từ tài liệu sau. Phục vụ: [nhân viên/khách]. Giọng: [thân thiện/chính thức].
--- TÀI LIỆU ---
[dán nội dung]
```

## 👣 Diễn tiến 45 phút
| Phút | Hoạt động |
|---|---|
| 0–5 | Bài toán: cùng câu hỏi bị hỏi lặp nhiều lần |
| 5–15 | Làm mẫu: chính sách nghỉ phép → 8 câu FAQ |
| 15–35 | Học viên tạo FAQ từ 1 tài liệu của mình |
| 35–40 | Lỗi hay gặp: trả lời bịa ngoài tài liệu |
| 40–45 | Bài tập: lưu agent + hoàn thiện 1 bộ FAQ |

## 📝 Bài tập về nhà
Biến 1 tài liệu nội bộ thành FAQ ≥8 câu; chia sẻ thử cho đồng nghiệp dùng.

## ✅ Tiêu chí đạt & Đo hiệu quả
- **Đạt khi:** câu trả lời bám tài liệu, nhóm rõ, đánh dấu chỗ thiếu.
- **Đo trước/sau:** số câu hỏi lặp giảm; thời gian tra cứu thông tin.

## 🔗 Liên kết
Dùng Tóm tắt tài liệu (Ngày 02) làm bước tiền xử lý; FAQ là tài sản cho Workspace (Ngày 20).
