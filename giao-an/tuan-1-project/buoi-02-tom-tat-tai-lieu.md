# Buổi 02 - AI Agent tóm tắt tài liệu (kịch bản hands-on)

> **Tuần 1 - Thứ 3** | Thời lượng: 45 phút | Công cụ: Claude Project (claude.ai)
> **Mô tả trên landing page:** "Tóm tắt tài liệu dài thành bảng ý chính".
> **Mô hình buổi học:** HANDS-ON. Trình tự: Giới thiệu -> điểm đau -> rồi mới vào thực hành từng bước. Giảng viên và học viên làm SONG SONG.
> **Tính năng trọng tâm hôm nay: CONTEXT** - nạp tài liệu (PDF/văn bản) vào Project để agent đọc và tham chiếu. Buổi 1 đã học Instructions (bộ não); hôm nay thêm Context (cho agent "tài liệu để đọc"). Vẫn Mức 1 - Project, không cài đặt gì.
> **Xưng hô:** giảng viên xưng **"em"**, gọi học viên là **"anh chị"**.
> **Định dạng script:** ngoặc vuông `[ ]` là chỉ dẫn thao tác (không đọc to); ngoặc kép `"..."` là lời giảng viên nói gần như nguyên văn; mỗi khối ``` là nội dung copy-dán được.

---

## A. Chuẩn bị trước buổi học

**Giảng viên chuẩn bị:**
- Claude đăng nhập sẵn; mở một Project để demo nút **Context** ("+" Add PDFs, documents, or other text).
- Gửi TRƯỚC vào nhóm lớp: file agent tóm tắt (khối ở Phần 2) + file PDF hợp đồng mẫu `tai-lieu-mau-hop-dong-dich-vu.pdf` (hư cấu, 8 trang) để cả lớp cùng nạp ở Phần 3 và thực hành.
- (Tùy chọn) chuẩn bị thêm 1-2 mẫu khác (báo cáo, chuỗi email - bản KHÔNG có thông tin thật) cho anh chị chưa mang tài liệu riêng.
- Slide tiêu đề + slide "bài toán ngập tài liệu".

**Học viên cần có sẵn (nhắn nhóm trước 1 tiếng):**
- Máy tính, tài khoản Claude (đã có Project từ buổi 1).
- Chuẩn bị 1 tài liệu thật hay phải đọc: hợp đồng, báo cáo dài, công văn, biên bản, hoặc chuỗi email. **Ẩn/che thông tin nhạy cảm** nếu là tài liệu mật.

**Mục tiêu buổi học:**
- Anh chị biết dùng **Context** của Project: nạp tài liệu một lần, hỏi và tóm tắt bao nhiêu lần cũng được.
- Có 1 trợ lý tóm tắt cho ra bản 4 phần: Ý chính / Số liệu - mốc / Điểm cần chú ý - rủi ro / Việc cần làm.
- Tự tóm tắt được 1 tài liệu thật ngay trong buổi và biết cách đối chiếu lại chỗ quan trọng với bản gốc.

---

## B. Kịch bản hands-on (45 phút)

### Phần 1 [00:00 - 07:00] - Giới thiệu và điểm đau

[Chào lớp, nối buổi 1.]

> "Em chào anh chị, mình quay lại buổi thứ hai. Hôm qua anh chị đã có trợ lý viết email đầu tiên - có ai đã dùng nó viết email thật rồi chưa ạ? [Chờ vài phản hồi.] Tuyệt vời. Hôm nay mình xây trợ lý thứ hai, và học thêm một tính năng mới của Claude giúp trợ lý mạnh hơn hẳn."

[Slide "bài toán ngập tài liệu".]

> "Em hỏi thật: một tuần anh chị phải đọc bao nhiêu tài liệu dài - hợp đồng, báo cáo, công văn, biên bản, hay chuỗi email 20-30 cái? [Chờ.] Với nhiều anh chị, đọc tài liệu ngốn cả buổi, mà đọc xong vẫn lo sót: sót một điều khoản phạt, sót một con số, sót một cái hạn."

> "Em kể một tình huống rất đời. Chị Hoa bên hành chính nhận một hợp đồng dịch vụ 15 trang, sếp bảo 'em rà nhanh rồi anh ký'. Chị đọc gần một tiếng, vẫn không chắc mình có bỏ sót điều khoản tự động gia hạn hay mức phạt nào không. Đọc kỹ thì mất thời gian, đọc lướt thì sợ sai - kẹt cả hai đường."

> "Hôm nay mình giải đúng bài đó: dựng một trợ lý ĐỌC GIÚP mình - tóm tắt tài liệu dài thành vài dòng ý chính, chỉ ra số liệu, mốc thời gian, và quan trọng nhất là điểm rủi ro cần chú ý. Và mình học một tính năng mới của Project tên là **Context** - hiểu nôm na là đưa hẳn tài liệu cho trợ lý 'cầm đọc', hỏi bao nhiêu lần cũng được mà không phải dán lại. Vẫn không cài đặt gì, vẫn trên web Claude. Mình bắt đầu, anh chị mở máy ra nhé."

### Phần 2 [07:00 - 16:00] - Nạp agent tóm tắt + làm quen tính năng Context

**Bước 2a - Nạp "bộ não" cho trợ lý (cả lớp cùng làm):**

> "Đầu tiên, giống hôm qua, mình cho trợ lý một bộ não. Anh chị vào claude.ai, bấm 'Projects', tạo project mới, đặt tên 'Trợ lý Tóm tắt tài liệu'. Rồi copy khối em gửi trong nhóm, dán vào ô Instructions, lưu lại. Ai xong gõ '1'."

[Chiếu khối bộ hướng dẫn để đối chiếu - không đọc to hết.]

```
VAI TRÒ
Bạn là chuyên viên phân tích tài liệu cho nhân viên văn phòng Việt Nam. Bạn đọc nhanh văn bản dài (hợp đồng, báo cáo, công văn, biên bản, chuỗi email, tài liệu kỹ thuật, PDF) và rút ra đúng thông tin người đọc cần để ra quyết định.

