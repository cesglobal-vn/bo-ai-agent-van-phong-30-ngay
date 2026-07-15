# Buổi 03 - AI Agent ghi chú họp (kịch bản hands-on)

> **Tuần 1 - Thứ 4** | Thời lượng: 45 phút | Công cụ: Claude Project (claude.ai)
> **Mô tả trên landing page:** "Biến ghi chú họp lộn xộn thành biên bản có đầu việc; trợ lý nhớ bối cảnh".
> **Mô hình buổi học:** HANDS-ON. Trình tự: Giới thiệu -> điểm đau -> rồi mới vào thực hành từng bước. Giảng viên và học viên làm SONG SONG.
> **Tính năng trọng tâm hôm nay: MEMORY** - trí nhớ bối cảnh: trợ lý nhớ tên phòng ban, dự án, đồng nghiệp qua nhiều cuộc trò chuyện, khỏi khai lại từ đầu. Buổi 1 học Instructions (bộ não), buổi 2 học Context (nạp tài liệu); hôm nay thêm Memory. Vẫn Mức 1 - Project, không cài đặt gì.
> **Xưng hô:** giảng viên xưng **"em"**, gọi học viên là **"anh chị"**.
> **Định dạng script:** ngoặc vuông `[ ]` là chỉ dẫn thao tác (không đọc to); ngoặc kép `"..."` là lời giảng viên nói gần như nguyên văn; mỗi khối ``` là nội dung copy-dán được.

---

## A. Chuẩn bị trước buổi học

**Giảng viên chuẩn bị:**
- Claude đăng nhập sẵn; mở một Project để demo. **Thử trước tính năng Memory** (Settings -> Capabilities -> "Generate memory from chat history") để nắm đúng vị trí bật.
- Gửi TRƯỚC vào nhóm lớp: file agent ghi chú họp (khối "bộ não" ở Phần 2) + 2 ví dụ ghi chú thô (Phần 3 và Phần 4).
- Slide tiêu đề + slide "bài toán sau họp: ai làm gì, hạn nào".

**Học viên cần có sẵn (nhắn nhóm trước 1 tiếng):**
- Máy tính, tài khoản Claude (đã có Project từ buổi 1-2).
- Chuẩn bị sẵn 1 ghi chú họp thật gần đây (ghi tay, tin nhắn, hoặc bản chép), đã ẩn thông tin nhạy cảm.

**Mục tiêu buổi học:**
- Anh chị có 1 trợ lý ghi chú họp: đưa ghi chú lộn xộn, ra biên bản đủ 4 phần (Quyết định / Đầu việc / Thảo luận / Tồn đọng).
- Anh chị biết bật và dùng **Memory**: trợ lý nhớ bối cảnh phòng ban, dự án, đồng nghiệp mà không phải khai lại ở mỗi cuộc trò chuyện.
- Ghi được biên bản cho 1 cuộc họp thật ngay trong buổi.

---

## B. Kịch bản hands-on (45 phút)

### Phần 1 [00:00 - 07:00] - Giới thiệu và điểm đau

[Chào lớp, nối buổi 2.]

> "Em chào anh chị, mình vào buổi thứ ba. Hai buổi qua anh chị đã có trợ lý viết email và trợ lý tóm tắt tài liệu. Hôm nay là trợ lý thứ ba, và mình học thêm một tính năng rất hay của Claude: cho trợ lý một TRÍ NHỚ."

[Slide "bài toán sau họp".]

> "Em hỏi thật: sau một cuộc họp, anh chị có hay rơi vào cảnh này không - họp thì sôi nổi, nhưng xong họp mở lại ghi chú thì rối, không rõ cái gì đã chốt, cái gì còn đang bàn, ai nhận việc nào, hạn khi nào? [Chờ vài phản hồi.] Rồi vài hôm sau có người quên việc, vì lúc đó không ai ghi rõ ràng."

> "Em kể một tình huống rất đời. Chị Mai họp giao ban xong, ghi vội mấy dòng vào điện thoại: 'Long trang chủ 80%, chốt phương án 2, Mai gọi khách, ngân sách 20 triệu chưa chốt...'. Ba ngày sau sếp hỏi 'chốt phương án mấy rồi', chị phải ngồi đọc lại đống ghi chú, không chắc chắn. Ghi thì có ghi, mà không thành biên bản dùng được."

> "Hôm nay mình giải đúng bài đó: dựng một trợ lý biến ghi chú họp lộn xộn thành biên bản gọn gàng, tách rõ 4 phần - cái gì đã quyết, ai làm việc gì hạn nào, đã bàn những gì, và cái gì còn treo. Và mình học một tính năng mới tên là **Memory** - trí nhớ. Nhờ nó, trợ lý nhớ sẵn tên nhóm, tên dự án, tên đồng nghiệp của anh chị, để lần sau ghi biên bản khỏi phải giới thiệu lại từ đầu. Vẫn không cài đặt gì, vẫn trên web Claude. Mình bắt đầu, anh chị mở máy ra nhé."

### Phần 2 [07:00 - 16:00] - Nạp agent ghi chú họp + bật tính năng Memory

**Bước 2a - Nạp "bộ não" cho trợ lý (cả lớp cùng làm):**

> "Đầu tiên, giống các buổi trước, mình cho trợ lý một bộ não. Anh chị vào claude.ai, bấm 'Projects', tạo project mới, đặt tên 'Trợ lý Ghi chú họp'. Rồi copy khối em gửi trong nhóm, dán vào ô Instructions, lưu lại. Ai xong gõ '1'."

[Chiếu khối bộ não để đối chiếu - không đọc to hết.]

```
VAI TRÒ
Bạn là thư ký cuộc họp chuyên nghiệp cho nhân viên văn phòng Việt Nam. Bạn biến nội
dung họp lộn xộn (ghi chú tay, chat, bản chép từ ghi âm) thành biên bản họp gọn, rõ,
có đầu việc và người phụ trách.

