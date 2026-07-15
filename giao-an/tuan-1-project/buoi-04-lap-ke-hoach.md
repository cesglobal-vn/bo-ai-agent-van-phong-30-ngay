# Buổi 04 - AI Agent lập kế hoạch (kịch bản hands-on)

> **Tuần 1 - Thứ 5** | Thời lượng: 45 phút | Công cụ: Claude Project (claude.ai)
> **Mô tả trên landing page:** "Lập kế hoạch ngày/tuần có ưu tiên, đặt trợ lý tự chạy định kỳ".
> **Mô hình buổi học:** HANDS-ON. Trình tự: Giới thiệu -> điểm đau -> rồi mới vào thực hành từng bước. Giảng viên và học viên làm SONG SONG.
> **Tính năng trọng tâm hôm nay: SCHEDULED** - đặt trợ lý tự chạy theo lịch định kỳ (ví dụ mỗi sáng, mỗi đầu tuần). Buổi 1 học Instructions (bộ não), buổi 2 học Context (nạp tài liệu), buổi 3 học Memory (nhớ bối cảnh); hôm nay thêm Scheduled - tính năng thứ 4, khép lại bộ 4 tính năng của Project. Vẫn Mức 1 - Project, không cài đặt gì.
> **Xưng hô:** giảng viên xưng **"em"**, gọi học viên là **"anh chị"**.
> **Định dạng script:** ngoặc vuông `[ ]` là chỉ dẫn thao tác (không đọc to); ngoặc kép `"..."` là lời giảng viên nói gần như nguyên văn; mỗi khối ``` là nội dung copy-dán được.

---

## A. Chuẩn bị trước buổi học

**Giảng viên chuẩn bị:**
- Claude đăng nhập sẵn; mở một Project để demo. **Thử trước tính năng Scheduled/Tasks** (nút đặt lịch tự chạy) trong tài khoản để nắm đúng vị trí nút trước khi lên lớp.
- Gửi TRƯỚC vào nhóm lớp: file agent lập kế hoạch (khối "bộ não" ở Phần 2) + 1 danh sách việc mẫu (Phần 3) để cả lớp cùng chạy thử.
- Slide tiêu đề + slide "bài toán ngập việc, không biết làm gì trước".

**Học viên cần có sẵn (nhắn nhóm trước 1 tiếng):**
- Máy tính, tài khoản Claude (đã có Project từ các buổi trước).
- Chuẩn bị sẵn 1 danh sách việc thật của tuần này (gạch đầu dòng cũng được), kèm hạn chót nếu có.

**Mục tiêu buổi học:**
- Anh chị có 1 trợ lý lập kế hoạch: nhập danh sách việc lộn xộn, ra bảng việc có ưu tiên A/B/C, chỉ rõ 1 việc quan trọng nhất, và cảnh báo khi quá tải.
- Anh chị biết dùng **Scheduled**: đặt trợ lý tự chạy theo lịch (ví dụ mỗi sáng gửi kế hoạch ngày, mỗi Thứ 2 gửi kế hoạch tuần) mà không phải gõ lại.
- Lập được kế hoạch cho tuần thật của mình ngay trong buổi.

---

## B. Kịch bản hands-on (45 phút)

### Phần 1 [00:00 - 07:00] - Giới thiệu và điểm đau

[Chào lớp, nối buổi 3.]

> "Em chào anh chị, mình vào buổi thứ tư. Ba buổi qua anh chị đã có trợ lý viết email, trợ lý tóm tắt tài liệu, và trợ lý ghi biên bản họp. Hôm nay là trợ lý thứ tư, và mình học nốt tính năng thứ tư, cũng là tính năng cuối của bộ Project: cho trợ lý TỰ CHẠY theo lịch."

[Slide "bài toán ngập việc".]

> "Em hỏi thật: sáng đầu tuần anh chị mở máy lên, việc thì một đống, deadline chồng nhau, mà không biết nên làm cái gì trước đúng không? [Chờ vài phản hồi.] Rồi cuối tuần nhìn lại, việc gấp thì làm rồi, nhưng việc quan trọng lại bị đẩy lùi mãi."

> "Em kể một tình huống rất đời. Anh Sơn trưởng nhóm, sáng nào cũng mất 20-30 phút ngồi nghĩ hôm nay làm gì trước, ghi ra giấy, xong tới trưa lại rối vì việc mới chen vào. Kế hoạch có, nhưng không có thứ tự ưu tiên, và ngày nào cũng phải làm lại từ đầu."

> "Hôm nay mình giải đúng bài đó: dựng một trợ lý biến danh sách việc rối thành kế hoạch có ưu tiên rõ ràng, chỉ ra đúng một việc quan trọng nhất, và cảnh báo khi mình ôm quá nhiều so với thời gian thật có. Rồi mình dạy nó TỰ CHẠY: mỗi sáng, hoặc mỗi đầu tuần, tự gửi cho mình một bản kế hoạch nháp, khỏi phải nhớ. Vẫn không cài đặt gì, vẫn trên web Claude. Mình bắt đầu, anh chị mở máy ra nhé."

### Phần 2 [07:00 - 16:00] - Nạp agent lập kế hoạch + làm quen tính năng Scheduled

**Bước 2a - Nạp "bộ não" cho trợ lý (cả lớp cùng làm):**

> "Đầu tiên, giống các buổi trước, mình cho trợ lý một bộ não. Anh chị vào claude.ai, bấm 'Projects', tạo project mới, đặt tên 'Trợ lý Lập kế hoạch'. Rồi copy khối em gửi trong nhóm, dán vào ô Instructions, lưu lại. Ai xong gõ '1'."

[Chiếu khối bộ não để đối chiếu - không đọc to hết.]

```
VAI TRÒ
Bạn là trợ lý lập kế hoạch cá nhân và nhóm cho nhân viên văn phòng Việt Nam. Bạn biến
mục tiêu và danh sách việc rối rắm thành kế hoạch ngày/tuần/tháng có thứ tự ưu tiên,
thực tế và bám thời gian thật.

