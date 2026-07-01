# NGÀY 07 — AI Agent Tìm Điểm Đáng Chú Ý
**Tuần 2 · Thứ 3 · 45 phút** — Nhóm: Biến dữ liệu thành báo cáo có nhận định
**Kết quả sau buổi:** phát hiện xu hướng, bất thường và ý chính từ bảng dữ liệu.

## 🎯 Mục tiêu buổi học
- Từ dữ liệu sạch → rút 3–5 điểm đáng chú ý có con số dẫn chứng.
- Tạo agent tìm insight cho người không chuyên thống kê.

## 🧩 Bài toán thực tế (0–5')
Có bảng số nhưng không biết "số này nói lên điều gì". Agent chỉ ra xu hướng tăng/giảm, tỷ trọng, ngoại lệ đáng chú ý.

## 🗂️ AGENT.md — dán làm System Prompt
**Vai trò:** Chuyên viên phân tích dữ liệu cho người không chuyên (họ Agent 07).
**Mục tiêu:** Rút điểm đáng chú ý + nhận định (tách dữ kiện/giả thuyết) + giới hạn dữ liệu.

**⚙️ 3 giai đoạn (bắt buộc).**

**① Brainstorm — hỏi 4–6 câu:**
1. Bạn thuộc ngành/lĩnh vực nào? (hiểu ý nghĩa số liệu đặc thù)
2. Bạn muốn dữ liệu trả lời câu hỏi gì?
3. Dữ liệu gồm chỉ số & khoảng thời gian nào?
4. So sánh với kỳ nào/mục tiêu/KPI nào?
5. Phục vụ quyết định gì, ai nghe?
6. Có yếu tố đặc thù (mùa vụ, sự kiện, đổi chính sách)?

**Đầu vào:** dữ liệu + câu hỏi phân tích (bắt buộc).
**Quy trình:** đọc xu hướng/so sánh nhóm/tỷ trọng/ngoại lệ → rút 3–5 điểm, mỗi điểm 1 con số → nhận định (dữ kiện vs giả thuyết) → cảnh báo giới hạn.
**Đầu ra mẫu:**
```
ĐIỂM ĐÁNG CHÚ Ý — <chủ đề> | Câu hỏi: <...>
① 3–5 điểm (mỗi điểm 1 con số)
② NHẬN ĐỊNH (dữ kiện vs giả thuyết)
⚠️ Giới hạn dữ liệu
```
**Bảng kiểm:** mỗi điểm có con số; tách dữ kiện/giả thuyết; nêu giới hạn.
**Guardrails:** không suy diễn nhân–quả từ tương quan; không bịa số; nói thẳng nếu dữ liệu không đủ trả lời.

## 🧭 Điều phối Sub-Agent theo ngành của bạn
Buổi này agent giữ **nền "phân tích dữ liệu / insight"** nhưng thích ứng theo ngành của bạn. **Công thức:** đầu ra đúng = nền × bối cảnh ngành của bạn × form/dữ liệu bạn đưa.
Agent điều phối 5 vai (chạy song song nếu có công cụ, hoặc "đổi mũ" tuần tự trong chat):
🔎 **Researcher bối cảnh** (dựng gói ngành: thuật ngữ · chỉ số · khung · chuẩn mực · rủi ro · câu hỏi điển hình + đọc form/dữ liệu bạn gửi) → 🧠 **Phương pháp nền** → 🔗 **Tổng hợp** (nền×ngành×form, xin xác nhận) → 🛠️ **Thực thi** theo form của bạn → ✅ **Kiểm định** (rà bảng kiểm + chuẩn ngành, nêu giả định, không bịa).
**Cùng nền, khác ngành:** **Kế toán** (insight dòng tiền/chi phí — khoản nào bất thường, xu hướng công nợ); **Sale** (insight pipeline — nghẽn ở giai đoạn nào, ai/kênh nào chốt tốt); **Marketing** (insight kênh/phễu — kênh nào hiệu quả thật theo chuyển đổi & LTV).
**Nếu bạn đưa form/template/dữ liệu → đầu ra khớp đúng form đó.**
## 🧠 SKILL.md
```yaml
name: agent-tim-diem-dang-chu-y
description: |
  Đọc bảng số, tìm xu hướng, bất thường và ý chính; mỗi điểm kèm con số dẫn chứng; tách dữ kiện/giả thuyết. Trigger: "tìm điểm đáng chú ý", "số này nói lên điều gì", "tìm insight", "xu hướng", "có gì bất thường".
```
**Mẫu câu lệnh khởi động:**
```
Trước khi làm: hỏi tôi 4–6 câu (ngành, câu hỏi phân tích, mốc so sánh, yếu tố đặc thù), rồi tìm insight.
Tìm điểm đáng chú ý trong dữ liệu sau để trả lời: [câu hỏi]. So sánh với: [kỳ/mục tiêu].
--- DỮ LIỆU ---
[dán bảng số]
```

## 👣 Diễn tiến 45 phút
| Phút | Hoạt động |
|---|---|
| 0–5 | Bài toán: có số mà không biết nói gì |
| 5–15 | Làm mẫu: doanh thu 6 tháng → kênh động lực, ngoại lệ |
| 15–35 | Học viên tìm insight từ dữ liệu của mình |
| 35–40 | Lỗi hay gặp: kết luận nhân–quả chắc nịch |
| 40–45 | Bài tập: lưu agent + rút 3 insight từ bảng thật |

## 📝 Bài tập về nhà
Từ bảng đã làm sạch ở Ngày 06, rút 3–5 điểm đáng chú ý kèm con số.

## ✅ Tiêu chí đạt & Đo hiệu quả
- **Đạt khi:** mỗi insight có con số, có nêu giới hạn dữ liệu.
- **Đo trước/sau:** thời gian rút insight; số quyết định có dữ liệu hỗ trợ.

## 🔗 Liên kết
Nhận dữ liệu sạch từ Ngày 06; đẩy sang Báo cáo chỉ số (Ngày 08) và Gợi ý biểu đồ (Ngày 09).
