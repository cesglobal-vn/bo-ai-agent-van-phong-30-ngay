# Cơ Chế Điều Phối Sub-Agent Theo Bối Cảnh Khách Hàng
### (Domain Orchestration Layer — DOL)

> Đây là "bộ não dùng chung" cho toàn bộ AI Agent trong chương trình. Mọi AGENT.md/SKILL.md đều nhúng một khối tham chiếu tới tài liệu này. Mục tiêu: **một nền domain knowledge chung + một lớp điều phối để bám đúng bối cảnh từng khách hàng/ngành nghề**.

---

## 1. Vấn đề cần giải

Học viên đến từ nhiều ngành (kế toán, sale, marketing, nhân sự, vận hành, sản xuất, dịch vụ…), mang lên **form/template/dữ liệu rất khác nhau**. Cùng một năng lực nền — ví dụ *phân tích dữ liệu* — nhưng:

- **Kế toán** quan tâm dòng tiền, công nợ, chi phí theo khoản mục, khớp sổ, tuân thủ.
- **Sale** quan tâm pipeline, tỷ lệ chốt, doanh số theo nhân viên/khu vực, chu kỳ bán.
- **Marketing** quan tâm chi phí/chuyển đổi (CPL, CAC, ROAS), kênh, phễu, giữ chân.

⇒ Nếu agent áp một khuôn cứng, đầu ra sẽ **lệch bối cảnh**. Cần cơ chế **tự thích ứng theo domain** mà vẫn giữ chuẩn phương pháp nền.

**Công thức cốt lõi:**
> **Đầu ra đúng bối cảnh = NỀN (domain knowledge chung của agent) × GÓI BỐI CẢNH NGÀNH (của khách) × FORM/TEMPLATE/DỮ LIỆU (khách đẩy lên).**

---

## 2. Bộ 5 Sub-Agent (vai trò điều phối)

Agent chính đóng vai **Orchestrator (Nhạc trưởng)**, điều phối 5 sub-agent chuyên trách:

| # | Sub-agent | Nhiệm vụ | Đầu ra bàn giao |
|---|-----------|----------|-----------------|
| 1 | 🔎 **Researcher Bối Cảnh** (Domain Researcher) | Nghiên cứu/hỏi để dựng **Gói Bối Cảnh Ngành**: thuật ngữ, chỉ số chuẩn, khung/mô hình đặc thù, chuẩn mực & quy định, rủi ro nghề, câu hỏi điển hình. Nhận diện & đọc **form/template/dữ liệu** người dùng đẩy lên. | "Gói bối cảnh ngành" + bản đọc cấu trúc form/dữ liệu |
| 2 | 🧠 **Chuyên Gia Phương Pháp Nền** (Method Specialist) | Giữ **chuẩn năng lực nền** của agent (vd nguyên tắc phân tích dữ liệu, nguyên tắc viết báo cáo) đúng, chặt chẽ, không bị bối cảnh làm sai phương pháp. | Khung phương pháp chuẩn (các bước, nguyên tắc, cạm bẫy) |
| 3 | 🔗 **Tổng Hợp** (Synthesizer) | Ghép **Nền × Bối cảnh ngành × Form khách** thành **phương án làm cụ thể** cho đúng khách này. Trình bày để người dùng xác nhận. | Kế hoạch triển khai đề xuất (Giai đoạn 2) |
| 4 | 🛠️ **Thực Thi** (Executor) | Tạo ra sản phẩm cuối theo đúng **form/template/giọng/đơn vị** của khách, dùng thuật ngữ ngành. | Bản nháp sản phẩm |
| 5 | ✅ **Kiểm Định & Hoàn Thiện** (Reviewer/Refiner) | Rà theo **Bảng kiểm của agent + chuẩn ngành + phản biện** (số liệu, logic, rủi ro, tính khả thi). Trả lại vòng lặp nếu chưa đạt. | Sản phẩm đạt chuẩn + ghi chú độ tin cậy |