NHIỆM VỤ
Từ danh sách việc và khung thời gian tôi cung cấp, tạo một kế hoạch rõ ràng: chỉ ra
việc quan trọng nhất, phân bổ thời gian hợp lý, và cảnh báo khi kế hoạch quá tải so
với thời gian thực có.

ĐẦU VÀO (thông tin tôi sẽ cung cấp)
Bắt buộc:
- Danh sách việc/mục tiêu cần làm.
- Khung thời gian (ngày/tuần/tháng).
Tùy chọn:
- Deadline từng việc, mức độ quan trọng.
- Thời gian thực có (số giờ rảnh, trừ họp cố định).
- Ràng buộc (lịch họp, ca kíp, phụ thuộc người khác); nguồn lực hỗ trợ.
Nếu tôi không nói rõ thời gian thực có, hãy hỏi lại đúng 1 câu; các mục khác tự suy
luận và ghi rõ giả định.

QUY TRÌNH XỬ LÝ
1. Làm rõ mục tiêu chính của kỳ (điều gì đạt được là coi như thành công).
2. Phân loại ưu tiên theo Quan trọng x Khẩn cấp: gán A (quan trọng, làm trước) / B / C.
3. Ước lượng thời gian mỗi việc; đối chiếu với thời gian thực có. Nếu tổng vượt quá thời
   gian có, cảnh báo và đề xuất cắt bớt/giãn tiến độ/uỷ quyền.
4. Chọn 1-3 việc "must-do", xếp phần còn lại, chừa khoảng đệm cho việc phát sinh.
5. Trình bày theo ĐỊNH DẠNG ĐẦU RA; tự rà BẢNG KIỂM trước khi giao.

ĐỊNH DẠNG ĐẦU RA
KẾ HOẠCH <NGÀY/TUẦN/THÁNG> - <kỳ>
Mục tiêu chính: <...>
Ưu tiên số 1: <việc quan trọng nhất>

VIỆC THEO ƯU TIÊN
| # | Việc | Ưu tiên (A/B/C) | Ước lượng | Hạn | Ghi chú |
|---|------|-----------------|-----------|-----|---------|
| 1 | ... | ... | ... | ... | ... |

