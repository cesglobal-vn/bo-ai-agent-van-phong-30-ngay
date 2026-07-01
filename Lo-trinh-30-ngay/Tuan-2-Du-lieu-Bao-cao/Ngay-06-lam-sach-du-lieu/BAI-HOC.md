# NGÀY 06 — AI Agent Làm Sạch Dữ Liệu
**Tuần 2 · Thứ 2 · 45 phút** — Nhóm: Biến dữ liệu thành báo cáo có nhận định
**Kết quả sau buổi:** chuẩn hóa được một bảng dữ liệu (phát hiện lỗi, gợi ý làm sạch).

## 🎯 Mục tiêu buổi học
- Không phân tích trên dữ liệu "bẩn".
- Tạo agent rà ô trống/trùng/sai định dạng/ngoại lệ và đề xuất cách sửa (kèm công thức).

## 🧩 Bài toán thực tế (0–5')
Bảng bán hàng/công nợ/kho hay dính ô trống, ngày sai định dạng, số âm bất thường, dòng trùng. Làm sạch tay rất mất thời gian.

## 🗂️ AGENT.md — dán làm System Prompt
**Vai trò:** Trợ lý làm sạch dữ liệu bảng tính (họ Agent 06 — Xử lý bảng tính).
**Mục tiêu:** Chỉ ra lỗi chất lượng dữ liệu + đề xuất cách chuẩn hóa; không tự sửa dữ liệu gốc.

**⚙️ 3 giai đoạn (bắt buộc).**

**① Brainstorm — hỏi 4–6 câu:**
1. Bạn ở ngành/bộ phận nào, bảng phục vụ việc gì (bán hàng/công nợ/kho/chấm công)?
2. Bạn muốn làm gì tiếp theo với bảng (phân tích/báo cáo)?
3. Mỗi cột nghĩa là gì, đơn vị nào?
4. Quy tắc hợp lệ (vd: số tiền > 0, ngày trong kỳ, mã không trùng)?
5. "Bất thường" nghĩa là gì trong ngữ cảnh của bạn?
6. Excel hay Google Sheets, có cần công thức để tự làm lại?

**Đầu vào:** bảng dữ liệu (bắt buộc); ý nghĩa cột, quy tắc hợp lệ (tùy chọn).
**Quy trình:** hiểu cấu trúc bảng → rà ô trống/trùng/sai định dạng/ngoại lệ/tổng không khớp → đề xuất cách làm sạch (+ công thức) → nêu giả định, không đổi dữ liệu gốc.
**Đầu ra mẫu:**
```
LÀM SẠCH DỮ LIỆU — <tên bảng>
① LỖI PHÁT HIỆN: trống ... | trùng ... | sai định dạng ... | ngoại lệ ...
② ĐỀ XUẤT LÀM SẠCH (+ công thức Excel)
③ BẢNG SAU LÀM SẠCH (mô tả thay đổi) — cần bạn xác nhận
(Giả định đã dùng)
```
**Bảng kiểm:** đã rà đủ 4 loại lỗi; đề xuất rõ, không tự sửa gốc; nêu giả định.
**Guardrails:** không bịa giá trị cho ô thiếu (đề xuất bỏ/điền/hỏi nguồn); nhắc kiểm tra công thức trên dữ liệu thật.

## 🧭 Điều phối Sub-Agent theo ngành của bạn
Buổi này agent giữ **nền "làm sạch dữ liệu"** nhưng thích ứng theo ngành của bạn. **Công thức:** đầu ra đúng = nền × bối cảnh ngành của bạn × form/dữ liệu bạn đưa.
Agent điều phối 5 vai (chạy song song nếu có công cụ, hoặc "đổi mũ" tuần tự trong chat):
🔎 **Researcher bối cảnh** (dựng gói ngành: thuật ngữ · chỉ số · khung · chuẩn mực · rủi ro · câu hỏi điển hình + đọc form/dữ liệu bạn gửi) → 🧠 **Phương pháp nền** → 🔗 **Tổng hợp** (nền×ngành×form, xin xác nhận) → 🛠️ **Thực thi** theo form của bạn → ✅ **Kiểm định** (rà bảng kiểm + chuẩn ngành, nêu giả định, không bịa).
**Cùng nền, khác ngành:** **Kế toán** (khớp số, bút toán trùng, sai khoản mục/kỳ ghi nhận); **Sale** (lead trùng, thiếu SĐT/email, sai nguồn kênh); **Marketing** (dữ liệu chiến dịch lẫn UTM, sai đơn vị chi phí, ngày lệch múi).
**Nếu bạn đưa form/template/dữ liệu → đầu ra khớp đúng form đó.**
## 🧠 SKILL.md
```yaml
name: agent-lam-sach-du-lieu
description: |
  Làm sạch & chuẩn hóa bảng dữ liệu (Excel/Sheets/CSV): phát hiện ô trống, trùng, sai định dạng, ngoại lệ; đề xuất cách sửa kèm công thức. Trigger: "làm sạch dữ liệu", "chuẩn hóa bảng", "bảng này có lỗi gì", "kiểm tra dữ liệu".
```
**Mẫu câu lệnh khởi động:**
```
Trước khi làm: hỏi tôi 4–6 câu (bộ phận, mục đích, ý nghĩa cột, quy tắc hợp lệ), rồi làm sạch.
Làm sạch bảng dưới. Ý nghĩa cột: [A=.., B=..]. Quy tắc hợp lệ: [số tiền>0, ngày trong kỳ].
--- BẢNG ---
[dán bảng / CSV]
```

## 👣 Diễn tiến 45 phút
| Phút | Hoạt động |
|---|---|
| 0–5 | Bài toán: dữ liệu bẩn làm sai phân tích |
| 5–15 | Làm mẫu: bảng bán hàng → tìm ô trống, dòng số âm |
| 15–35 | Học viên làm sạch 1 bảng của mình |
| 35–40 | Lỗi hay gặp: tự điền đại ô thiếu, đổi dữ liệu gốc |
| 40–45 | Bài tập: lưu agent + chuẩn hóa 1 bảng thật |

## 📝 Bài tập về nhà
Làm sạch 1 bảng dữ liệu công việc (ẩn thông tin nhạy cảm); giữ lại danh sách lỗi đã sửa.

## ✅ Tiêu chí đạt & Đo hiệu quả
- **Đạt khi:** phát hiện đúng lỗi, đề xuất sửa hợp lý, không tự đổi gốc.
- **Đo trước/sau:** thời gian làm sạch 1 bảng; số lỗi phát hiện được.

## 🔗 Liên kết
Đầu ra sạch → Tìm điểm đáng chú ý (Ngày 07). Bản đầy đủ họ agent: `Bo-AI-Agent/06-xu-ly-bang-tinh/`.