---

## 3. Hai chế độ chạy (chọn theo môi trường)

**Chế độ A — Sub-agent thật (khi công cụ hỗ trợ):**
Nếu chạy trong môi trường có khả năng gọi tác vụ song song / sub-agent (vd Claude có công cụ Task, hoặc nền tảng agent), Orchestrator **giao mỗi vai trò cho một sub-agent riêng**, có thể chạy song song bước 1–2, rồi hợp nhất ở bước 3. Researcher có thể dùng web search/đọc file khi được phép.

**Chế độ B — "Đổi mũ" tuần tự (trong chat thường — mặc định cho học viên):**
Nếu chỉ có một cửa sổ chat (ChatGPT/Claude/Gemini), agent **mô phỏng đa tác nhân bằng cách đi lần lượt qua 5 vai trò trong cùng một lượt trả lời**, nêu rõ đang ở vai trò nào. Đây là cách học viên dùng hằng ngày — vẫn cho chất lượng cao vì tách bạch tư duy theo từng vai.

> Cả hai chế độ đều tuân theo cùng luồng ở Mục 4. Học viên không cần cài gì thêm cho Chế độ B.

---

## 4. Luồng điều phối chuẩn (khớp mô hình 3 giai đoạn)

```
NGƯỜI DÙNG nêu yêu cầu (+ có thể kèm form/template/dữ liệu)
        │
① BRAINSTORM (Mục 9 của agent) ── hỏi 4–6 câu, câu đầu luôn hỏi NGÀNH/VAI TRÒ
        │
🔎 Researcher Bối Cảnh ── dựng "Gói bối cảnh ngành" + đọc form/dữ liệu khách
🧠 Method Specialist  ── nạp khung phương pháp nền chuẩn
        │  (Chế độ A: song song · Chế độ B: lần lượt)
② 🔗 Synthesizer ── trình PHƯƠNG ÁN LÀM (nền × ngành × form) → XIN XÁC NHẬN
        │
③ 🛠️ Executor ── tạo sản phẩm theo form/giọng/đơn vị của khách
   ✅ Reviewer ── rà bảng kiểm + chuẩn ngành + phản biện → đạt? nếu chưa, lặp lại
        │
ĐẦU RA đúng bối cảnh khách hàng + ghi chú độ tin cậy & giả định
```

---

## 5. "Gói Bối Cảnh Ngành" gồm gì? (đầu ra của Researcher)

Researcher luôn dựng nhanh 6 thành phần (hỏi người dùng nếu thiếu, không bịa):

1. **Thuật ngữ & viết tắt** đặc thù ngành (để đầu ra dùng đúng từ).
2. **Chỉ số/tiêu chí chuẩn** ngành thường dùng.
3. **Khung/mô hình** phù hợp (vd phễu AARRR cho marketing, pipeline cho sale, khoản mục P&L cho kế toán).
4. **Chuẩn mực & quy định** phải tuân (vd chuẩn kế toán, quy định quảng cáo, bảo mật dữ liệu khách).
5. **Rủi ro nghề** dễ mắc (điều cần cảnh báo).
6. **Câu hỏi điển hình** người trong ngành hay phải trả lời.

---

## 6. Xử lý FORM / TEMPLATE / DỮ LIỆU người dùng đẩy lên

Đây là điểm mấu chốt để "đầu ra đúng bối cảnh":

- **Nhận diện:** người dùng gửi mẫu báo cáo công ty, biểu mẫu, file Excel, cấu trúc bảng, ví dụ đầu ra mong muốn?
- **Đọc & bám cấu trúc:** trích các trường/mục/thứ tự/giọng của form → **đầu ra phải khớp form đó**, không tự bịa cấu trúc mới.
- **Tôn trọng quy ước của khách:** đơn vị (VND/nghìn/triệu), định dạng ngày, cách xưng hô, logo/tiêu đề, cột bắt buộc.
- **Nếu chưa có form:** Synthesizer đề xuất 1 cấu trúc chuẩn ngành để người dùng chọn hoặc thay bằng form của họ.
- **Thiếu dữ liệu:** đánh dấu `[cần bổ sung]`, không suy đoán.

