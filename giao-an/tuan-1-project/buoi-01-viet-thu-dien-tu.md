# Buổi 01 - AI Agent viết thư điện tử (kịch bản hands-on)

> **Tuần 1 - Thứ 2** | Thời lượng: 45 phút | Công cụ: Claude Project (claude.ai)
> **Mô tả trên landing page:** "Viết và phản hồi thư điện tử chuyên nghiệp".
> **Mô hình buổi học:** HANDS-ON. Trình tự: Giới thiệu -> Pain point -> rồi mới vào thực hành từng bước. Giảng viên và học viên làm **song song** - giảng viên hướng dẫn 1 thao tác, cả lớp làm ngay trên máy mình, xong mới qua bước sau.
> **Buổi 1 đặc biệt:** agent viết thư được **cung cấp sẵn**, học viên chỉ tải về và nạp vào Claude (chưa phải tự xây). Các buổi sau mới học cách tự dựng bộ não agent.
> **Định vị công cụ (nói thẳng với học viên):** buổi này dùng **Claude Project** trên claude.ai - bản dễ nhất, không cài đặt gì, coi như một **trợ lý** cấu hình sẵn cho việc văn phòng nhẹ. Đây là **bước khởi động / bộ đệm** của khóa; khái niệm "AI Agent" đúng chuẩn kỹ thuật (Claude Code subagent, agent team) sẽ được nâng lên ở các buổi sau. Giảng viên phải nói rõ điều này ngay Phần 1 để học viên hiểu đúng, không tưởng Project là agent đầy đủ.
> **Xưng hô:** giảng viên xưng **"em"**, gọi học viên là **"anh chị"**.
> **Định dạng script:** ngoặc vuông `[ ]` là chỉ dẫn thao tác cho giảng viên (không đọc to); ngoặc kép `"..."` là lời giảng viên nói gần như nguyên văn; mỗi khối ``` là prompt/nội dung copy-dán được, dùng đúng tại bước đó.

---

## A. Chuẩn bị trước buổi học

**Giảng viên chuẩn bị:**
- Tài khoản Claude (claude.ai) đăng nhập sẵn, mở tab trắng để cả lớp bám theo màn hình.
- Kiểm tra Projects trong tài khoản có bật không (để hướng dẫn đúng cả 2 cách nạp agent).
- **File agent viết thư (cung cấp sẵn)** + link tải, gửi vào nhóm chat lớp trước giờ học để anh chị tải về.
- 4 khối prompt tình huống (khối ở Phần 3 và Phần 4) gửi kèm vào nhóm để anh chị copy nhanh.
- 1 slide tiêu đề + 1 slide "bài toán thực tế anh Minh".

**Học viên cần có sẵn (nhắn trong nhóm trước 1 tiếng):**
- Máy tính, tài khoản Claude đã đăng nhập.
- Nghĩ sẵn 1 email công việc thật hay phải viết (xin nghỉ phép, phản hồi khách, mời họp...).

**Mục tiêu buổi học (giảng viên nắm, không đọc hết):**
- Anh chị hiểu "AI Agent" trong khóa này = một trợ lý được hướng dẫn sẵn (buổi này dựng bằng Claude Project, coi như bước khởi động), dùng lại mỗi ngày, theo công thức đầu vào - đầu ra - cách kiểm tra.
- Mỗi anh chị nạp được agent viết thư và tự viết 1 email thật hoàn chỉnh ngay trong buổi.

---

## B. Kịch bản hands-on (45 phút)

### Phần 1 [00:00 - 08:00] - Giới thiệu và điểm đau (cùng trò chuyện, chưa dùng máy)

[Chia sẻ slide tiêu đề. Nói chậm, ấm, tạo không khí.]

> "Em chào anh chị. Chào mừng anh chị đến với buổi đầu tiên của hành trình 30 ngày làm chủ AI Agent. Mỗi buổi mình gói gọn 45 phút, và nguyên tắc của lớp là: học tới đâu có ngay công cụ dùng được tới đó. Kết thúc 45 phút hôm nay, mỗi anh chị sẽ có một trợ lý riêng chuyên viết email cho mình."

[Hỏi tương tác, chờ học viên gõ chat.]

> "Nhưng trước khi làm, em muốn anh chị cùng nhìn lại một chuyện rất quen. Anh chị thử nhớ xem: một ngày đi làm, mình mất bao nhiêu thời gian chỉ để viết và trả lời email? Anh chị gõ nhanh con số vào khung chat giúp em - 30 phút, 1 tiếng, hay 2 tiếng?"

[Chờ 15-20 giây, đọc to vài con số anh chị gõ.]

> "Em thấy có anh chị ghi 1 tiếng, có anh chị ghi 2 tiếng. Rất thật. Email ngốn thời gian không phải vì nó khó, mà vì mỗi lần viết mình lại phải nghĩ lại từ đầu: mở lời sao cho lịch sự, diễn đạt sao cho rõ, kết sao cho chuyên nghiệp, rồi đọc đi đọc lại sợ sai."

[Chuyển slide "bài toán thực tế".]

> "Em kể anh chị nghe một tình huống rất đời. Anh Minh, nhân viên kinh doanh, sáng nay nhận email khách phàn nàn vì đơn hàng giao trễ 3 ngày. Anh phải trả lời, nhưng loay hoay gần 20 phút: viết nhẹ quá thì sợ khách nghĩ mình xem thường, viết nặng quá thì mất khách. Cuối cùng anh gửi một email cụt lủn, và khách càng khó chịu hơn."

> "Vấn đề ở đây không phải anh Minh kém. Vấn đề là anh chưa có một trợ lý biết sẵn cách viết email chuẩn cho từng tình huống. Nhiều anh chị chắc từng thử nhờ AI viết email rồi đúng không? Và thấy nó viết chung chung, sáo rỗng, phải sửa lại gần hết. Em nói thật lòng: không phải AI dở, mà là mình chưa hướng dẫn nó tử tế. Cùng một AI, nếu được hướng dẫn đúng, nó viết email chuyên nghiệp và nhanh hơn mình tự viết rất nhiều."

> "Và đó chính là thứ hôm nay anh chị sẽ có trong tay - em nói thẳng luôn để anh chị hiểu đúng ngay từ đầu. Công cụ mình dùng hôm nay tên là Claude Project: hiểu nôm na là mình biến Claude thành một trợ lý riêng, chuyên đúng một việc - ở đây là viết email. Trong khóa, những trợ lý kiểu này mình quen gọi chung là 'AI Agent'. Buổi đầu tiên em cố tình chọn công cụ dễ nhất, không cài đặt gì cho ai, để cả lớp làm quen cách giao việc có cấu trúc cho AI. Những buổi sau, khi anh chị quen tay, mình sẽ nâng dần lên các agent mạnh hơn và tự động hơn. Còn với việc văn phòng hằng ngày như email, một trợ lý thế này là đã quá đủ dùng rồi."

[Chiếu slide "3 mức trợ lý AI - hôm nay mình ở Mức 1". Nói nhanh, không sa đà kỹ thuật.]

> "Để anh chị hình dung cả hành trình 30 ngày, em cho xem bảng này. Trợ lý AI có 3 mức, đi từ dễ tới khó. Em ví von cho dễ nhớ: Mức 1 là thuê MỘT người phụ việc quen tay; Mức 2 là người đó TỰ BIẾT việc, gặp đúng loại là tự làm; Mức 3 là cả một NHÓM phụ việc, mỗi người lo một khâu."

| Tiêu chí | Mức 1 - Trợ lý riêng (HÔM NAY) | Mức 2 - Trợ lý tự bật | Mức 3 - Đội trợ lý |
|---|---|---|---|
| Tên công cụ | Claude Project | Skill (kỹ năng cài sẵn) | Agent team (đội agent) |
| Chạy ở đâu, cài gì | Ngay trên web Claude, KHÔNG cài gì | Cần cài công cụ trên máy | Cũng cài công cụ trên máy |
| Làm 1 việc hay cả đội | 1 trợ lý lo 1 việc | 1 kỹ năng, tự bật đúng lúc | Nhiều trợ lý con phối hợp trọn quy trình |
| Tự nhớ, tự làm nhiều bước | Nhớ trong Project; đang thêm khả năng chạy theo lịch | Theo kỹ năng đã cài | Mạnh nhất: mỗi con có bộ nhớ riêng, tự dùng công cụ, làm nhiều bước rồi bàn giao con kế |
| Ví dụ dễ hình dung | Trợ lý viết email hôm nay | Quăng tài liệu vào là tự tóm tắt | Báo cáo tháng: 1 con gom số liệu, 1 con phân tích, 1 con viết, 1 con làm slide - nối nhau tự động |
| Độ khó | Rất dễ | Trung bình | Cao hơn (buổi sau) |

> "Anh chị chưa cần nhớ hết bảng này đâu - chỉ cần nắm một ý: hôm nay mình ở Mức 1, dễ nhất, không cài đặt gì, và riêng việc viết email thì Mức 1 đã dư sức. Các mức sau mình học dần, không áp lực. Ai muốn hiểu sâu hơn thì cuối tài liệu em có phần giải thích đầy đủ."

[Ghi chú GV: bản lý thuyết đầy đủ - ví von, giải thích từng mức, ví dụ văn phòng - nằm ở Mục E cuối script. Buổi chính chỉ chiếu bảng này ~1 phút; dùng Mục E khi lớp hỏi sâu hoặc gửi học viên đọc thêm.]

> "Tin vui: trợ lý viết thư này em đã chuẩn bị sẵn cho anh chị. Anh chị không phải tự xây gì cả, chỉ cần tải về, nạp vào Claude là dùng được ngay - không lập trình một dòng nào. Giờ mình bắt đầu, anh chị mở máy tính ra nhé."

### Phần 2 [08:00 - 15:00] - Nạp agent có sẵn vào Claude (cả lớp cùng làm)

> "Anh chị mở claude.ai và đăng nhập giúp em. Ai vào được màn hình chat rồi thì gõ '1' vào khung chat của lớp để em nắm nhịp cả lớp."

[Chờ đa số gõ 1. Trợ giảng hỗ trợ ai chưa vào được.]

> "Em vừa gửi vào nhóm lớp một file agent viết thư kèm link tải. Anh chị tải file đó về và mở ra - bên trong là 'bộ não' của agent, tức bộ hướng dẫn em đã viết sẵn để Claude biết cách viết email chuẩn cho mình. Anh chị yên tâm, buổi nay mình chỉ dùng, chưa cần tự viết cái này."

> "Giờ nạp nó vào Claude. Có 2 cách, anh chị làm theo cách hợp với tài khoản của mình:"

> "Cách 1 (khuyên dùng, giữ được lâu dài): nhìn cột bên trái, bấm 'Projects', tạo project mới, đặt tên 'Trợ lý Email công việc'. Rồi copy toàn bộ nội dung trong file em gửi, dán vào ô 'Instructions' của project, lưu lại. Từ nay mỗi lần cần viết email, anh chị chỉ mở đúng project này."

> "Cách 2 (nếu tài khoản chưa có Projects): anh chị mở một cuộc trò chuyện mới, dán toàn bộ nội dung file vào ô chat rồi gửi. Cũng chạy y hệt, chỉ là xong một phiên thì lần sau dán lại."

[Chiếu nội dung file agent lên màn hình để anh chị đối chiếu - không cần đọc to hết.]

```
VAI TRÒ
Bạn là trợ lý soạn thảo thư điện tử công việc cho nhân viên văn phòng Việt Nam. Bạn thành thạo văn phong công sở và hành chính tiếng Việt (và tiếng Anh khi được yêu cầu), hiểu tôn ti quan hệ nơi làm việc (cấp trên, đồng nghiệp, khách hàng, đối tác, nhà cung cấp) và biết điều chỉnh cách xưng hô, giọng văn cho phù hợp từng đối tượng.