LỊCH GỢI Ý (nếu theo ngày/tuần)
- Thứ 2: ...
- Thứ 3: ...

CẢNH BÁO TẢI: <nếu tổng thời gian > thời gian có; nêu cách xử lý>

QUY TẮC & AN TOÀN
- Luôn chỉ ra đúng 1 ưu tiên số 1; không dàn đều mọi việc thành quan trọng như nhau.
- Chỉ dùng thông tin tôi cung cấp; thiếu thì hỏi hoặc ghi [cần xác nhận], không bịa việc.
- Không hứa khối lượng bất khả thi; nói thẳng khi kế hoạch quá tải.
- Không tự gán việc cho người khác khi chưa xác nhận nguồn lực.
- Tôn trọng cân bằng công việc - nghỉ ngơi; luôn chừa thời gian đệm.

BẢNG KIỂM (tự rà trước khi giao)
- [ ] Có mục tiêu chính và đúng 1 ưu tiên số 1.
- [ ] Ưu tiên hợp lý theo quan trọng/khẩn cấp, không dàn đều.
- [ ] Đã đối chiếu thời gian và cảnh báo quá tải nếu cần.
- [ ] Thực tế, có chừa khoảng đệm cho phát sinh.

KHỞI ĐỘNG
Khi đã hiểu, hãy trả lời ngắn gọn rằng bạn đã sẵn sàng, và hỏi tôi: (1) danh sách việc
và khung thời gian, (2) số giờ làm việc thực có trong kỳ. Nếu là lần đầu làm việc cùng
tôi, hỏi thêm tôi làm ngành/vai trò gì để lập kế hoạch cho sát.
```

> "Nạp xong Claude sẽ báo sẵn sàng và hỏi anh chị danh sách việc. Giờ tới phần mới của hôm nay."

**Bước 2b - Tính năng SCHEDULED (điểm mới của buổi):**

> "Ba buổi trước mình học Instructions - bộ não, Context - tài liệu để đọc, Memory - trí nhớ bối cảnh. Hôm nay là tính năng thứ tư: **Scheduled**, tức là đặt lịch cho trợ lý TỰ CHẠY. Thay vì sáng nào cũng phải mở Claude gõ 'lập kế hoạch cho tôi', mình hẹn giờ một lần, rồi cứ đến giờ đó nó tự chạy và gửi kết quả cho mình."

> "Em nói rõ để anh chị hình dung khi nào dùng: những việc LẶP LẠI ĐỀU ĐẶN - lập kế hoạch mỗi sáng, tổng hợp việc mỗi Thứ 2, nhắc chuẩn bị họp giao ban hàng tuần. Những việc đó đặt lịch một lần cho nó tự làm. Còn việc phát sinh một lần thì mình cứ gõ tay như bình thường."

> "Anh chị nhìn màn hình em demo vị trí nút đặt lịch [chỉ vào nút Scheduled/Tasks], lát nữa cả lớp cùng đặt ở Phần 5. Giờ mình chạy thử cho trợ lý hoạt động đã."

### Phần 3 [16:00 - 25:00] - Cùng chạy thử: lập kế hoạch tuần từ danh sách mẫu

> "Để cả lớp cùng thấy trợ lý làm việc, mình dùng chung một danh sách việc mẫu. Anh chị copy khối này, dán vào ô chat của Project 'Trợ lý Lập kế hoạch' rồi gửi:"

```
Lập kế hoạch tuần giúp tôi từ danh sách dưới đây. Thời gian thực có: khoảng 5 giờ làm
việc mỗi ngày (đã trừ họp).

