# Buổi 07 - Skill: dặn một lần, dùng mãi (kịch bản hands-on)

> **Tuần 2 - Thứ 3** | Thời lượng: 45 phút | Công cụ: Claude (claude.ai / ứng dụng Claude)
> **Mô hình buổi học:** HANDS-ON. Trình tự: Giới thiệu -> điểm đau -> rồi mới vào thực hành từng bước. Giảng viên và học viên làm SONG SONG.
> **Buổi bản lề:** đây là lần đầu lớp gặp khái niệm **Skill**. Vẫn KHÔNG CÀI GÌ - dùng cách "nhờ Claude tự đóng gói". Buổi 8 mới mở nắp ra xem skill thật sự là file gì, và đó là lúc cần Claude Code.
> **Xưng hô:** giảng viên xưng **"em"**, gọi học viên là **"anh chị"**.
> **Định dạng script:** ngoặc vuông `[ ]` là chỉ dẫn thao tác (không đọc to); ngoặc kép `"..."` là lời giảng viên nói gần như nguyên văn; mỗi khối ``` là nội dung copy-dán được.

---

## A. Chuẩn bị trước buổi học

**Giảng viên chuẩn bị:**
- Claude đăng nhập sẵn; **chạy trước trọn bộ 3 bước ở nhà ít nhất 1 lần** (research -> ra file .docx -> đóng gói skill) để biết chỗ nào Claude hay hỏi lại.
- File logo của CES Global (PNG hoặc SVG, nền trắng) để dùng khi demo.
- Gửi TRƯỚC vào nhóm lớp: file `buoi-07-skill-dong-goi-tai-lieu.md` (3 câu lệnh mẫu) + nhắc anh chị chuẩn bị logo công ty mình.
- Slide tiêu đề + slide "mỗi lần nhờ lại phải dặn lại từ đầu".
- **Chuẩn bị link hướng dẫn cài Claude Code** (`00-tong-quan/huong-dan-cai-claude-code.md`) để giao ở cuối buổi - buổi 8 bắt buộc phải có.

**Học viên cần có sẵn (nhắn nhóm trước 1 tiếng):**
- Máy tính, tài khoản Claude.
- **File logo công ty mình** (ảnh PNG hoặc SVG, tốt nhất là nền trắng). Ai không có logo công ty thì lấy tạm một logo bất kỳ để tập.
- Nghĩ trước 1 loại tài liệu mình hay phải làm đi làm lại (báo cáo tháng, đề xuất, biên bản, hồ sơ năng lực...).

**Mục tiêu buổi học:**
- Anh chị nói được Skill là gì, khác gì với việc gõ lại chỉ dẫn mỗi lần, và Skill KHÔNG phải là gì.
- Anh chị tự tay đi hết 3 bước: nhờ nghiên cứu -> ra file Word đẹp đúng logo, đúng màu -> đóng gói cách làm đó thành 1 Skill và lưu lại.
- Anh chị gọi lại được Skill vừa tạo ở một cuộc trò chuyện mới và ra đúng kết quả cũ.

---

## B. Kịch bản hands-on (45 phút)

### Phần 1 [00:00 - 07:00] - Giới thiệu và điểm đau

[Chào lớp, nối buổi 6.]

> "Em chào anh chị. Hôm qua anh chị đã tự dựng được ứng dụng bằng tiếng Việt. Hôm nay mình giải một nỗi khổ khác, mà em đoán nhiều anh chị đang gặp hằng tuần."

[Slide "mỗi lần nhờ lại phải dặn lại từ đầu".]

> "Anh chị thử nhớ lại. Mỗi lần nhờ Claude làm giúp một tài liệu, anh chị phải dặn những gì? [Chờ vài phản hồi.] Dùng màu này của công ty, chèn logo ở góc trên, tiêu đề in đậm, cỡ chữ bao nhiêu, nhớ kiểm tra lỗi dấu tiếng Việt... Đúng không ạ. Lần sau làm tài liệu khác, anh chị lại phải dặn y hệt như vậy. Lần sau nữa cũng thế."

> "Và đây mới là chỗ đau nhất: cả phòng anh chị năm người, mỗi người dặn một kiểu. Ra năm bản tài liệu năm phong cách khác nhau, không ai giống ai. Sếp nhìn vào là biết ngay không có chuẩn."

> "Hôm nay mình xử lý đúng chỗ đó bằng một thứ tên là **Skill**."

**Skill là gì (nói chậm, đây là khái niệm mới):**

> "Skill là cách để **lưu lại cách làm một công việc** cho Claude. Anh chị dặn kỹ MỘT LẦN. Claude ghi nhớ lại. Từ đó về sau, anh chị chỉ nói một câu ngắn là nó tự làm đúng như vậy, không cần giải thích lại từ đầu."

> "Em hay ví thế này: Skill giống một **tờ quy trình dán trên tường**. Ai vào làm việc đó cũng theo đúng tờ quy trình, ra kết quả giống nhau. Skill chính là tờ quy trình đó, nhưng viết cho AI."

> "Và điều quan trọng nhất, em nhấn mạnh vì nhiều anh chị hay lo: **anh chị KHÔNG cần biết lập trình** để dùng hoặc tạo Skill. Chỉ cần làm một việc cho ưng ý một lần, rồi nhờ Claude ghi nhớ lại. Có vậy thôi."

**Skill làm được gì:**

- Tạo tài liệu **đúng chuẩn công ty** (Word, Excel, PowerPoint, PDF): đúng màu, đúng logo, đúng mẫu.
- Làm đúng **một quy trình nhiều bước** theo thứ tự cố định, không bỏ sót bước nào.
- Ghi nhớ **quy định, văn phong, cách trình bày riêng** của công ty.
- **Lặp lại chính xác** một công việc mà không cần anh chị dặn lại từ đầu.

**Skill KHÔNG phải là gì (nói rõ để lớp khỏi hiểu lầm):**

> "Em nói luôn ba điều Skill KHÔNG phải, kẻo anh chị kỳ vọng sai. Skill **không phải một phần mềm riêng** phải đi cài. Nó **không tự chạy** khi anh chị chưa nhờ tới. Và nó **không thay anh chị hiểu công việc** - nó chỉ giúp Claude làm lại đúng cách đã thống nhất từ trước, nhanh hơn và đều tay hơn. Trách nhiệm cuối vẫn là của mình."

> "Nói lý thuyết vậy đủ rồi. Mình làm luôn cho dễ hiểu. Anh chị mở máy nhé - mình sẽ đi ba bước, và cái Skill sẽ tự sinh ra ở bước thứ ba."

### Phần 2 [07:00 - 14:00] - Bước 1: nhờ Claude nghiên cứu một chủ đề

> "Bước một, mình cần có nội dung đã. Anh chị mở một cuộc trò chuyện mới trong Claude và gõ câu này:"

```
Research và cho tôi báo cáo về xu hướng phát triển AI trong năm 2026
```

[Chờ Claude tìm kiếm và trả lời. Mất một lúc - nói tiếp trong lúc chờ.]

> "Anh chị để ý: Claude đang tự đi tìm thông tin từ nhiều nguồn trên internet, rồi tổng hợp lại. Mình không phải mở Google, không phải copy từng bài."

> "Xong rồi. Anh chị đọc lướt kết quả. Ở bước này em muốn anh chị **chỉ quan tâm nội dung thôi, chưa cần quan tâm hình thức đẹp hay xấu**. Nó đang nằm trong khung chat, chữ đen trên nền trắng, chưa có logo, chưa có màu gì cả. Đó là chuyện của bước hai."

> "Ai đã có kết quả nghiên cứu thì gõ '1' vào chat lớp."

### Phần 3 [14:00 - 25:00] - Bước 2: nhờ tạo file Word đẹp, đúng thương hiệu

> "Bước hai. Giờ mình biến nội dung đó thành một file Word tử tế, đúng màu công ty, có logo."

> "Trước khi gõ lệnh, anh chị làm một việc quan trọng: **kéo file logo công ty mình thả vào khung chat**. Gửi logo cho nó trước đã. Nếu không đưa logo, Claude phải tự đoán màu và không có hình để chèn - kết quả sẽ không đúng thương hiệu của mình."

[Chờ cả lớp gửi logo xong. Giảng viên gửi logo CES Global khi demo.]

> "Có logo rồi thì gõ tiếp câu này:"

```
Tôi thấy nội dung khá chi tiết rồi, bây giờ hãy tổng hợp và tạo cho tôi 1 file docx cho nội dung trên. Sử dụng tone màu của logo công ty của tôi, trong file docx phải có logo kèm theo luôn. Lưu ý file docx phải chuẩn tiếng Việt và không bị lỗi dấu.
```

[Chờ Claude dựng file. Đây là bước lâu nhất của buổi - canh giờ.]

> "Claude đang lấy nội dung vừa nghiên cứu, sắp xếp lại gọn gàng, tạo ra file Word có logo, đúng màu thương hiệu, và tự kiểm tra để không bị lỗi dấu tiếng Việt. Lát nữa file sẽ hiện ra trong khung chat, anh chị bấm tải về."

> "Anh chị **tải file về và mở ra xem thật** nhé. Đây là bước phải kiểm bằng mắt: logo có đúng chỗ không, màu có đúng của công ty mình không, tiếng Việt có bị lỗi dấu không. Chỗ nào chưa ưng thì nói tiếp để nó sửa - ví dụ 'logo nhỏ lại và đưa lên góc phải', 'tiêu đề đổi sang màu đậm hơn'."

> "Cứ chỉnh tới khi anh chị thấy **ưng ý thật sự**. Điểm này quan trọng, em sẽ giải thích ngay ở bước sau: mình chỉ đóng gói cái đã ưng, chứ không đóng gói cái tàm tạm."

### Phần 4 [25:00 - 35:00] - Bước 3: đóng gói cách làm này thành một Skill

> "Bước ba - bước đáng tiền nhất buổi hôm nay."

> "Anh chị nhìn lại xem mình vừa mất bao nhiêu công: gửi logo, dặn màu, dặn chèn logo, dặn kiểm tra lỗi dấu, rồi chỉnh tới chỉnh lui mấy lượt. Tuần sau làm tài liệu khác, anh chị lại mất đúng chừng đó công. Vô lý đúng không ạ."

> "Nên mình bảo Claude gói toàn bộ cách làm vừa rồi lại. Anh chị gõ câu này - nhớ thay tên công ty của mình vào chỗ trong ngoặc:"

```
Tôi thấy file này đẹp rồi, bây giờ hãy tạo cho tôi skill đóng gói tài liệu đẹp và đúng tone màu như vậy, sau này khi tôi nói tạo tài liệu theo chuẩn <tên công ty của tôi> thì hãy áp dụng skill này cho tôi (logo tôi sẽ cung cấp).
```

> "[Giảng viên demo thì điền 'CES Global'.] Anh chị điền tên công ty mình vào nhé."

[Claude thường hỏi lại vài câu trước khi tạo.]

> "Anh chị để ý: Claude sẽ **hỏi lại vài câu cho rõ** - kiểu như khi nào thì dùng skill này, có cần thêm gì không. Anh chị cứ trả lời bình thường bằng tiếng Việt. Đây là chuyện tốt: nó đang làm rõ tờ quy trình trước khi dán lên tường."

> "Sau đó Claude tự ghi nhớ toàn bộ cách trình bày mình vừa dùng ở bước 2 - màu sắc, bố cục, cách chèn logo - và đóng gói lại thành một Skill, kèm một nút bấm để lưu."

**Lưu Skill lại (quan trọng - không lưu là mất):**

> "Anh chị nhìn trong khung chat: có một file skill hiện ra kèm nút **Save skill**. **Bấm nút đó**. Bấm rồi thì Skill được lưu vào tài khoản của anh chị, dùng lại được ở mọi cuộc trò chuyện sau. Không bấm thì lát nữa đóng chat là công cốc."

> "Ai bấm Save xong gõ '2' vào chat lớp cho em."

[Đi một vòng, kiểm tra từng máy đã lưu skill chưa. Đây là chỗ hay sót nhất.]

### Phần 5 [35:00 - 41:00] - Dùng lại Skill và cách mang Skill đi

**Thử lại ngay để tin:**

> "Giờ thử xem nó có thật sự dùng lại được không. Anh chị **mở một cuộc trò chuyện MỚI** - mới hoàn toàn, không phải chat cũ. Gõ dấu **/** để hiện danh sách skill, chọn skill anh chị vừa tạo. Rồi nhờ nó làm một tài liệu khác, ví dụ:"

```
Tạo cho tôi tài liệu giới thiệu dịch vụ theo chuẩn <tên công ty của tôi>.
```

> "Để ý: lần này anh chị **không dặn lại màu, không dặn chèn logo, không dặn kiểm tra lỗi dấu**. Chỉ một câu ngắn. Mà nó vẫn ra đúng kiểu tài liệu đẹp như lúc nãy. Đó là toàn bộ giá trị của Skill: dặn một lần, dùng mãi."

**Hai cách tạo Skill (chốt lại cho lớp hiểu bức tranh):**

> "Em chốt lại: có hai cách tạo Skill."

- **Cách 1 - nhờ Claude đóng gói giúp (khuyến nghị, không cần biết code).** Chính là cái anh chị vừa làm: làm một việc cho tới khi ưng ý -> nói "hãy đóng gói cách làm này thành một skill để lần sau dùng lại" -> trả lời vài câu Claude hỏi -> xong.
- **Cách 2 - tự soạn thủ công (dành cho ai rành kỹ thuật hơn).** Skill về bản chất là một **thư mục** gồm một file hướng dẫn tên **SKILL.md** - ghi rõ hai điều: *skill này làm gì* và *khi nào nên dùng nó*. Kèm theo có thể có file phụ trợ: mẫu tài liệu, logo, hình ảnh.

> "Anh chị nhớ giúp em cái tên **SKILL.md** này. Ngày mai mình sẽ mở nắp ra xem bên trong nó có gì, và tự tay viết một cái."

**Cách lưu và mang Skill đi dùng:**

- **Trong ứng dụng Claude:** khi Claude tạo xong Skill, bấm nút **Save skill** hiện trong khung chat - đúng cái anh chị vừa bấm.
- **Trên claude.ai (bản web):** vào **Settings -> Skills**, chọn tải lên (upload) file Skill dạng **.zip**. Skill áp dụng riêng cho tài khoản của anh chị.
- **Dùng chung cho cả công ty (gói Team/Enterprise):** quản trị viên cấp phát Skill cho toàn bộ nhân viên, không cần từng người tự tải. Đây là cách các công ty chuẩn hóa tài liệu cho cả phòng.

**Lưu ý an toàn:**

> "Hai điều em phải nhắc. Một: **chỉ dùng Skill từ nguồn tin cậy** - skill là chỉ dẫn cho AI làm việc thay mình, nhận skill lạ về dùng thì rủi ro. Hai: **không đưa thông tin nhạy cảm vào bên trong Skill** - mật khẩu, dữ liệu khách hàng, số tài khoản. Skill là thứ để chia sẻ cho đồng nghiệp, mà thứ gì chia sẻ được thì đừng cất bí mật trong đó."

### Phần 6 [41:00 - 45:00] - Tổng kết và giao bài

> "Chốt lại buổi hôm nay bằng một câu: hôm nay anh chị chuyển từ *dặn mỗi lần* sang *dặn một lần*."

- **Skill** = lưu lại cách làm một việc, để lần sau nói một câu ngắn là ra đúng kết quả cũ.
- Cách dễ nhất để tạo: **làm cho ưng ý một lần, rồi nhờ Claude đóng gói lại**. Không cần biết code.
- Nhớ **bấm Save skill**, và nhớ cái tên **SKILL.md** cho buổi sau.

**Bài tập về nhà buổi 7:**
1. Tạo 1 Skill cho **loại tài liệu anh chị hay phải làm đi làm lại** (đã nghĩ trước khi vào lớp): làm cho ưng ý một lần rồi nhờ đóng gói. Nhớ bấm Save.
2. Mở cuộc trò chuyện mới, gõ `/` gọi Skill đó ra dùng lại. Chụp màn hình kết quả đăng nhóm lớp.
3. Viết 1 dòng: skill này giúp mình khỏi phải dặn lại những gì.
4. **[Bắt buộc - chuẩn bị cho buổi 8]** Cài **Claude Code** theo hướng dẫn em gửi trong nhóm. Ai vướng thì nhắn trợ giảng **trước buổi 8**, đừng để tới giờ học mới báo.

> "Buổi sau mình sang một mức mới. Hôm nay Claude tự gói skill cho anh chị, mình không nhìn thấy bên trong nó có gì. Buổi 8 mình sẽ **mở nắp ra**: skill thật sự chỉ là một file văn bản tên SKILL.md nằm trong thư mục dự án của mình. Anh chị sẽ tự tay tạo một cái, và quan trọng hơn - anh chị sẽ thấy **skill sinh ra từ đâu**, chứ không phải chép một file mẫu ở đâu về."

> "Buổi 8 dùng công cụ tên là **Claude Code**, nên tối nay anh chị chịu khó cài trước giúp em. Hướng dẫn em gửi trong nhóm ngay bây giờ, làm theo từng bước là được, có gì vướng nhắn trợ giảng. Cảm ơn anh chị, hẹn gặp lại."

[Kết thúc buổi. Trợ giảng gửi ngay hướng dẫn cài Claude Code vào nhóm + mở luồng hỗ trợ cài đặt; điểm danh ai đã cài xong trước buổi 8.]

---

## C. Checklist chuẩn bị của giảng viên

- [ ] Slide tiêu đề + slide "mỗi lần nhờ lại phải dặn lại từ đầu".
- [ ] **Đã chạy trước trọn 3 bước ở nhà** (research -> file .docx -> đóng gói skill); biết chỗ Claude hay hỏi lại.
- [ ] File logo CES Global (PNG/SVG nền trắng) sẵn trên máy để demo.
- [ ] Gửi vào nhóm TRƯỚC giờ học: `buoi-07-skill-dong-goi-tai-lieu.md` + nhắc anh chị chuẩn bị logo công ty.
- [ ] Canh giờ: bước tạo file .docx là bước lâu nhất. Nếu lớp chậm, cắt bớt vòng chỉnh sửa ở Phần 3, tuyệt đối không cắt Phần 4 (đóng gói skill).
- [ ] Đi một vòng kiểm **từng máy đã bấm Save skill** - đây là chỗ học viên hay sót nhất.
- [ ] **Gửi hướng dẫn cài Claude Code ngay cuối buổi** + mở luồng hỗ trợ; điểm danh ai đã cài xong trước buổi 8.
- [ ] Link ghi hình buổi học.

## D. Tiêu chí hoàn thành buổi 7

- Anh chị nói được Skill là gì và nêu được ít nhất 1 điều Skill KHÔNG phải.
- Anh chị đi hết 3 bước và **có file .docx đúng logo, đúng màu, tiếng Việt không lỗi dấu**.
- Anh chị đóng gói được cách làm đó thành Skill và **đã bấm Save skill**.
- Anh chị gọi lại được Skill ở một cuộc trò chuyện mới bằng `/` và ra đúng kiểu tài liệu cũ.
- Anh chị biết Skill về bản chất là thư mục có file **SKILL.md** (bắc cầu sang buổi 8).
- **Đã nhận hướng dẫn cài Claude Code** và biết hạn phải cài xong là trước buổi 8.
