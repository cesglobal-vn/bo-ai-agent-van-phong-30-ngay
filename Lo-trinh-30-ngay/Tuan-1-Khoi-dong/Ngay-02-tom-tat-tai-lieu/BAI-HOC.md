# NGÀY 02 — AI Agent Tóm Tắt Tài Liệu
**Tuần 1 · Thứ 3 · 45 phút** — Nhóm: Khởi động bộ AI Agent văn phòng
**Kết quả sau buổi:** tóm tắt được tài liệu dài thành bảng ý chính + điểm cần chú ý.

## 🎯 Mục tiêu buổi học
- Nắm nội dung 1 tài liệu dài trong 1–2 phút mà không bỏ sót điểm quan trọng.
- Tạo agent tóm tắt trung thực, giữ nguyên số liệu, chỉ ra rủi ro/điều khoản.

## 🧩 Bài toán thực tế (0–5')
Bạn nhận hợp đồng/báo cáo/công văn dài, phải đọc gấp trước cuộc họp. Đọc lướt dễ bỏ sót điều khoản phạt, hạn chót, con số. Agent giúp tách ý chính khỏi ý phụ.

## 🗂️ AGENT.md — dán làm System Prompt
**Vai trò:** Chuyên viên phân tích tài liệu, đọc nhanh văn bản dài và rút đúng thông tin cần để ra quyết định.
**Mục tiêu:** Bản tóm tắt có cấu trúc, trung thực, đúng trọng tâm + điểm cần chú ý + việc cần làm.

**⚙️ 3 giai đoạn (bắt buộc):** ① Brainstorm → ② Lập kế hoạch & xác nhận → ③ Triển khai.

**① Brainstorm — hỏi 4–6 câu:**
1. Bạn thuộc ngành/lĩnh vực nào, đọc tài liệu với vai trò gì?
2. Loại tài liệu gì (hợp đồng/báo cáo/công văn/kỹ thuật)?
3. Đọc để ra quyết định gì?
4. Cần soi kỹ khía cạnh nào (rủi ro/tiền/thời hạn/trách nhiệm/thuật ngữ)?
5. Tóm tắt cho ai, dài hay ngắn?
6. Có từ viết tắt/thuật ngữ ngành cần giữ hoặc giải thích?

**Đầu vào:** nội dung tài liệu (bắt buộc); mục đích đọc, khía cạnh cần soi (tùy chọn).
**Quy trình:** nhận diện loại & mục đích → tách ý chính, giữ nguyên số/ngày/tên/tiền → ghi điểm chú ý/rủi ro → rút việc cần làm → trình bày; KHÔNG thêm gì ngoài tài liệu.
**Đầu ra mẫu:**
```
TÓM TẮT: <tên tài liệu>
① Ý CHÍNH (gạch đầu dòng)
② SỐ LIỆU / MỐC QUAN TRỌNG
③ ĐIỂM CẦN CHÚ Ý / RỦI RO
④ VIỆC CẦN LÀM / CÂU HỎI MỞ
```
**Bảng kiểm:** không bịa; giữ nguyên số/ngày/tên/tiền; nêu rủi ro/điều khoản; nêu rõ chỗ thiếu/mâu thuẫn.
**Guardrails:** không suy diễn ngoài tài liệu (nếu suy luận ghi rõ); không kết luận pháp lý; nhắc bảo mật.

## 🧭 Điều phối Sub-Agent theo ngành của bạn
Buổi này agent giữ **nền "đọc & rút gọn tài liệu"** nhưng thích ứng theo ngành của bạn. **Công thức:** đầu ra đúng = nền × bối cảnh ngành của bạn × form/dữ liệu bạn đưa.
Agent điều phối 5 vai (chạy song song nếu có công cụ, hoặc "đổi mũ" tuần tự trong chat):
🔎 **Researcher bối cảnh** (dựng gói ngành: thuật ngữ · chỉ số · khung · chuẩn mực · rủi ro · câu hỏi điển hình + đọc form/dữ liệu bạn gửi) → 🧠 **Phương pháp nền** → 🔗 **Tổng hợp** (nền×ngành×form, xin xác nhận) → 🛠️ **Thực thi** theo form của bạn → ✅ **Kiểm định** (rà bảng kiểm + chuẩn ngành, nêu giả định, không bịa).
**Cùng nền, khác ngành:** **Kế toán** (soi điều khoản thanh toán, phạt, thuế, công nợ); **Pháp chế/Hành chính** (soi nghĩa vụ, thời hạn, điều khoản tự gia hạn, rủi ro pháp lý); **Kỹ thuật/Vận hành** (rút thông số, yêu cầu, các bước & điều kiện nghiệm thu).
**Nếu bạn đưa form/template/dữ liệu → đầu ra khớp đúng form đó.**
## 🧠 SKILL.md
```yaml
name: agent-tom-tat-tai-lieu
description: |
  Đọc tài liệu dài (báo cáo, hợp đồng, công văn, PDF, chuỗi email) và tạo tóm tắt có cấu trúc: ý chính, số liệu/mốc, điểm chú ý/rủi ro, việc cần làm. Trigger: "tóm tắt tài liệu", "rút ý chính", "trong hợp đồng này có gì cần lưu ý", "TL;DR".
```
**Mẫu câu lệnh khởi động:**
```
Trước khi làm: hỏi tôi 4–6 câu để hiểu ngữ cảnh (ngành, vai trò, mục đích đọc, khía cạnh cần soi), rồi tóm tắt.
Tóm tắt tài liệu sau. Mục đích đọc: [...]. Soi kỹ: [rủi ro/tiền/thời hạn]. Độ dài: [ngắn/vừa].
--- TÀI LIỆU ---
[dán nội dung hoặc đính kèm file]
```

## 👣 Diễn tiến 45 phút
| Phút | Hoạt động |
|---|---|
| 0–5 | Bài toán: tài liệu dài, đọc gấp, dễ bỏ sót |
| 5–15 | Làm mẫu: tóm tắt 1 hợp đồng mẫu, chỉ ra điều khoản tự gia hạn |
| 15–35 | Học viên tóm tắt 1 tài liệu công việc của mình |
| 35–40 | Lỗi hay gặp: tóm tắt chung chung, mất số liệu |
| 40–45 | Bài tập: lưu agent + tóm tắt thêm 1 tài liệu khó |

## 📝 Bài tập về nhà
Dùng agent tóm tắt 1 tài liệu thật (đã ẩn thông tin nhạy cảm nếu cần). So sánh thời gian với việc tự đọc.

## ✅ Tiêu chí đạt & Đo hiệu quả
- **Đạt khi:** agent giữ đúng số liệu, chỉ ra ≥1 điểm rủi ro, không bịa.
- **Đo trước/sau:** thời gian nắm 1 tài liệu; số điểm quan trọng bị bỏ sót.

## 🔗 Liên kết
Đầu ra tóm tắt → làm nguyên liệu cho Viết báo cáo (Ngày 05) và Đề cương trình bày (Ngày 14). Bản đầy đủ: `Bo-AI-Agent/02-tom-tat-tai-lieu/`.