NHIỆM VỤ
Biến một tài liệu dài thành bản tóm tắt ngắn gọn, trung thực, đúng trọng tâm - kèm điểm cần chú ý và việc cần làm - giúp tôi nắm nội dung trong 1-2 phút mà không bỏ sót điều quan trọng.

ĐẦU VÀO (thông tin tôi sẽ cung cấp)
Bắt buộc:
- Nội dung tài liệu (nạp vào Context, đính kèm file, hoặc dán vào chat).
Tùy chọn:
- Mục đích đọc (để làm gì); soi kỹ khía cạnh nào (rủi ro, số tiền, thời hạn, trách nhiệm, điều khoản); độ dài mong muốn; đối tượng đọc bản tóm tắt.
Nếu tôi không nói mục đích, cứ giả định "nắm nhanh nội dung để ra quyết định" và ghi rõ giả định đó; đừng hỏi vặn nhiều.

QUY TRÌNH XỬ LÝ
1. Xác định loại tài liệu và mục đích đọc.
2. Đọc toàn bộ; tách ý chính khỏi ý phụ; giữ NGUYÊN mọi số liệu, ngày tháng, tên, số tiền.
3. Ghi lại điểm cần chú ý: điều khoản quan trọng, rủi ro, cam kết, hạn chót, mâu thuẫn hoặc thiếu sót.
4. Rút việc cần làm hoặc câu hỏi mở nếu tài liệu ngụ ý hành động.
5. Nếu tài liệu dài hoặc nhiều phần: tóm tắt từng phần rồi tổng hợp.
6. Trình bày theo ĐỊNH DẠNG ĐẦU RA; tự rà BẢNG KIỂM trước khi giao.

ĐỊNH DẠNG ĐẦU RA
TÓM TẮT: <tên hoặc loại tài liệu>
Mục đích đọc: <... (ghi rõ nếu là giả định)>

1) Ý CHÍNH (3-7 gạch đầu dòng)
- ...

2) SỐ LIỆU / MỐC QUAN TRỌNG
- <con số, ngày, số tiền, tên bên liên quan - trích đúng từ tài liệu>

3) ĐIỂM CẦN CHÚ Ý / RỦI RO
- <điều khoản quan trọng, mức phạt, hạn chót, điều bất lợi, mâu thuẫn...>

4) VIỆC CẦN LÀM / CÂU HỎI MỞ
- ...

(Tùy chọn) BẢNG SO SÁNH nếu tài liệu có nhiều hạng mục hoặc mốc cần đối chiếu.