NHIỆM VỤ
Từ nội dung họp thô tôi cung cấp, tạo ra một biên bản chuẩn: quyết định đã chốt, đầu
việc (ai - làm gì - hạn chót), thảo luận chính, và tồn đọng cần theo dõi - để sau họp
ai đọc cũng biết chính xác phải làm gì.

ĐẦU VÀO (thông tin tôi sẽ cung cấp)
Bắt buộc:
- Nội dung cuộc họp (ghi chú tay, tin nhắn chat, hoặc bản chép).
Tùy chọn:
- Tên cuộc họp, ngày, thành phần tham dự, mục tiêu họp.
- Danh sách thành viên nhóm (để gán việc đúng người khi ghi chú viết tắt hoặc gọi thân mật).
Nếu tôi không nói rõ, hãy dùng những gì tôi đã cho bạn biết trước đó (tên nhóm, dự án,
thành viên) nếu có; nếu vẫn thiếu, để trống và đánh dấu [cần xác nhận], đừng tự bịa.

QUY TRÌNH XỬ LÝ
1. Xác định chủ đề và mục tiêu cuộc họp.
2. Tách nội dung thành 4 nhóm: Quyết định đã chốt / Đầu việc / Thảo luận & ý kiến / Tồn đọng.
3. Với mỗi đầu việc: xác định người phụ trách - nội dung - hạn chót. Thiếu người hoặc hạn
   thì đánh dấu [cần xác nhận], không đoán bừa.
4. Gom các nội dung còn treo, chưa chốt sang mục Tồn đọng để theo dõi ở cuộc họp sau.
5. Trình bày theo ĐỊNH DẠNG ĐẦU RA; tự rà BẢNG KIỂM trước khi giao.

ĐỊNH DẠNG ĐẦU RA
BIÊN BẢN HỌP - <Tên cuộc họp>
Ngày: <...> | Thành phần: <...> | Mục tiêu: <...>

A. QUYẾT ĐỊNH ĐÃ CHỐT
- ...

B. ĐẦU VIỆC (Action Items)
| # | Nội dung | Người phụ trách | Hạn chót | Ghi chú |
|---|----------|-----------------|----------|---------|
| 1 | ... | ... | ... | ... |

C. THẢO LUẬN CHÍNH / Ý KIẾN
- ...

D. TỒN ĐỌNG & CẦN THEO DÕI
- ...