- Hoàn thành báo cáo quý, hạn Thứ 5.
- Chuẩn bị tài liệu họp khách hàng, họp vào Thứ 4.
- Rà 3 hợp đồng trước khi trình ký.
- Trả lời email tồn đọng.
- Họp giao ban nhóm sáng Thứ 2 (cố định).
- Làm slide đào tạo nội bộ, chưa có hạn cụ thể.
```

[Chờ cả lớp chạy. Đọc chung 1 kết quả.]

> "Anh chị nhìn kết quả. Trợ lý không liệt kê lại y nguyên, mà nó XẾP ƯU TIÊN: báo cáo quý và chuẩn bị họp khách được gán A vì vừa quan trọng vừa gấp; rà hợp đồng gán B; trả lời email và làm slide gán C vì chưa gấp. Và nó chốt đúng một Ưu tiên số 1 là báo cáo quý. Đây là điểm quan trọng nhất: không phải việc nào cũng như nhau."

> "Để ý dòng CẢNH BÁO TẢI cuối cùng: nó cộng thời gian các việc rồi so với 5 tiếng mỗi ngày, nếu quá thì nó nói thẳng 'tuần này hơi quá tải, nên giãn việc C sang tuần sau'. Nó không hứa làm hết trong khi thời gian không đủ."

> "Sức mạnh là ở chỗ này: mình hỏi tiếp mà không phải nhập lại danh sách. Anh chị thử gõ thêm:"

```
Chia nhỏ Ưu tiên số 1 (báo cáo quý) thành các bước làm cụ thể, xếp vào Thứ 2 và Thứ 3.
```

> "Thấy chưa, nó tách báo cáo quý thành từng bước và xếp vào lịch. Cả kế hoạch tuần, hỏi chỗ nào nó chi tiết chỗ đó."

### Phần 4 [25:00 - 35:00] - Thực hành với việc thật của anh chị

> "Đến lượt anh chị làm với danh sách việc thật của mình. Anh chị lấy danh sách việc tuần này đã chuẩn bị, copy khung này, điền vào rồi gửi:"

```
Lập kế hoạch [tuần này / hôm nay] giúp tôi.
Thời gian thực có: [số giờ làm việc mỗi ngày, đã trừ họp].
Danh sách việc (kèm hạn nếu có):
- [...]
- [...]
- [...]
```

> "Anh chị nào chưa có danh sách thật thì dùng lại danh sách mẫu ở Phần 3, thử đổi thời gian thực có xuống 3 tiếng mỗi ngày xem trợ lý cảnh báo tải như thế nào."

[Đi một vòng, gọi tên 1-2 anh chị, gỡ vướng. Nhắc mẹo dưới khi có người hỏi.]

> "Chị Lan ơi, việc của chị nhiều mà không có hạn đúng không? Chị gõ thêm 'giúp tôi đề xuất hạn hợp lý cho từng việc' là nó gợi ý mốc. Còn anh Hùng, nếu thấy nó gán ưu tiên chưa đúng ý, anh cứ nói 'việc X với tôi quan trọng hơn việc Y, xếp lại giúp tôi' - nó sắp lại ngay."

> "Ai có kế hoạch ưng ý rồi thì gõ 'xong' cho em."

### Phần 5 [35:00 - 41:00] - Đặt lịch TỰ CHẠY ĐỊNH KỲ (Scheduled) - điểm mới nhất

> "Giờ tới phần hay nhất của hôm nay. Kế hoạch anh chị vừa tạo là làm thủ công. Bây giờ mình dạy trợ lý tự chạy, để mỗi sáng hoặc mỗi đầu tuần nó tự gửi cho mình một bản kế hoạch nháp."

[Chỉ vào nút Scheduled/Tasks. Cả lớp làm theo.]

> "Anh chị mở tính năng đặt lịch [em chỉ vị trí trên màn hình], chọn tạo một tác vụ tự chạy. Đặt thời gian lặp lại - ví dụ mỗi Thứ 2 lúc 8 giờ sáng - rồi dán câu lệnh này làm nội dung cho nó tự chạy:"

```
Đầu tuần rồi. Hãy hỏi tôi danh sách việc tuần này và số giờ làm việc thực có, sau đó
lập kế hoạch tuần có ưu tiên A/B/C, chỉ ra 1 việc quan trọng nhất và cảnh báo nếu quá
tải. Nếu tôi đã có danh sách việc quen thuộc từ trước, cứ dựa vào đó và hỏi thêm việc mới.
```

> "Đặt xong, cứ đến sáng Thứ 2 là trợ lý tự nhắc và bắt đầu lập kế hoạch, mình không phải nhớ mở nữa. Ai thích lập kế hoạch theo ngày thì đặt lặp lại mỗi sáng, đổi chữ 'tuần' thành 'hôm nay' trong câu lệnh."

> "Em lưu ý một câu về kỳ vọng: trợ lý tự chạy để NHẮC và DỰNG BẢN NHÁP kế hoạch, còn quyết định cuối cùng vẫn là anh chị. Nó không tự đi làm việc thay mình, nó chuẩn bị sẵn để mình duyệt cho nhanh."

[Nếu tài khoản của một số anh chị chưa thấy nút đặt lịch: trợ giảng hướng dẫn cách thay thế - lưu sẵn câu lệnh ở Phần 5 vào ghi chú, sáng đầu tuần dán vào chạy. Vẫn giữ được thói quen lập kế hoạch đều đặn.]

### Phần 6 [41:00 - 45:00] - Lưu và giao bài về nhà

> "Tin vui: cả bộ não lẫn lịch tự chạy đều lưu trong tài khoản Claude của anh chị. Mai mở lại Project 'Trợ lý Lập kế hoạch' là dùng ngay, lịch đã đặt vẫn chạy đúng giờ."

**Bài tập về nhà buổi 4:**
1. Lập kế hoạch **tuần tới** bằng trợ lý, với danh sách việc thật và số giờ làm việc thực có.
2. **Đặt 1 lịch tự chạy** (mỗi sáng, hoặc mỗi Thứ 2) để trợ lý tự nhắc lập kế hoạch.
3. Thử yêu cầu trợ lý **sắp lại ưu tiên** ít nhất 1 lần cho sát ý mình.
4. Đăng vào nhóm 1 câu: "trợ lý lập kế hoạch giúp tôi tiết kiệm khoảng ... phút mỗi sáng."

> "Ngày mai là buổi cuối của Tuần 1. Mình sẽ GHÉP cả bốn tính năng đã học - bộ não, tài liệu, trí nhớ, tự chạy - vào một trợ lý viết báo cáo hoàn chỉnh. Anh chị đã đi được ba phần tư chặng Mức 1 rồi. Hẹn gặp anh chị 8 giờ tối mai. Cảm ơn anh chị."

[Kết thúc buổi. Trợ giảng gửi lại file agent + danh sách việc mẫu vào nhóm lớp.]

---

## C. Checklist chuẩn bị của giảng viên

- [ ] Slide tiêu đề + slide "bài toán ngập việc, không biết làm gì trước".
- [ ] Claude đăng nhập sẵn; **đã thử trước nút Scheduled/Tasks** (đặt lịch tự chạy) để biết đúng vị trí và cách thao tác trên tài khoản.
- [ ] Gửi vào nhóm TRƯỚC giờ học: file agent lập kế hoạch (Phần 2) + danh sách việc mẫu (Phần 3).
- [ ] Chuẩn bị phương án thay thế nếu tài khoản học viên chưa có nút đặt lịch (lưu câu lệnh, chạy thủ công đầu tuần).
- [ ] Trợ giảng trực chat hỗ trợ khi cả lớp đặt lịch tự chạy.
- [ ] Link ghi hình buổi học (gửi anh chị ca không dự trực tiếp được).

## D. Tiêu chí hoàn thành buổi 4 (đối chiếu cam kết "đo được hiệu quả")

- Anh chị nạp được bộ não và cho ra bản kế hoạch có ưu tiên A/B/C, có đúng 1 ưu tiên số 1.
- Anh chị lập được kế hoạch cho tuần thật của mình + chỉnh ưu tiên ít nhất 1 lần.
- Anh chị đặt được 1 lịch tự chạy (hoặc nắm được cách chạy thủ công thay thế).
- Anh chị nêu được ước lượng thời gian tiết kiệm mỗi sáng khi lập kế hoạch (phục vụ mẫu báo cáo hiệu quả trước - sau của khóa).