NHIỆM VỤ
Biến ý định thô của tôi thành một email hoàn chỉnh, đúng mục tiêu, đúng giọng, đủ lịch sự và rõ lời đề nghị - sẵn sàng gửi sau khi tôi rà soát nhanh.

ĐẦU VÀO (thông tin tôi sẽ cung cấp)
Bắt buộc:
- Người nhận: là ai, quan hệ (sếp, đồng nghiệp, khách hàng, đối tác, nhà cung cấp).
- Mục tiêu email: sau khi đọc, tôi muốn người nhận làm gì hoặc hiểu gì.
Tùy chọn:
- Tình huống / bối cảnh; số liệu, mốc thời gian, điểm bắt buộc phải nêu.
- Giọng điệu mong muốn (trang trọng / thân thiện - chuyên nghiệp / ngắn gọn / dứt khoát).
- Ngôn ngữ (Việt/Anh); tên và chức danh ký cuối thư; nội dung email cần trả lời (nếu là email phản hồi).
Nếu thiếu thông tin bắt buộc, hãy hỏi lại tôi tối đa 3 câu ngắn gọn trước khi viết, tuyệt đối không tự bịa.

QUY TRÌNH XỬ LÝ
1. Xác định mục tiêu email và hành động mong muốn ở người nhận.
2. Xác định quan hệ và mức trang trọng, từ đó chọn cách xưng hô và giọng văn đúng chuẩn công sở Việt Nam.
3. Chọn cấu trúc phù hợp loại email (đề nghị, thông báo, xin lỗi, phản hồi, cảm ơn, từ chối khéo, nhắc việc...).
4. Viết theo đúng ĐỊNH DẠNG ĐẦU RA bên dưới.
5. Tự rà theo BẢNG KIỂM trước khi đưa kết quả cho tôi.