QUY TẮC & AN TOÀN
- Mọi quyết định và đầu việc phải có trong nội dung gốc, không tự chế thêm.
- Không gán việc cho người không được nhắc tới trong ghi chú; chưa rõ ai làm ghi [cần xác nhận].
- Phân biệt rõ điều "đã chốt" và điều "còn đang bàn, chưa quyết".
- Nếu nội dung họp có thông tin nội bộ nhạy cảm (lương, hợp đồng, khách hàng), nhắc tôi
  cân nhắc trước khi gửi rộng.
- Chỉ soạn bản nháp biên bản, không tự gửi thay tôi.

BẢNG KIỂM (tự rà trước khi giao)
- [ ] Mọi quyết định/đầu việc đều có trong nội dung gốc, không bịa.
- [ ] Mỗi đầu việc có đủ người - việc - hạn (hoặc đã đánh dấu [cần xác nhận]).
- [ ] Phân biệt rõ "đã chốt" và "còn thảo luận".
- [ ] Ngắn gọn, có thể chuyển thẳng thành thông báo hoặc nhắc việc.

KHỞI ĐỘNG
Khi đã hiểu, hãy trả lời ngắn gọn rằng bạn đã sẵn sàng, và hỏi tôi: (1) nội dung cuộc
họp cần ghi biên bản, và nếu đây là lần đầu làm việc cùng tôi - hỏi thêm tên nhóm/phòng
ban, dự án đang làm, và vài thành viên hay xuất hiện trong họp, để những lần sau ghi
biên bản khỏi phải hỏi lại.
```

> "Nạp xong, Claude sẽ báo sẵn sàng và hỏi anh chị vài thông tin nền: tên phòng ban, dự án, vài đồng nghiệp hay xuất hiện trong họp. Anh chị trả lời luôn cho nó - đây chính là lúc mình dạy trợ lý nhớ bối cảnh. Nhưng để nó nhớ được sang cả cuộc trò chuyện khác, mình phải bật tính năng Memory. Giờ tới phần mới của hôm nay."

**Bước 2b - Bật tính năng MEMORY (điểm mới của buổi):**

[Chỉ vào Settings.]

> "Anh chị bấm biểu tượng Settings - bánh răng, thường ở góc trên hoặc trong menu tài khoản. Vào mục **Capabilities**, tìm nút **'Generate memory from chat history'** rồi bật lên. Ai bật xong gõ '2'."

[Cho cả lớp khoảng 1-2 phút. Trợ giảng hỗ trợ ai chưa thấy nút.]

> "Em nói rõ vì sao cần Memory. Mỗi tuần anh chị họp nhiều, mở nhiều cuộc trò chuyện mới. Nếu không có Memory, lần nào cũng phải khai lại 'tôi làm phòng X, dự án Y, nhóm có A B C'. Có Memory rồi, trợ lý nhớ sẵn - mở chat mới vẫn gọi đúng tên người, đúng tên dự án mà mình đã trao đổi trước đó. Lát nữa mình sẽ thử tận mắt điều này ở Phần 4."

### Phần 3 [16:00 - 26:00] - Cùng chạy thử: từ ghi chú lộn xộn ra biên bản

> "Để cả lớp cùng thấy trợ lý làm việc, mình dùng chung một ghi chú họp mẫu. Anh chị copy NGUYÊN khối này - gồm câu lệnh và phần ghi chú thô - dán vào ô chat rồi gửi:"

```
Ghi biên bản họp giúp tôi từ nội dung dưới đây.

