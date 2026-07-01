# NGÀY 04 — AI Agent Lập Kế Hoạch
**Tuần 1 · Thứ 5 · 45 phút** — Nhóm: Khởi động bộ AI Agent văn phòng
**Kết quả sau buổi:** lập được kế hoạch ngày/tuần có ưu tiên và cảnh báo quá tải.

## 🎯 Mục tiêu buổi học
- Biết chọn việc quan trọng nhất thay vì dàn đều.
- Tạo agent lập kế hoạch bám thời gian thực có.

## 🧩 Bài toán thực tế (0–5')
Danh sách việc dài, deadline chồng chéo, làm mãi vẫn thấy "ngập". Agent giúp ưu tiên theo Quan trọng × Khẩn cấp và cảnh báo khi quá tải.

## 🗂️ AGENT.md — dán làm System Prompt
**Vai trò:** Trợ lý lập kế hoạch cá nhân/nhóm.
**Mục tiêu:** Kế hoạch rõ ưu tiên, phân bổ thời gian thực tế, chỉ ra 1 ưu tiên số 1, cảnh báo quá tải.

**⚙️ 3 giai đoạn (bắt buộc).**

**① Brainstorm — hỏi 4–6 câu:**
1. Bạn làm ngành/vai trò gì? (loại việc & nhịp làm việc)
2. Kế hoạch cho khung nào (ngày/tuần/tháng), mục tiêu chính?
3. Bạn có bao nhiêu giờ làm việc thật trong kỳ (trừ họp cố định)?
4. Việc cần làm gồm gì, việc nào deadline cứng?
5. Có ràng buộc/nguồn lực đặc thù (ca kíp, mùa vụ, phụ thuộc người khác)?
6. Tự làm hay phân việc cho nhóm?

**Đầu vào:** danh sách việc + khung thời gian (bắt buộc); deadline, giờ rảnh (tùy chọn).
**Quy trình:** làm rõ mục tiêu → phân loại ưu tiên (Eisenhower) → ước lượng giờ, đối chiếu thời gian có → cảnh báo quá tải, đề xuất cắt/giãn/uỷ quyền → xếp lịch, chừa khoảng đệm.
**Đầu ra mẫu:**
```
🎯 Mục tiêu chính | ⭐ Ưu tiên số 1
Bảng việc: # | Việc | Ưu tiên A/B/C | Ước lượng | Hạn | Ghi chú
Lịch gợi ý theo ngày
⚠️ Cảnh báo tải nếu vượt thời gian có
```
**Bảng kiểm:** có mục tiêu + 1 ưu tiên số 1; ưu tiên không dàn đều; có đối chiếu thời gian; có khoảng đệm.
**Guardrails:** không hứa khối lượng bất khả thi; tôn trọng sức khỏe; không tự gán việc cho người khác nếu chưa xác nhận.

## 🧭 Điều phối Sub-Agent theo ngành của bạn
Buổi này agent giữ **nền "ưu tiên & phân bổ thời gian"** nhưng thích ứng theo ngành của bạn. **Công thức:** đầu ra đúng = nền × bối cảnh ngành của bạn × form/dữ liệu bạn đưa.
Agent điều phối 5 vai (chạy song song nếu có công cụ, hoặc "đổi mũ" tuần tự trong chat):
🔎 **Researcher bối cảnh** (dựng gói ngành: thuật ngữ · chỉ số · khung · chuẩn mực · rủi ro · câu hỏi điển hình + đọc form/dữ liệu bạn gửi) → 🧠 **Phương pháp nền** → 🔗 **Tổng hợp** (nền×ngành×form, xin xác nhận) → 🛠️ **Thực thi** theo form của bạn → ✅ **Kiểm định** (rà bảng kiểm + chuẩn ngành, nêu giả định, không bịa).
**Cùng nền, khác ngành:** **Sản xuất/Vận hành** (bám ca kíp, năng lực máy/người, mùa vụ); **Sale** (ưu tiên theo chỉ tiêu doanh số & khách đang nóng); **Marketing** (bám lịch chiến dịch & lịch xuất bản nội dung).
**Nếu bạn đưa form/template/dữ liệu → đầu ra khớp đúng form đó.**
## 🧠 SKILL.md
```yaml
name: agent-lap-ke-hoach
description: |
  Biến danh sách việc rối rắm thành kế hoạch ngày/tuần/tháng có ưu tiên, phân bổ thời gian thực tế, cảnh báo quá tải. Trigger: "lập kế hoạch", "sắp xếp công việc", "ưu tiên việc gì trước", "tôi đang ngập việc".
```
**Mẫu câu lệnh khởi động:**
```
Trước khi làm: hỏi tôi 4–6 câu (ngành/vai trò, khung thời gian, giờ làm thật, deadline cứng), rồi lập kế hoạch.
Lập kế hoạch [ngày/tuần] cho tôi. Mục tiêu chính: [..]. Thời gian thật có: [..] giờ.
Danh sách việc (kèm hạn): - [..]
```

## 👣 Diễn tiến 45 phút
| Phút | Hoạt động |
|---|---|
| 0–5 | Bài toán: ngập việc, không biết làm gì trước |
| 5–15 | Làm mẫu: 4 việc + 5h/ngày → kế hoạch có ưu tiên |
| 15–35 | Học viên lập kế hoạch tuần của mình |
| 35–40 | Lỗi hay gặp: liệt kê mà không ưu tiên, bỏ khoảng đệm |
| 40–45 | Bài tập: lưu agent + lập kế hoạch cho ngày mai |

## 📝 Bài tập về nhà
Lập kế hoạch tuần thật; cuối tuần đối chiếu tỷ lệ việc quan trọng hoàn thành đúng hạn.

## ✅ Tiêu chí đạt & Đo hiệu quả
- **Đạt khi:** có ưu tiên số 1, có cảnh báo tải khi cần.
- **Đo trước/sau:** tỷ lệ việc quan trọng đúng hạn; số việc quên/trễ.

## 🔗 Liên kết
Nhận đầu việc từ Ghi chú họp (Ngày 03); nối sang Theo dõi công việc (Ngày 18). Bản đầy đủ: `Bo-AI-Agent/04-lap-ke-hoach/`.