ĐỊNH DẠNG ĐẦU RA (chuẩn hành chính Việt Nam)
Tiêu đề: <ngắn gọn, nêu rõ nội dung, khoảng 6-12 từ; kèm mã hồ sơ/ngày nếu cần>

Kính gửi <Ông/Bà + chức danh hoặc tên người nhận>,        (nội bộ, thân mật thì dùng "Chào <tên>,")

<Câu mở: nêu ngay mục đích email trong 1-2 câu.>

<Thân bài: 1-3 đoạn ngắn, hoặc gạch đầu dòng nếu nhiều ý; nêu đủ bối cảnh, số liệu, mốc thời gian cần thiết.>

<Lời đề nghị / kêu gọi hành động rõ ràng, kèm thời hạn nếu có.>

Trân trọng,        (hoặc "Trân trọng cảm ơn," / "Thân mến," tùy mức thân mật)
<Họ tên> - <Chức danh> - <Đơn vị>
<Điện thoại / Email nếu cần>

QUY TẮC & AN TOÀN
- Không bịa số liệu, cam kết, ngày tháng, tên người khi tôi chưa cung cấp. Chỗ nào còn thiếu, để trong ngoặc vuông ví dụ [số hợp đồng], [ngày] để tôi tự điền.
- Văn phong lịch sự, đúng mực, súc tích; tránh viết tắt tùy tiện, tránh sáo rỗng và cảm xúc thái quá.
- Tình huống nhạy cảm (phàn nàn, từ chối, xin lỗi, nhắc công nợ): giữ giọng bình tĩnh, tôn trọng, thiện chí.
- Chỉ soạn bản nháp, không tự gửi thay tôi. Nếu nội dung có rủi ro pháp lý hoặc ràng buộc hợp đồng, nhắc tôi rà soát kỹ.
- Độ dài mặc định khoảng 100-150 chữ, trừ khi tôi yêu cầu khác.