QUY TẮC & AN TOÀN
- Chỉ dùng thông tin CÓ trong tài liệu; không thêm, không bịa. Nếu có suy luận, ghi rõ "(suy luận)".
- Giữ nguyên số liệu, ngày, tên, số tiền - không làm tròn, không đổi.
- Nếu tài liệu thiếu thông tin hoặc mâu thuẫn, nói rõ thay vì đoán.
- Không đưa ra kết luận pháp lý; chỉ nêu điểm cần luật sư/chuyên môn rà thêm.
- Nhắc tôi bảo mật nếu tài liệu có thông tin nhạy cảm.

BẢNG KIỂM (tự rà trước khi giao)
- [ ] Mọi ý đều truy được về tài liệu gốc, không bịa.
- [ ] Giữ nguyên số liệu, ngày, tên, số tiền.
- [ ] Đã nêu rõ điểm rủi ro / điều khoản quan trọng (nếu có).
- [ ] Ngắn hơn bản gốc đáng kể nhưng không mất ý cốt lõi.
- [ ] Đã nói rõ chỗ tài liệu thiếu hoặc mâu thuẫn.

ĐẦU RA MẪU (tham khảo cách trình bày, không sao chép cứng)
TÓM TẮT: Hợp đồng dịch vụ số <...>
Mục đích đọc: rà nhanh trước khi trình ký.

1) Ý CHÍNH
- Bên B cung cấp dịch vụ bảo trì cho Bên A trong 12 tháng.
- Hợp đồng có điều khoản tự động gia hạn.

2) SỐ LIỆU / MỐC QUAN TRỌNG
- Giá trị: <số tiền>/năm, thanh toán 2 đợt.
- Hiệu lực từ <ngày>; đợt 2 thanh toán <ngày>.

3) ĐIỂM CẦN CHÚ Ý / RỦI RO
- Điều 7: chậm thanh toán phạt 0,5%/ngày; chậm cung cấp dịch vụ quá 5 ngày phạt 5% giá trị.
- Điều 9: TỰ ĐỘNG GIA HẠN 12 tháng nếu không báo chấm dứt trước 30 ngày.

4) VIỆC CẦN LÀM / CÂU HỎI MỞ
- Xác nhận với sếp về điều khoản tự gia hạn trước khi ký.
- Kiểm tra lại mốc thanh toán đợt 2 có khớp dòng tiền không.

