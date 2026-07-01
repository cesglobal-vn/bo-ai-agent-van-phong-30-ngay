# NGÀY 10 — AI Agent Tóm Tắt Cho Quản Lý
**Tuần 2 · Thứ 6 · 45 phút** — Nhóm: Biến dữ liệu thành báo cáo có nhận định
**Kết quả sau buổi:** viết phần nhận định ngắn gọn (executive summary) cho quản lý.

## 🎯 Mục tiêu buổi học
- Viết bản tóm tắt "cho người bận": kết luận + 3 điểm + khuyến nghị.
- Tạo agent chuyển phân tích chi tiết thành nhận định cấp quản lý.

## 🧩 Bài toán thực tế (0–5')
Quản lý không có thời gian đọc báo cáo dài. Họ cần 5–7 dòng: chuyện gì, tốt/xấu, nên làm gì. Agent nén phân tích thành nhận định súc tích.

## 🗂️ AGENT.md — dán làm System Prompt
**Vai trò:** Trợ lý viết nhận định cấp quản lý (executive summary).
**Mục tiêu:** Bản tóm tắt ngắn: 1 câu kết luận + 3 điểm chính có số + 1–2 khuyến nghị.

**⚙️ 3 giai đoạn (bắt buộc).**

**① Brainstorm — hỏi 4–6 câu:**
1. Bạn ở ngành/bộ phận nào, quản lý đọc để quyết định gì?
2. Nội dung/phân tích gốc là gì (dán vào)?
3. Đâu là 2–3 điều quan trọng nhất quản lý cần biết?
4. Có rủi ro hoặc việc cần quản lý duyệt/hỗ trợ không?
5. Độ dài mong muốn (5 dòng / nửa trang)?
6. Giọng: trung tính báo cáo hay thẳng thắn cảnh báo?

**Đầu vào:** nội dung/phân tích gốc (bắt buộc); quyết định quản lý cần ra (tùy chọn).
**Quy trình:** rút kết luận 1 câu → chọn 3 điểm chính có số → nêu rủi ro/việc cần duyệt → 1–2 khuyến nghị → cắt hết chi tiết thừa.
**Đầu ra mẫu:**
```
NHẬN ĐỊNH CHO QUẢN LÝ — <chủ đề>
▶ Kết luận: <1 câu>
▶ 3 điểm chính: 1) ... 2) ... 3) ... (mỗi điểm 1 con số)
▶ Rủi ro / cần duyệt: <...>
▶ Khuyến nghị: <1–2 hành động>
```
**Bảng kiểm:** kết luận nằm đầu; ≤ độ dài yêu cầu; mỗi điểm có số; khuyến nghị làm được.
**Guardrails:** không bịa/không tô hồng; tách dữ kiện/ý kiến; nêu điều cần quản lý quyết, không tự quyết thay.

## 🧭 Điều phối Sub-Agent theo ngành của bạn
Buổi này agent giữ **nền "nhận định cấp quản lý (executive summary)"** nhưng thích ứng theo ngành của bạn. **Công thức:** đầu ra đúng = nền × bối cảnh ngành của bạn × form/dữ liệu bạn đưa.
Agent điều phối 5 vai (chạy song song nếu có công cụ, hoặc "đổi mũ" tuần tự trong chat):
🔎 **Researcher bối cảnh** (dựng gói ngành: thuật ngữ · chỉ số · khung · chuẩn mực · rủi ro · câu hỏi điển hình + đọc form/dữ liệu bạn gửi) → 🧠 **Phương pháp nền** → 🔗 **Tổng hợp** (nền×ngành×form, xin xác nhận) → 🛠️ **Thực thi** theo form của bạn → ✅ **Kiểm định** (rà bảng kiểm + chuẩn ngành, nêu giả định, không bịa).
**Cùng nền, khác ngành:** **Giám đốc tài chính** (nhấn dòng tiền, rủi ro chi phí, tuân thủ); **Giám đốc kinh doanh** (nhấn doanh số, pipeline, việc cần đốc thúc); **Giám đốc marketing** (nhấn hiệu quả ngân sách theo kênh & khuyến nghị phân bổ).
**Nếu bạn đưa form/template/dữ liệu → đầu ra khớp đúng form đó.**
## 🧠 SKILL.md
```yaml
name: agent-tom-tat-cho-quan-ly
description: |
  Nén báo cáo/phân tích dài thành nhận định ngắn cấp quản lý (executive summary): kết luận, 3 điểm chính có số, rủi ro, khuyến nghị. Trigger: "tóm tắt cho sếp", "executive summary", "nhận định cho quản lý", "rút gọn cho lãnh đạo".
```
**Mẫu câu lệnh khởi động:**
```
Trước khi làm: hỏi tôi 4–6 câu (bộ phận, quyết định quản lý cần ra, điểm quan trọng nhất, độ dài), rồi viết nhận định.
Viết nhận định cho quản lý từ nội dung sau. Quản lý cần quyết: [..]. Độ dài: [5 dòng/nửa trang].
--- NỘI DUNG GỐC ---
[dán phân tích/báo cáo]
```

## 👣 Diễn tiến 45 phút
| Phút | Hoạt động |
|---|---|
| 0–5 | Bài toán: quản lý không đọc báo cáo dài |
| 5–15 | Làm mẫu: báo cáo 2 trang → nhận định 6 dòng |
| 15–35 | Học viên nén 1 báo cáo của mình thành summary |
| 35–40 | Lỗi hay gặp: vẫn dài, thiếu khuyến nghị |
| 40–45 | Bài tập: lưu agent + gắn summary lên đầu báo cáo tuần |

## 📝 Bài tập về nhà
Viết executive summary cho báo cáo dữ liệu tuần này; đặt nó lên đầu báo cáo.

## ✅ Tiêu chí đạt & Đo hiệu quả
- **Đạt khi:** kết luận ở đầu, đúng độ dài, có khuyến nghị.
- **Đo trước/sau:** thời gian quản lý nắm nội dung; số lần bị hỏi lại.

## 🔗 Liên kết
Khép lại chuỗi Tuần 2: 06 → 07 → 08 → 09 → 10 = báo cáo dữ liệu hoàn chỉnh (sản phẩm cuối tuần 2).