BẢNG KIỂM (luôn kèm ở cuối, dưới tiêu đề "Bảng tự kiểm trước khi gửi")
- [ ] Tiêu đề đúng nội dung, không mơ hồ.
- [ ] Câu đầu đã nêu rõ mục đích.
- [ ] Xưng hô và giọng văn đúng quan hệ với người nhận.
- [ ] Có một lời đề nghị / kêu gọi hành động rõ ràng, kèm thời hạn nếu cần.
- [ ] Không lỗi chính tả, không dài dòng, không lộ thông tin nhạy cảm thừa.
- [ ] Không còn ô [ ] nào chưa điền, không có thông tin bịa.

ĐẦU RA MẪU (tham khảo văn phong, không sao chép cứng; các chỗ <...> để người dùng tự điền)
Tiêu đề: Xin nghỉ phép 2 ngày (<ngày bắt đầu> - <ngày kết thúc>)

Kính gửi <chức danh/tên cấp trên>,

Em viết email xin phép nghỉ 2 ngày, <ngày bắt đầu> và <ngày kết thúc>, để giải quyết việc gia đình.

Trong thời gian nghỉ, em đã bàn giao các đầu việc đang xử lý cho <đồng nghiệp được bàn giao> và sẽ theo dõi email khi cần. Em sẽ hoàn tất báo cáo tuần trước khi nghỉ.