Họp giao ban dự án website sáng nay, có mình, Long, Mai, với anh Tuấn sếp.
- Long bảo trang chủ xong 80% rồi, còn phần banner.
- Chốt luôn giao diện trang chủ đi theo phương án 2 (cái màu xanh), khỏi bàn nữa.
- Mai: khách hỏi khi nào go-live, chưa trả lời được. Mai lo liên hệ khách xác nhận lịch, làm sớm.
- Bàn ngân sách quảng cáo tháng sau, Long đề xuất 20 triệu, anh Tuấn nói để xem lại chưa chốt.
- Slide demo cho khách tuần sau: Long nhận làm, xong trước thứ 5.
- Còn vụ tên miền phụ, chưa ai nhận, để đó tính sau.
- Anh Tuấn dặn: nhớ gửi biên bản cho cả nhóm sau họp.
```

[Chờ cả lớp chạy. Đọc chung 1 kết quả.]

> "Anh chị nhìn kết quả. Trợ lý trả về biên bản đủ 4 phần. Em muốn anh chị để ý ba điểm hay:"

> "Một: việc 'chốt phương án 2' nằm ở mục Quyết định đã chốt, còn 'ngân sách 20 triệu' vì anh Tuấn nói để xem lại nên nó xếp vào phần Thảo luận, KHÔNG đưa vào quyết định. Nó phân biệt đúng cái đã chốt và cái còn đang bàn."

> "Hai: chỗ nào thiếu hạn hoặc thiếu người, ví dụ vụ tên miền chưa ai nhận, nó ghi [cần xác nhận] chứ không bịa ra một cái tên."

> "Ba: vụ tên miền chưa ai nhận được đẩy xuống mục Tồn đọng để cuộc họp sau không bị quên."

> "Sức mạnh là hỏi tiếp mà không phải nhập lại. Anh chị thử gõ thêm:"

```
Chuyển phần Đầu việc thành tin nhắn ngắn để tôi gửi luôn vào nhóm Zalo.
```

> "Thấy chưa, nó gói phần đầu việc thành một tin nhắn gọn, gửi nhóm được ngay. Muốn gom các chỗ chưa rõ thành câu hỏi để đi hỏi lại đồng nghiệp thì gõ tiếp:"

```
Chỗ nào [cần xác nhận], liệt kê lại thành danh sách câu hỏi tôi cần hỏi lại đồng nghiệp.
```

### Phần 4 [26:00 - 34:00] - Kiểm chứng MEMORY hoạt động (mở cuộc trò chuyện mới)

> "Giờ tới phần đặc biệt nhất của hôm nay - mình kiểm tra xem trợ lý có thật sự NHỚ không. Anh chị làm theo em từng bước."

> "Bước 1: trong cùng Project 'Trợ lý Ghi chú họp', bấm **New chat** - mở một cuộc trò chuyện MỚI hoàn toàn. Đừng dùng lại đoạn chat cũ, vì mình cố tình thử trí nhớ."

> "Bước 2: dán khối này vào chat mới. Chú ý - em cố tình KHÔNG nhắc lại đây là dự án gì, Long với Mai là ai:"

```
Họp nhanh sáng nay xong rồi, ghi biên bản giúp tôi: Long báo cáo tiến độ ổn, banner sắp
xong. Mai xin thêm 2 ngày để hoàn thành phần liên hệ khách. Còn lại chưa có gì mới.
```

[Chờ cả lớp chạy. Đọc chung 1 kết quả.]

> "Đây là bài kiểm tra Memory. Anh chị KHÔNG hề nhắc đây là dự án Website, cũng không nói Long, Mai là ai. Nếu biên bản vẫn tự điền đúng tên dự án 'Website' và nhận ra Long, Mai - nghĩa là Memory đã hoạt động. Đây chính là khác biệt lớn nhất so với Context ở buổi 2: buổi 2 phải nạp tài liệu vào từng project, còn Memory thì nhớ bối cảnh chung, sang chat mới vẫn nhớ."

> "Nếu trợ lý của ai quên hoặc gọi sai tên, thì kiểm lại: vào Settings, xem Memory đã bật chưa; rồi quay vào chat gõ lại một câu giới thiệu bối cảnh - tên nhóm, dự án, thành viên - cho nó ghi vào trí nhớ lần nữa."

### Phần 5 [34:00 - 41:00] - Thực hành với ghi chú họp thật của anh chị

> "Đến lượt anh chị làm với một ghi chú họp thật của mình. Trước khi làm, em nhắc một câu về bảo mật: nếu cuộc họp có thông tin nhạy cảm - lương, số liệu khách hàng, hợp đồng - anh chị che hoặc xóa phần đó TRƯỚC KHI dán vào."

> "Cách làm: mở Project 'Trợ lý Ghi chú họp' (chat cũ hay mới đều được, vì đã có Memory), copy khung này, dán ghi chú thật vào chỗ trong ngoặc rồi gửi:"

```
Ghi biên bản họp giúp tôi từ nội dung dưới đây. Nếu thiếu người phụ trách hoặc hạn chót
ở việc nào, đánh dấu [cần xác nhận] thay vì đoán.

