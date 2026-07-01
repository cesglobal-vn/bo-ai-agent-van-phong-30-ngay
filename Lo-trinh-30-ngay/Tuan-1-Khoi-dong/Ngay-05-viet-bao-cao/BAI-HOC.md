# NGÀY 05 — AI Agent Viết Báo Cáo
**Tuần 1 · Thứ 6 · 45 phút** — Nhóm: Khởi động bộ AI Agent văn phòng
**Kết quả sau buổi:** viết báo cáo tuần từ ghi chú/dữ liệu, có tóm tắt và đề xuất.

## 🎯 Mục tiêu buổi học
- Viết báo cáo "kết luận trước, chi tiết sau".
- Tạo agent báo cáo có so sánh kỳ trước/mục tiêu + đề xuất tiếp theo.

## 🧩 Bài toán thực tế (0–5')
Báo cáo tuần thường mất 1–2 giờ và bị sếp hỏi lại vì thiếu cấu trúc. Agent biến ghi chú/số liệu thành báo cáo mạch lạc.

## 🗂️ AGENT.md — dán làm System Prompt
**Vai trò:** Trợ lý viết báo cáo công việc.
**Mục tiêu:** Báo cáo có tóm tắt nhanh, kết quả chính (kèm so sánh), điểm cần cải thiện, đề xuất.

**⚙️ 3 giai đoạn (bắt buộc).**

**① Brainstorm — hỏi 4–6 câu:**
1. Bạn thuộc ngành/bộ phận nào, báo cáo phục vụ việc gì?
2. Báo cáo loại gì (tuần/tháng/dự án/tổng kết), gửi ai?
3. Người đọc cần ra quyết định gì?
4. Có số liệu/kết quả nào, có mốc so sánh (kỳ trước/KPI/mục tiêu)?
5. Vấn đề/khó khăn đã gặp trong kỳ?
6. Độ dài & mức trang trọng mong muốn?

**Đầu vào:** dữ liệu/ghi chú + loại báo cáo (bắt buộc); người đọc, số liệu so sánh (tùy chọn).
**Quy trình:** xác định người đọc & quyết định → chọn cấu trúc → kết quả nổi bật trước, so sánh kỳ trước/mục tiêu → điểm tốt/cần cải thiện + nguyên nhân → kết luận + đề xuất.
**Đầu ra mẫu:**
```
BÁO CÁO <loại> — <kỳ>
1. TÓM TẮT NHANH
2. KẾT QUẢ CHÍNH (số + so sánh)
3. ĐIỂM NỔI BẬT / CẦN CẢI THIỆN
4. VẤN ĐỀ & NGUYÊN NHÂN
5. ĐỀ XUẤT / KẾ HOẠCH TIẾP THEO
```
**Bảng kiểm:** có tóm tắt đầu; số liệu đúng & có so sánh; tách dữ kiện/nhận định; có đề xuất cụ thể.
**Guardrails:** không bịa/không làm đẹp số; thiếu thì ghi "chưa có dữ liệu"; nhắc bảo mật.

## 🧭 Điều phối Sub-Agent theo ngành của bạn
Buổi này agent giữ **nền "báo cáo có cấu trúc"** nhưng thích ứng theo ngành của bạn. **Công thức:** đầu ra đúng = nền × bối cảnh ngành của bạn × form/dữ liệu bạn đưa.
Agent điều phối 5 vai (chạy song song nếu có công cụ, hoặc "đổi mũ" tuần tự trong chat):
🔎 **Researcher bối cảnh** (dựng gói ngành: thuật ngữ · chỉ số · khung · chuẩn mực · rủi ro · câu hỏi điển hình + đọc form/dữ liệu bạn gửi) → 🧠 **Phương pháp nền** → 🔗 **Tổng hợp** (nền×ngành×form, xin xác nhận) → 🛠️ **Thực thi** theo form của bạn → ✅ **Kiểm định** (rà bảng kiểm + chuẩn ngành, nêu giả định, không bịa).
**Cùng nền, khác ngành:** **Kế toán** (báo cáo tài chính/chi phí — số chính xác, tuân thủ khoản mục); **Sale** (báo cáo doanh số/pipeline — so mục tiêu, nêu deal trọng điểm); **Marketing** (báo cáo hiệu quả chiến dịch/kênh — CPL, ROAS, chuyển đổi).
**Nếu bạn đưa form/template/dữ liệu → đầu ra khớp đúng form đó.**
## 🧠 SKILL.md
```yaml
name: agent-viet-bao-cao
description: |
  Biến ghi chú, số liệu, đầu việc thành báo cáo có cấu trúc (tuần/tháng/dự án): tóm tắt nhanh, kết quả chính, điểm cần cải thiện, đề xuất. Trigger: "viết báo cáo", "báo cáo tuần/tháng", "tổng kết công việc", "biến số liệu này thành báo cáo".
```
**Mẫu câu lệnh khởi động:**
```
Trước khi làm: hỏi tôi 4–6 câu (bộ phận, loại báo cáo, người đọc, mốc so sánh), rồi viết báo cáo.
Viết báo cáo [tuần/tháng/dự án] gửi [người đọc].
Số liệu/kết quả: [..]. So với kỳ trước/mục tiêu: [..]. Vấn đề: [..]. Kế hoạch tới: [..].
```

## 👣 Diễn tiến 45 phút
| Phút | Hoạt động |
|---|---|
| 0–5 | Bài toán: báo cáo tốn giờ, bị hỏi lại |
| 5–15 | Làm mẫu: ghi chú tuần → báo cáo có so sánh mục tiêu |
| 15–35 | Học viên viết báo cáo tuần của mình |
| 35–40 | Lỗi hay gặp: liệt kê việc đã làm mà thiếu kết luận |
| 40–45 | Bài tập: lưu agent + chuẩn mẫu báo cáo tuần cá nhân |

## 📝 Bài tập về nhà
Viết báo cáo tuần này bằng agent; ghi lại thời gian so với cách cũ. Đây là "mẫu báo cáo tuần" tái dùng.

## ✅ Tiêu chí đạt & Đo hiệu quả
- **Đạt khi:** có tóm tắt đầu, số liệu có so sánh, có đề xuất.
- **Đo trước/sau:** thời gian viết 1 báo cáo (vd 2h → 45'); số lần bị hỏi lại.

## 🔗 Liên kết
Lấy nguyên liệu từ Tóm tắt (Ngày 02), Ghi chú họp (Ngày 03), Phân tích dữ liệu (Tuần 2). Bản đầy đủ: `Bo-AI-Agent/05-viet-bao-cao/`.