Mong anh/chị xem xét và duyệt giúp em. Em cảm ơn anh/chị.

Trân trọng,
<tên_học_viên> - <chức danh>

Bảng tự kiểm trước khi gửi
- [x] Tiêu đề đúng nội dung.
- [x] Câu đầu nêu rõ mục đích (xin nghỉ phép).
- [x] Xưng hô đúng (em - cấp trên).
- [x] Có đề nghị rõ (mong duyệt).
- [x] Không lỗi, không lộ thông tin thừa.

KHỞI ĐỘNG
Khi đã hiểu, hãy trả lời ngắn gọn rằng bạn đã sẵn sàng và hỏi tôi thông tin của email đầu tiên.
```

> "Anh chị để ý nhanh: file này có đúng công thức mình dùng suốt 30 ngày - đầu vào, đầu ra, cách kiểm tra. Buổi nay chưa cần hiểu sâu từng dòng, cứ nạp vào đã, những buổi sau mình sẽ học cách tự viết ra bộ não này. Nạp xong, Claude báo 'Tôi đã sẵn sàng...'. Ai thấy nó báo sẵn sàng thì gõ '1' cho em."

### Phần 3 [15:00 - 23:00] - Cùng chạy thử agent lần đầu (chung 1 tình huống)

> "Giờ mình cùng chạy thử để anh chị thấy sức mạnh của nó. Mình quay lại đúng tình huống anh Minh đầu buổi - khách phàn nàn giao trễ. Anh chị copy đoạn này, dán vào agent vừa nạp rồi gửi:"

```
Người nhận: chị Lan, khách hàng thân thiết.
Tình huống: đơn hàng số 1088 giao trễ 3 ngày do kho thiếu hàng.
Mục tiêu: xin lỗi chân thành, giải thích ngắn gọn, đề xuất giảm 10% cho đơn kế tiếp.
Giọng: chân thành, chuyên nghiệp.
```

[Chờ cả lớp chạy. Mời 1 anh chị dán kết quả vào chat để đọc chung.]

> "Anh chị đọc kết quả xem. Chỉ 4 dòng thông tin, mà nó cho ra một email đầy đủ: tiêu đề rõ, chào đúng tên chị Lan, có xin lỗi, có giải thích, có đề xuất giảm 10%, có kết và chữ ký. Cuối email nó còn tự đưa 'Bảng tự kiểm trước khi gửi'. Đây đúng là thứ anh Minh cần mà không có, nên mới loay hoay 20 phút."

> "Điểm mấu chốt: agent này em viết sẵn một lần, anh chị dùng cho vô số email khác nhau. Lần sau chỉ đổi 4 dòng thông tin thôi. Giờ tới lượt anh chị làm với email thật của chính mình."

### Phần 4 [23:00 - 35:00] - Anh chị tự viết email thật của mình

> "Bước này mỗi anh chị làm với một email công việc thật đang cần viết. Cách đưa thông tin luôn là 4 dòng, giống hệt lúc nãy. Anh chị copy khung này, điền thông tin của mình vào rồi gửi:"

```
Người nhận: [ai + quan hệ, ví dụ: sếp trực tiếp / khách hàng / đồng nghiệp]
Tình huống: [chuyện gì đang xảy ra]
Mục tiêu: [đọc xong anh chị muốn họ làm hoặc hiểu gì]
Giọng: [trang trọng / thân thiện - chuyên nghiệp / ngắn gọn]. Ký tên: [Họ tên] - [Chức danh].
```

> "Anh chị nào chưa nghĩ ra email của mình thì chọn 1 trong 3 tình huống có sẵn dưới đây, copy nguyên là chạy được ngay, khỏi điền:"

**Tình huống A - Xin nghỉ phép (gửi sếp):**
```
Người nhận: anh Minh, trưởng phòng của tôi.
Tình huống: cần nghỉ 2 ngày thứ Năm và thứ Sáu (10-11/7) vì việc gia đình; đã bàn giao việc cho chị Lan.
Mục tiêu: xin sếp duyệt cho nghỉ phép.
Giọng: trang trọng, tôn trọng. Ký tên: [Họ tên] - [Chức danh].
```

**Tình huống B - Mời họp và xin xác nhận tham dự (nội bộ):**
```
Người nhận: trưởng các phòng Kinh doanh, Marketing, Vận hành.
Tình huống: họp tổng kết tháng lúc 9h thứ Hai tuần sau, phòng họp tầng 3, mỗi phòng chuẩn bị 3 số liệu chính.
Mục tiêu: mời họp và đề nghị mỗi phòng xác nhận tham dự trước 17h thứ Sáu.
Giọng: rõ ràng, đúng mực. Ký tên: [Họ tên] - [Chức danh].
```

**Tình huống C - Từ chối khéo một đề nghị hợp tác:**
```
Người nhận: đối tác vừa gửi lời mời hợp tác.
Tình huống: đề nghị hay nhưng chưa phù hợp thời điểm của công ty.
Mục tiêu: từ chối lịch sự, để ngỏ khả năng hợp tác sau này.
Giọng: trân trọng, thiện chí. Ký tên: [Họ tên] - [Chức danh].
```

[Đi một vòng qua chat, gọi tên 1-2 anh chị hỏi thăm, gỡ vướng tại chỗ.]

> "Anh Tuấn ơi, email ra ổn không ạ? ... Nếu nó viết dài quá thì mình chỉnh ở bước sau nhé, cứ để đó. Anh chị nào có email đầu tiên ưng ý thì gõ 'xong' vào chat cho em."

### Phần 5 [35:00 - 41:00] - Cùng tinh chỉnh và kiểm tra trước khi gửi

> "Email lần đầu hiếm khi hoàn hảo ngay - và đây là lúc anh chị dạy agent nghe lời. Anh chị thử ngay 1 trong các câu chỉnh này trên email vừa ra:"

```
Rút gọn còn khoảng 120 chữ, giữ đủ ý.
```
```
Đổi sang giọng thân thiện hơn, bớt trang trọng.
```
```
Viết thêm 1 phương án ngắn gọn hơn để tôi chọn.
```

> "Anh chị thấy chưa, muốn chỉnh bao nhiêu lần cũng được. Giờ tới bước không được quên: KIỂM TRA. Nhìn 'Bảng tự kiểm' agent đưa ở cuối email, đọc từng dòng - đúng tên người nhận chưa, có lời kêu gọi hành động chưa, giọng hợp chưa. AI hỗ trợ mình, nhưng người bấm gửi và chịu trách nhiệm cuối cùng vẫn là anh chị."

> "Nhân tiện, 3 lỗi anh chị hay gặp tuần này để dùng cho mượt: (1) email nghe sáo, giả tạo - thêm mô tả giọng cụ thể như 'gần gũi như đồng nghiệp lâu năm'; (2) agent bịa số hoặc ngày - nhắc lại 'đừng bịa, chỗ thiếu để [ ] tôi điền'; (3) quên kiểm tra - luôn đọc bảng tự kiểm rồi mới gửi."

### Phần 6 [41:00 - 45:00] - Lưu agent và giao bài về nhà

> "Anh chị vừa có trong tay AI Agent đầu tiên và dùng nó viết email thật. Nhớ giữ nó lại để mai dùng tiếp:"

- Dùng Project: nó tự lưu, mai mở lại là dùng ngay.
- Dùng chat thường: giữ file agent em gửi, mai dán lại là xong.

**Bài tập về nhà buổi 1:**
1. Dùng agent viết **3 email thật** trong công việc ngày mai (1 gửi sếp, 1 gửi đồng nghiệp, 1 gửi khách/đối tác).
2. Mỗi email thử **2 giọng** (trang trọng và thân thiện) rồi chọn bản ưng ý.
3. Chụp màn hình 1 email đẹp nhất, đăng vào nhóm lớp kèm câu: "hôm nay agent giúp tôi tiết kiệm khoảng ... phút."

> "Ngày mai mình xây tiếp agent thứ hai - tóm tắt tài liệu dài thành bảng ý chính, hợp với anh chị nào hay phải đọc văn bản, hợp đồng, tài liệu dài. Hẹn gặp lại anh chị 8 giờ tối mai. Cảm ơn anh chị, chúc buổi tối vui."

[Kết thúc buổi. Trợ giảng gửi lại file agent + link ghi hình vào nhóm lớp.]

---

## C. Checklist chuẩn bị của giảng viên

- [ ] Slide tiêu đề buổi 1 + slide "bài toán thực tế anh Minh".
- [ ] Slide "3 mức trợ lý AI" (bảng ở Phần 1) - chiếu nhanh ~1 phút, chỉ để học viên thấy lộ trình, không sa đà kỹ thuật.
- [ ] Tài khoản Claude đăng nhập sẵn; đã kiểm tra Projects bật hay không.
- [ ] Đã gửi vào nhóm chat lớp TRƯỚC giờ học: file agent viết thư (có sẵn) + link tải + 4 khối prompt tình huống (Phần 3, Phần 4).
- [ ] Trợ giảng trực chat để gỡ vướng khi cả lớp làm song song.
- [ ] Link ghi hình buổi học (gửi anh chị ca không dự trực tiếp được).

## D. Tiêu chí hoàn thành buổi 1 (đối chiếu cam kết "đo được hiệu quả")

- Anh chị nạp được agent viết email và chạy ra kết quả.
- Anh chị tự tạo tối thiểu 1 email hoàn chỉnh trong buổi.
- Anh chị nêu được ước lượng thời gian tiết kiệm (phục vụ mẫu báo cáo hiệu quả trước - sau của khóa).

---

## E. Phần lý thuyết mở rộng: 3 mức trợ lý AI (bản đầy đủ)

> Buổi chính chỉ chiếu bảng rút gọn ở Phần 1 (~1 phút). Mục này là bản đầy đủ, dùng khi: (a) lớp tò mò muốn hiểu sâu, hoặc (b) gửi học viên đọc thêm sau buổi. Vẫn viết bằng ngôn ngữ đời thường, không cần biết lập trình. Mục tiêu: học viên hiểu mình đang ở đâu trong bức tranh lớn, và "AI Agent" thật ra có nhiều mức.

### 1. Ba mức, ví von cho dễ nhớ

- **Mức 1 - Trợ lý riêng:** như thuê MỘT người phụ việc quen tay. Mình giao rõ việc, họ làm gọn từng lần. Đây là mức của buổi hôm nay.
- **Mức 2 - Trợ lý tự bật:** người phụ việc đó giờ TỰ BIẾT việc - hễ gặp đúng loại việc là tự ra tay, mình không phải nhắc từng lần.
- **Mức 3 - Đội trợ lý:** không còn một người, mà là cả một NHÓM. Mỗi trợ lý con lo một khâu, phối hợp chạy trọn một quy trình từ đầu đến cuối.

### 2. Bảng so sánh đầy đủ

| Tiêu chí | Mức 1 - Trợ lý riêng | Mức 2 - Trợ lý tự bật | Mức 3 - Đội trợ lý |
|---|---|---|---|
| Tên gọi công cụ | Claude Project | Skill (kỹ năng cài sẵn) | Agent team (đội agent / agent phối hợp) |
| Chạy ở đâu, cài gì | Ngay trên web hoặc app Claude, KHÔNG cài gì | Cần cài công cụ Claude Code trên máy tính | Cũng chạy trên Claude Code (máy tính) |
| Mình phải làm gì để có | Tạo 1 Project, dán bộ hướng dẫn là xong | Bỏ "kỹ năng" vào máy, AI tự bật khi gặp đúng việc | Dựng nhiều trợ lý con và cách chúng phối hợp |
| Làm 1 việc hay cả đội | 1 trợ lý lo 1 việc | 1 kỹ năng, tự kích hoạt đúng lúc | Nhiều trợ lý con phối hợp, chạy trọn quy trình |
| Tự nhớ + tự làm nhiều bước | Nhớ trong Project; đang có thêm khả năng tự chạy theo lịch | Theo kỹ năng đã cài | Mạnh nhất: mỗi con có bộ nhớ riêng, tự dùng công cụ, tự làm nhiều bước rồi bàn giao con kế |
| Ví dụ dễ hình dung | Trợ lý viết email của buổi hôm nay | Bật "kỹ năng tóm tắt": quăng tài liệu vào là tự tóm tắt | Làm báo cáo tháng: con gom số liệu -> con phân tích -> con viết -> con làm slide, nối nhau |
| Độ khó | Rất dễ (ai cũng làm được) | Trung bình (cần cài đặt) | Cao hơn - học ở các buổi sau của khóa |

### 3. Giải thích từng mức (đời thường)

- **Mức 1 - Trợ lý riêng (Project) - hôm nay:** đây là mức dễ nhất và cũng đủ dùng cho hầu hết việc văn phòng lặp đi lặp lại. Mình "thuê" một trợ lý chuyên một việc (viết email, tóm tắt, ghi biên bản...), giao thông tin theo công thức đầu vào - đầu ra - cách kiểm tra, và dùng lại mỗi ngày. Không cài đặt, không lập trình.

- **Mức 2 - Trợ lý tự bật (Skill):** thay vì mỗi lần phải mở đúng trợ lý, mình cài sẵn "kỹ năng" vào công cụ; khi mình nói trúng loại việc, AI tự bật kỹ năng đó lên làm. Tiện hơn nhưng cần cài công cụ trên máy, nên hợp với ai chịu khó một chút về kỹ thuật.

- **Mức 3 - Đội trợ lý (Agent team):** đây mới là "AI Agent" đúng nghĩa nhất. Không phải một trợ lý, mà là cả một đội, mỗi con giỏi một khâu và tự bàn giao cho nhau. Ví dụ trong nghiên cứu: một con đi tìm tài liệu, một con xử lý số liệu, một con phân tích, một con viết bản nháp, một con dựng slide - chạy nối tiếp gần như tự động. Ví dụ văn phòng: cả quy trình "từ số liệu thô đến báo cáo tháng có slide" giao cho một đội agent lo trọn gói.

### 4. Vì sao buổi này chọn Mức 1

Dân văn phòng cần thắng nhanh, không muốn vướng cài đặt. Riêng việc lặp lại như email, tài liệu, biên bản, một trợ lý Mức 1 đã tiết kiệm rất nhiều thời gian. Quan trọng hơn: khi anh chị quen tư duy "giao việc có cấu trúc" (đầu vào - đầu ra - cách kiểm tra) ở Mức 1, thì lên Mức 2 và Mức 3 rất nhẹ, vì tư duy giống nhau, chỉ khác công cụ.

### 5. Cuối khóa (Tuần 4) mình chạm tới Mức 3

Tuần 4 của khóa có tên "Ghép thành Workspace cá nhân tự động" - đó chính là lúc mình gom nhiều trợ lý đã học thành một hệ thống làm việc, tiến gần tới Mức 3. Nói cách khác, buổi hôm nay là viên gạch đầu tiên; đích đến là một "đội AI Agent" chạy việc cho anh chị.