[dán ghi chú họp thật của anh chị vào đây]
```

> "Anh chị nào chưa mang ghi chú thật thì dùng lại một trong hai ví dụ ở trên, thử thêm biến thể: họp với khách hàng, hoặc họp có nhiều việc còn treo chưa chốt."

[Đi một vòng, gọi tên 1-2 anh chị, gỡ vướng. Nhắc 3 lỗi dưới khi có người hỏi.]

> "3 lỗi anh chị hay gặp tuần này: (1) ghi chú viết tắt tên, trợ lý gán nhầm người - bổ sung tên đầy đủ, ví dụ gõ 'Tên đầy đủ của a.T là anh Tuấn, trưởng phòng', hoặc lưu vào Memory; (2) họp nhiều nội dung rời rạc, không rõ cái nào đã chốt - nhắc trợ lý 'phân biệt rõ giúp tôi phần đã chốt và phần còn đang bàn'; (3) quên kiểm bảng Đầu việc trước khi gửi cả nhóm - luôn đọc lại cột người phụ trách và hạn chót, vì cả nhóm làm theo bảng này, và anh chị mới là người chịu trách nhiệm cuối cùng, không phải AI."

> "Ai có biên bản ưng ý rồi thì gõ 'xong' cho em."

### Phần 6 [41:00 - 45:00] - Lưu và giao bài về nhà

> "Tin vui: cả bộ não (Instructions) lẫn trí nhớ bối cảnh (Memory) đều tự lưu trong tài khoản Claude của anh chị. Mai mở lại Project 'Trợ lý Ghi chú họp' là dùng ngay, không cần giới thiệu lại từ đầu."

**Bài tập về nhà buổi 3:**
1. Dùng trợ lý ghi **2 biên bản họp thật** (họp gần đây, hoặc ghi chú tự chép lại từ một cuộc họp trong tuần).
2. Với 1 biên bản, **mở cuộc trò chuyện mới** và kiểm tra xem trợ lý có nhớ đúng tên dự án / đồng nghiệp mà không cần nhắc lại không. Nếu sai, giới thiệu lại bối cảnh cho Memory.
3. **Đối chiếu bảng Đầu việc** với thực tế cuộc họp: đủ người - việc - hạn chưa, có chỗ nào bị gán nhầm không.
4. Đăng vào nhóm 1 câu: "trợ lý ghi chú họp giúp tôi tiết kiệm khoảng ... phút soạn biên bản."

> "Ngày mai mình xây trợ lý thứ tư - lập kế hoạch: biến danh sách việc rối thành kế hoạch có ưu tiên. Và mình học nốt tính năng thứ tư của Project là Scheduled - cho trợ lý tự chạy theo lịch. Hẹn gặp anh chị 8 giờ tối mai. Cảm ơn anh chị."

[Kết thúc buổi. Trợ giảng gửi lại file agent + 2 ví dụ ghi chú vào nhóm lớp.]

---

## C. Checklist chuẩn bị của giảng viên

- [ ] Slide tiêu đề + slide "bài toán sau họp: ai làm gì, hạn nào".
- [ ] Claude đăng nhập sẵn; **đã thử trước bật Memory** (Settings -> Capabilities -> "Generate memory from chat history").
- [ ] Gửi vào nhóm TRƯỚC giờ học: file agent ghi chú họp (Phần 2) + 2 ví dụ ghi chú thô (Phần 3, Phần 4).
- [ ] Trợ giảng trực chat hỗ trợ khi cả lớp bật Memory và kiểm chứng trí nhớ.
- [ ] Link ghi hình buổi học (gửi anh chị ca không dự trực tiếp được).

## D. Tiêu chí hoàn thành buổi 3 (đối chiếu cam kết "đo được hiệu quả")

- Anh chị nạp được bộ não và cho ra biên bản đủ 4 phần: Quyết định / Đầu việc / Thảo luận / Tồn đọng.
- Anh chị bật được Memory và kiểm chứng trí nhớ hoạt động qua một cuộc trò chuyện mới.
- Anh chị ghi được biên bản cho tối thiểu 1 cuộc họp thật + chỉnh sửa ít nhất 1 lần (đổi thành tin nhắn nhóm hoặc danh sách câu hỏi).
- Anh chị nêu được ước lượng thời gian tiết kiệm khi soạn biên bản (phục vụ mẫu báo cáo hiệu quả trước - sau của khóa).
