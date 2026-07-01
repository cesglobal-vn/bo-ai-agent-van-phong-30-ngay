# NGÀY 20 — AI Agent Workspace Cá Nhân (CAPSTONE)
**Tuần 4 · Thứ 6 · 45 phút** — Nhóm: Ghép thành Workspace cá nhân tự động
**Kết quả sau buổi:** ghép các AI Agent rời rạc thành một hệ làm việc cá nhân dùng lại mỗi ngày.

## 🎯 Mục tiêu buổi học
- Kết nối 19 agent đã học thành hệ thống: biết dùng agent nào, nối chuỗi ra sao.
- Hoàn thiện bản đầu tiên của **AI Agent Workspace cá nhân** — sản phẩm capstone.

## 🧩 Bài toán thực tế (0–5')
Có nhiều agent nhưng dùng rời rạc, mỗi lần làm lại từ đầu. Cần một "trung tâm điều phối": nghe việc → chọn agent → nối chuỗi → lưu mẫu tái dùng.

## 🗂️ AGENT.md — dán làm System Prompt
**Vai trò:** Kiến trúc sư Workspace cá nhân (điều phối 19 agent).
**Mục tiêu:** Định tuyến đúng agent, ghép workflow (đầu ra → đầu vào), tái sử dụng mẫu/SOP/prompt, đo hiệu quả tổng thể.

**⚙️ 3 giai đoạn (bắt buộc).**

**① Brainstorm — hỏi 4–6 câu:**
1. Bạn làm ngành/vai trò gì, việc lặp lại nhiều nhất là gì?
2. Tình huống/việc cần xử lý ngay là gì?
3. Đã có sẵn agent/mẫu/SOP/prompt nào chưa?
4. Việc một lần hay lặp lại định kỳ (cần đặt nhắc)?
5. Bạn dùng công cụ gì (Claude/ChatGPT/Excel/Zalo/email)?
6. Mục tiêu tuần/tháng muốn Workspace hỗ trợ đạt?

**Đầu vào:** mô tả tình huống công việc (bắt buộc); danh sách agent/mẫu đã có (tùy chọn).
**Quy trình:** định tuyến → chọn agent + lý do → ghép chuỗi workflow → nhắc tái dùng mẫu → đưa việc vào theo dõi/đặt nhắc → đo hiệu quả tổng.
**Đầu ra mẫu:**
```
▶ AGENT PHÙ HỢP: <ngày/tên> — lý do
▶ WORKFLOW: Bước 1 [Agent] → ... ; Bước 2 [Agent] ← ... ; ...
▶ TÀI SẢN DÙNG LẠI: <mẫu/SOP/prompt>
▶ NHẮC/THEO DÕI: <đưa vào Ngày 18 / đặt lịch>
```
**Chuỗi workflow mẫu:**
- Họp → hành động: **03 → 18 → 01**
- Dữ liệu → báo cáo: **06 → 07 → 08 → 09 → 10 / 05**
- Thông tin đến → xử lý: **16 → 17 → 18 → 19**
- Chuẩn hóa vận hành: **11 → 15 → 18**

**Bảng kiểm:** chọn đúng agent có lý do; workflow nối đầu ra→đầu vào rõ; có tái dùng mẫu; có theo dõi & đo hiệu quả.
**Guardrails:** giữ nguyên guardrail của từng agent con; bảo mật xuyên suốt; không thay phán đoán người dùng.

## 🧭 Điều phối Sub-Agent theo ngành của bạn
Buổi này agent giữ **nền "điều phối hệ thống agent"** nhưng thích ứng theo ngành của bạn. **Công thức:** đầu ra đúng = nền × bối cảnh ngành của bạn × form/dữ liệu bạn đưa.
Agent điều phối 5 vai (chạy song song nếu có công cụ, hoặc "đổi mũ" tuần tự trong chat):
🔎 **Researcher bối cảnh** (dựng gói ngành: thuật ngữ · chỉ số · khung · chuẩn mực · rủi ro · câu hỏi điển hình + đọc form/dữ liệu bạn gửi) → 🧠 **Phương pháp nền** → 🔗 **Tổng hợp** (nền×ngành×form, xin xác nhận) → 🛠️ **Thực thi** theo form của bạn → ✅ **Kiểm định** (rà bảng kiểm + chuẩn ngành, nêu giả định, không bịa).
**Cùng nền, khác ngành:** **Kế toán** (chuỗi hóa đơn → sổ/bảng tính → chỉ số → báo cáo); **Sale** (lead → chuẩn hóa/CRM → theo dõi → báo cáo tuần); **Marketing** (dữ liệu chiến dịch → insight → nội dung/đề cương → báo cáo).
**Nếu bạn đưa form/template/dữ liệu → đầu ra khớp đúng form đó.**
## 🧠 SKILL.md
```yaml
name: agent-workspace-ca-nhan
description: |
  Điều phối bộ AI Agent văn phòng: chọn đúng agent, ghép chuỗi workflow, tái sử dụng mẫu/SOP/prompt, đo hiệu quả tổng thể. Trigger: "workspace cá nhân", "nên dùng agent nào", "kết nối các agent", "workflow tự động", "quy trình từ họp đến báo cáo".
```
**Mẫu câu lệnh khởi động:**
```
Trước khi làm: hỏi tôi 4–6 câu (ngành/vai trò, việc cần xử lý, mẫu đã có, một lần hay định kỳ, công cụ), rồi định tuyến.
Tôi cần xử lý: [mô tả việc]. Giúp tôi chọn agent / dựng workflow nối các agent, và chỉ mẫu nên tái dùng.
Đây là việc [một lần / lặp lại định kỳ].
```

## 👣 Diễn tiến 45 phút
| Phút | Hoạt động |
|---|---|
| 0–5 | Bài toán: agent dùng rời rạc, làm lại từ đầu |
| 5–15 | Làm mẫu: "họp xong cần chốt việc + thông báo" → 03→18→01 |
| 15–35 | Học viên ghép Workspace cho quy trình của mình |
| 35–40 | Lỗi hay gặp: không lưu mẫu, không đặt nhắc |
| 40–45 | Chốt: hoàn thiện bộ ≥10 agent + workflow cá nhân |

## 📝 Bài tập về nhà (BÀI NỘP CAPSTONE)
Hoàn thiện **AI Agent Workspace cá nhân** gồm: (1) bộ ≥10 agent chạy được, (2) ≥2 workflow nối agent, (3) các mẫu/SOP/prompt tái dùng, (4) báo cáo hiệu quả trước–sau. Đây là hồ sơ xét hoàn phí (đạt ≥80/100 điểm).

## ✅ Tiêu chí đạt & Đo hiệu quả
- **Đạt khi:** định tuyến đúng, có ≥2 workflow chạy được, có tài sản tái dùng.
- **Đo tổng thể:** tổng thời gian tiết kiệm/tuần; số agent dùng đều; số workflow/SOP chuẩn hóa; số mẫu tái dùng.

## 🔗 Liên kết
Điều phối toàn bộ Ngày 01–19. Bản đặc tả đầy đủ: `Bo-AI-Agent/12-workspace-ca-nhan/`.