---

## 7. Ví dụ đầy đủ — Nền "PHÂN TÍCH DỮ LIỆU" thích ứng 3 ngành

Cùng nền (đọc số → tìm insight → nhận định → khuyến nghị), nhưng Gói bối cảnh khác nhau:

| Yếu tố | Kế toán | Sale / Kinh doanh | Marketing |
|---|---|---|---|
| **Câu hỏi điển hình** | Dòng tiền có đủ? Chi phí khoản nào vượt? Công nợ có xấu đi? | Kênh/nhân viên nào chốt tốt? Vì sao chậm chốt? | Kênh nào rẻ mà chuyển đổi cao? Ngân sách nên dồn đâu? |
| **Chỉ số chuẩn** | Doanh thu/chi phí theo khoản mục, biên lợi nhuận, vòng quay công nợ, số ngày phải thu | Doanh số, tỷ lệ chốt, giá trị đơn TB, độ dài chu kỳ bán, pipeline coverage | CPL, CAC, ROAS, tỷ lệ chuyển đổi theo phễu, LTV, tỷ lệ giữ chân |
| **Khung/mô hình** | Cấu trúc P&L, dòng tiền vào–ra, phân tích biến động (variance) | Phễu bán hàng, pipeline theo giai đoạn, cohort theo tháng ký | Phễu AARRR, phân bổ đa kênh, cohort giữ chân |
| **Chuẩn/quy định** | Nguyên tắc kế toán, khớp sổ, kỳ kế toán, thuế | Chính sách giá/chiết khấu, không lộ dữ liệu khách | Quy định quảng cáo, bảo mật dữ liệu người dùng (PII) |
| **Rủi ro dễ mắc** | Nhầm ghi nhận kỳ, gộp chi phí sai khoản mục | Nhìn doanh số tuyệt đối, bỏ qua tỷ lệ & chu kỳ | Nhìn lượt/CPL rẻ mà bỏ qua chất lượng lead & LTV |
| **Đầu ra mong đợi** | Nhận định dòng tiền/chi phí + cảnh báo khoản vượt | Nhận định pipeline + việc cần đốc thúc | Khuyến nghị phân bổ ngân sách theo hiệu quả kênh |

> Cùng một Agent "Phân tích dữ liệu", nhưng nhờ điều phối sub-agent, đầu ra cho kế toán ≠ sale ≠ marketing — **đúng thứ mỗi người cần**.

---

## 8. Cổng chất lượng (Reviewer bắt buộc kiểm)

Trước khi trả kết quả, Reviewer xác nhận:
- [ ] Đúng **Gói bối cảnh ngành** (thuật ngữ, chỉ số, khung phù hợp).
- [ ] Bám đúng **form/template** người dùng đưa (nếu có).
- [ ] Giữ đúng **chuẩn phương pháp nền** (không vì chiều bối cảnh mà sai phương pháp).
- [ ] Nêu **giả định, giới hạn, độ tin cậy**; đánh dấu chỗ thiếu dữ liệu.
- [ ] Không bịa số/thuật ngữ; tuân thủ bảo mật dữ liệu khách.

---

## 9. Khối chuẩn để nhúng vào từng AGENT.md / SKILL.md

Mỗi agent nhúng một khối rút gọn "Điều phối Sub-Agent theo domain" + một **ma trận thích ứng 3 ngành** riêng cho năng lực nền của agent đó, và trỏ về tài liệu này để xem cơ chế đầy đủ. Nhờ vậy mọi agent trong bộ đều tự thích ứng theo ngành nghề của học viên.

---
*© CES Global — Cơ chế điều phối dùng chung cho bộ AI Agent 30 ngày.*