KHỞI ĐỘNG
Khi đã hiểu, hãy trả lời ngắn gọn rằng bạn đã sẵn sàng và hỏi tôi tài liệu cần tóm tắt (hoặc mục đích đọc nếu tài liệu đã có trong Context).
```

> "Nạp xong Claude sẽ báo sẵn sàng. Giờ tới phần mới của hôm nay."

**Bước 2b - Tính năng CONTEXT (điểm mới của buổi):**

[Chỉ vào panel bên phải của Project - ô Context.]

> "Anh chị nhìn bên phải màn hình Project, ngay dưới Instructions có một ô tên **Context**, ghi 'Add PDFs, documents, or other text'. Đây là chỗ mình đưa TÀI LIỆU cho trợ lý cầm."

> "Em nói rõ khác biệt để anh chị dùng đúng chỗ:"

- **Dán tài liệu vào ô chat:** dùng cho tài liệu đọc một lần rồi thôi (ví dụ một email cần tóm tắt nhanh).
- **Nạp tài liệu vào Context:** dùng cho tài liệu mình tra đi tra lại - hợp đồng đang xử lý, sổ tay công ty, quy định, bộ tài liệu dự án. Nạp một lần, từ đó hỏi mãi mà không phải dán lại; trợ lý luôn "nhớ" tài liệu đó.

> "Giờ cả lớp cùng nạp thử một tài liệu. Em gửi trong nhóm một hợp đồng mẫu (bản không có thông tin thật). Anh chị bấm dấu '+' ở ô Context, chọn 'Add text' rồi dán nội dung vào (hoặc tải file PDF lên nếu em gửi file), lưu lại. Ai nạp xong gõ '2'."

[Cho cả lớp khoảng 2 phút. Trợ giảng hỗ trợ ai vướng.]

### Phần 3 [16:00 - 24:00] - Cùng chạy thử: tóm tắt tài liệu mẫu

> "Để có tài liệu thật để tóm tắt, em gửi trong nhóm một file PDF hợp đồng dịch vụ mẫu (8 trang, `tai-lieu-mau-hop-dong-dich-vu.pdf`) - hư cấu nhưng nhiều điều khoản và số liệu như hợp đồng thật ngoài đời. Cả lớp tải file PDF về, bấm '+' ở ô Context, tải file PDF lên, lưu lại. Ai nạp xong gõ '2'."

[Chờ cả lớp nạp file vào Context. Trợ giảng hỗ trợ ai vướng.]

> "Nạp xong, mình để trợ lý đọc giúp. Cả lớp gõ đúng câu này vào ô chat rồi gửi:"

```
Tóm tắt tài liệu trong Context giúp tôi. Mục đích đọc: rà nhanh trước khi trình sếp ký. Soi kỹ: rủi ro, số tiền, thời hạn, điều khoản phạt và gia hạn.
```

[Chờ cả lớp chạy. Đọc chung 1 kết quả.]

> "Anh chị nhìn kết quả. Trợ lý trả về đúng 4 phần: Ý chính, Số liệu - mốc, Điểm cần chú ý - rủi ro, Việc cần làm. Cả một file 8 trang mà rút gọn còn mấy dòng. Để ý phần Rủi ro: nó tự lôi ra Điều 9 (chậm tiến độ phạt 0,3%/ngày, chậm thanh toán 0,5%/ngày) và Điều 10 - bảo trì TỰ ĐỘNG GIA HẠN, đơn giá tăng tới 8%/năm nếu không báo trước 30 ngày. Đúng cái bẫy mà đọc lướt hay bỏ sót. Và nó giữ nguyên các con số: tổng 1.320.000.000, golive 10/04/2026, uptime 99,5% - không bịa."

> "Sức mạnh thật của Context là ở chỗ này: mình hỏi sâu tiếp mà không cần dán lại tài liệu. Anh chị thử gõ thêm:"

```
Nếu tôi thanh toán đợt 2 trễ 10 ngày thì bị phạt bao nhiêu tiền? Trích đúng điều khoản và tính ra số cụ thể.
```

> "Thấy chưa - đợt 2 là 528 triệu, phạt 0,5%/ngày trong 10 ngày, nó tính ngay ra 26.400.000 đồng và trích đúng Điều 9.2. Cả hợp đồng 8 trang, hỏi câu nào nó tra câu đó. Nếu dán vào chat từng lần thì rất phiền; có Context thì hỏi thoải mái."

### Phần 4 [24:00 - 36:00] - Thực hành với tài liệu thật của anh chị

> "Đến lượt anh chị làm với một tài liệu thật của mình. Trước khi làm, em nhắc một câu quan trọng về bảo mật: nếu tài liệu có thông tin mật (lương, thông tin khách hàng, số tài khoản), anh chị che hoặc xóa phần đó trước khi nạp, hoặc dùng bản đã ẩn thông tin. AI hỗ trợ mình, nhưng dữ liệu mình vẫn phải tự giữ."

> "Cách làm: nạp tài liệu của anh chị vào ô Context (hoặc đính vào chat nếu chỉ đọc một lần), rồi copy khung này, điền mục đích, gửi:"

```
Tóm tắt tài liệu giúp tôi.
Mục đích đọc: [để làm gì, ví dụ: chuẩn bị họp / rà trước khi ký / báo cáo sếp].
Soi kỹ: [rủi ro / số tiền / thời hạn / trách nhiệm / điều khoản...].
Độ dài: [ngắn gọn / vừa].
```

> "Anh chị nào chưa mang tài liệu thì dùng file PDF hợp đồng mẫu em gửi trong nhóm (`tai-lieu-mau-hop-dong-dich-vu.pdf`) - hỏi thêm các câu khác trên chính file vừa nạp, hoặc thử soi một khía cạnh mới (tài chính, tiến độ, trách nhiệm)."

[Đi một vòng, gọi tên 1-2 anh chị, gỡ vướng. Nhắc mẹo dưới khi có người hỏi.]

> "Anh Nam ơi, tài liệu của anh dài quá đúng không? Anh gõ thêm 'Tóm tắt theo từng phần rồi tổng hợp lại' là nó chia nhỏ ra xử lý. Còn nếu là file scan hoặc ảnh chụp mà nó đọc không ra, thì cần bản chữ (đánh máy) hoặc file gốc - ảnh mờ thì AI dễ đọc sai số."

> "Ai có bản tóm tắt ưng ý rồi thì gõ 'xong' cho em."

### Phần 5 [36:00 - 41:00] - Tinh chỉnh, và ĐỐI CHIẾU lại (bước quan trọng nhất)

> "Bản tóm tắt hiếm khi vừa ý ngay. Anh chị thử một trong các câu chỉnh này:"

```
Tóm gọn hơn nữa, chỉ 5 gạch đầu dòng quan trọng nhất.
```
```
Soi kỹ hơn phần tài chính: mọi con số tiền, thuế, công nợ, thời hạn thanh toán.
```
```
Lập bảng so sánh các mốc thời gian và việc phải làm ở mỗi mốc.
```

> "Và đây là bước em muốn anh chị nhớ nhất của buổi hôm nay, quan trọng hơn cả cách tóm tắt: **ĐỐI CHIẾU LẠI**. Với tài liệu quan trọng - hợp đồng, số tiền, hạn chót, điều khoản phạt - anh chị phải mở tài liệu gốc, kiểm lại đúng những con số và điều khoản mà bản tóm tắt nêu. AI đọc rất nhanh nhưng vẫn có thể đọc sót hoặc nhầm một chỗ, nhất là tài liệu dài hoặc file scan. Bản tóm tắt là để mình nắm nhanh và biết chỗ nào cần soi - không phải để thay mình chịu trách nhiệm."

> "3 lỗi anh chị hay gặp tuần này: (1) tài liệu quá dài hoặc ảnh scan mờ, agent đọc sót - dùng bản chữ, chia nhỏ; (2) tin 100% bản tóm tắt mà không mở gốc kiểm - rất nguy với hợp đồng; (3) nạp tài liệu mật khi chưa được phép - luôn ẩn thông tin nhạy cảm trước."

### Phần 6 [41:00 - 45:00] - Lưu và giao bài về nhà

> "Tin vui: tài liệu anh chị nạp vào Context được lưu luôn trong Project. Mai mở lại project 'Trợ lý Tóm tắt' là tài liệu vẫn còn đó, hỏi tiếp được ngay, không phải nạp lại."

**Bài tập về nhà buổi 2:**
1. Nạp **2 tài liệu thật** (đã ẩn thông tin nhạy cảm) vào Project, tóm tắt mỗi cái.
2. Với mỗi tài liệu, hỏi thêm **3 câu sâu** (ví dụ: hạn chót gần nhất là ngày nào, điều khoản nào bất lợi, ai chịu trách nhiệm việc X).
3. **Đối chiếu** phần số liệu/điều khoản quan trọng với bản gốc, xem AI có sót hay nhầm chỗ nào không.
4. Đăng vào nhóm 1 câu: "hôm nay trợ lý tóm tắt giúp tôi tiết kiệm khoảng ... phút đọc tài liệu."

> "Ngày mai mình xây trợ lý thứ ba - ghi chú họp: biến ghi chú họp lộn xộn thành biên bản có đầu việc rõ ràng. Và mình học thêm tính năng Memory - cho trợ lý nhớ bối cảnh công ty mình. Hẹn gặp anh chị 8 giờ tối mai. Cảm ơn anh chị."

[Kết thúc buổi. Trợ giảng gửi lại file agent + các tài liệu mẫu vào nhóm lớp.]

---

## C. Checklist chuẩn bị của giảng viên

- [ ] Slide tiêu đề + slide "bài toán ngập tài liệu".
- [ ] Claude đăng nhập sẵn; đã thử nút Context (Add text / Add PDF) trong Project.
- [ ] Gửi vào nhóm TRƯỚC giờ học: file agent tóm tắt (Phần 2) + file PDF hợp đồng mẫu `tai-lieu-mau-hop-dong-dich-vu.pdf` (dùng cho Phần 3 + thực hành). Có thể thêm mẫu báo cáo/chuỗi email nếu muốn đa dạng.
- [ ] Trợ giảng trực chat hỗ trợ khi cả lớp nạp Context.
- [ ] Link ghi hình buổi học (gửi anh chị ca không dự trực tiếp được).

## D. Tiêu chí hoàn thành buổi 2 (đối chiếu cam kết "đo được hiệu quả")

- Anh chị nạp được tài liệu vào Context và cho ra bản tóm tắt đủ 4 phần.
- Anh chị tóm tắt được tối thiểu 1 tài liệu thật + hỏi sâu ít nhất 1 câu.
- Anh chị biết và thực hành bước đối chiếu số liệu/điều khoản với bản gốc.
- Anh chị nêu được ước lượng thời gian tiết kiệm khi đọc tài liệu (phục vụ mẫu báo cáo hiệu quả trước - sau của khóa).
