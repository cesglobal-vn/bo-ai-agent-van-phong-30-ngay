# Buổi 08 - Skill tóm tắt tài liệu (1): skill sinh ra từ đâu (kịch bản hands-on)

> **Tuần 2 - Thứ 4** | Thời lượng: 45 phút | Công cụ: **Claude Code** (buổi đầu tiên dùng)
> **Mô hình buổi học:** HANDS-ON. Giảng viên và học viên làm SONG SONG từng lượt.
> **Ý ĐỒ CỐT LÕI CỦA BUỔI NÀY - GIẢNG VIÊN ĐỌC KỸ TRƯỚC KHI LÊN LỚP:**
> **TUYỆT ĐỐI KHÔNG phát sẵn nội dung SKILL.md cho lớp chép.** Cả lớp phải tự mình hỏi đi hỏi lại **5 lượt** mới ra bản tóm tắt dùng được, rồi mới đóng gói chỗ đó lại thành skill. Mỗi lượt chat biến thành đúng **một mục** trong SKILL.md. Học viên hiểu **vì sao có từng mục**, thay vì chép một file mẫu rơi từ trên trời xuống. Đây là điểm khác biệt lớn nhất của buổi này - đừng rút gọn, đừng phát file trước.
> **Xưng hô:** giảng viên xưng **"em"**, gọi học viên là **"anh chị"**.
> **Định dạng script:** ngoặc vuông `[ ]` là chỉ dẫn thao tác (không đọc to); ngoặc kép `"..."` là lời giảng viên nói gần như nguyên văn; mỗi khối ``` là nội dung copy-dán được.

---

## A. Chuẩn bị trước buổi học

**Giảng viên chuẩn bị:**
- **Claude Code đã cài và chạy được**; đã tự đi hết 5 lượt + bước đóng gói ít nhất 1 lần ở nhà.
- **Bảng/flipchart hoặc slide trống để ghi 5 dòng trong buổi** - buổi này bắt buộc phải ghi lại từng lượt, vì cuối buổi sẽ đối chiếu với 5 mục trong SKILL.md.
- Gửi TRƯỚC vào nhóm lớp: file thực hành `tai-lieu-mau-bao-cao-tong-ket-2026.pdf` (14 trang) + hướng dẫn tạo thư mục dự án. **KHÔNG gửi file SKILL.md mẫu.**
- **Điểm danh trước buổi:** ai chưa cài được Claude Code phải được trợ giảng hỗ trợ xong trước giờ học. Lớp có người chưa cài là buổi này vỡ.
- Xem trước bảng "tình huống hay gặp" ở mục C.

**Học viên cần có sẵn:**
- **Claude Code đã cài xong** (bài tập buổi 7).
- Một thư mục dự án trên máy, ví dụ `hoc-ai-agent`, bên trong có thư mục `tai-lieu` chứa file `tai-lieu-mau-bao-cao-tong-ket-2026.pdf` tải từ nhóm lớp (**giữ nguyên tên file**, đừng đổi tên).

**Mục tiêu buổi học:**
- Anh chị nói được skill là gì và khác gì với việc gõ lại chỉ dẫn mỗi lần.
- Anh chị **hiểu skill sinh ra từ đâu**: làm tay vài lượt, thấy mình lặp lại chỉ dẫn nào thì gói chỉ dẫn đó lại.
- Anh chị biết skill là 1 thư mục chứa file `SKILL.md`, đặt đúng chỗ trong dự án.
- Anh chị tự tay tạo được skill `tom-tat-tai-lieu` trong dự án của mình.

---

## B. Kịch bản hands-on (45 phút)

### Phần 1 [00:00 - 05:00] - Giới thiệu và điểm đau

> "Em chào anh chị. Hôm qua anh chị đã tạo được Skill đầu tiên - nhưng để ý nhé: Claude tự gói, mình không nhìn thấy bên trong nó có gì. Nó là một cái hộp đen. Hôm nay mình **mở nắp hộp ra**."

> "Và em nói trước điều quan trọng nhất của buổi hôm nay. Em sẽ **không** đưa sẵn một file skill mẫu cho anh chị chép. Em sẽ để anh chị tự vật lộn với một tài liệu khó, hỏi đi hỏi lại mấy lượt cho tới khi ra kết quả dùng được. Rồi lúc đó mình mới gói lại. Vì em muốn anh chị thấy: **skill không phải thứ tải ở đâu về, skill là biên bản của những lần mình đã phải hỏi**."

[Giơ file báo cáo lên màn hình, kéo nhanh cho thấy độ dài.]

> "Đây là tài liệu hôm nay: một báo cáo tổng kết năm, **14 trang**, 9 phần, 3 phụ lục. Anh chị có 10 phút trước giờ họp. Đọc hết được không? Không ai đọc hết được. Đây đúng là loại tài liệu làm mình khổ nhất."

### Phần 2 [05:00 - 09:00] - Mở Claude Code tại thư mục dự án

> "Anh chị mở **Claude Code** tại thư mục `hoc-ai-agent` của mình - thư mục có chứa file báo cáo trong `tai-lieu`. Ai chưa mở được thì giơ tay, trợ giảng qua ngay."

[Trợ giảng đi hỗ trợ. Không bắt đầu khi còn người chưa mở được.]

> "Anh chị gõ thử `ls` rồi Enter để xem Claude Code có đang đứng đúng thư mục không - phải thấy thư mục `tai-lieu`. Thấy rồi thì gõ '1' vào chat lớp."

> "Khác biệt so với claude.ai anh chị dùng suốt hai tuần: ở đây Claude **đọc thẳng file trên máy anh chị**, không phải tải lên. Nó cũng **tạo được file mới** trên máy - lát nữa nó sẽ tự tạo file skill cho mình."

### Phần 3 [09:00 - 14:00] - Skill trong Claude Code là gì

> "Trước khi làm, em cho anh chị cái khung ngắn thôi. Phần 'vì sao cần skill' lát nữa tự sáng ra khi mình làm, em không giảng dài ở đây."

**1. Skill nằm ở đâu.** Là một **thư mục** trong dự án: `.claude/skills/<tên-skill>/`. Trong đó có một file tên `SKILL.md`. **Tên thư mục chính là tên skill.**

Ví dụ skill hôm nay sẽ nằm ở: `.claude/skills/tom-tat-tai-lieu/SKILL.md`

**2. Bên trong SKILL.md có gì.** Phần đầu ghi `name` (tên) và `description` (mô tả *dùng khi nào*). Phần thân là các bước chỉ dẫn cho AI làm.

**3. Claude tự nạp nhờ dòng description.**

> "Đây là điểm mấu chốt, anh chị nhớ giúp em. Dòng mô tả viết càng rõ **'dùng khi nào'** thì Claude càng biết lúc nào lôi skill ra dùng. Mô tả mà mờ thì Claude không tự nạp, khi đó mình phải gọi thẳng tên skill. Ngày mai mình sẽ thử cả hai kiểu."

**Câu hỏi tương tác (bắt buộc làm, dùng lại ở cuối):**

> "Em hỏi cả lớp một câu, ai trả lời em ghi lên bảng: **trong công việc của anh chị, có việc nào tuần nào cũng làm, bước nào cũng giống nhau không?** Kể em nghe một cái."

[Gọi 2-3 anh chị. **Ghi lên bảng** - cuối buổi 9 sẽ quay lại để họ tự làm skill cho đúng việc đó.]

### Phần 4 [14:00 - 33:00] - Năm lượt hỏi: cùng vật lộn với báo cáo 14 trang

> "Giờ mình làm thật. Anh chị làm song song với em, từng lượt một. Em nhắc trước: **mình sẽ phải hỏi 5 lượt**. Anh chị đếm giúp em, vì con số 5 đó chính là bài học hôm nay."

**Lượt 1 - Tóm tắt kiểu thông thường (để thấy nó chưa đủ):**

> "Đầu tiên mình nhờ tóm tắt theo cách bình thường nhất, tức là nghĩ gì gõ nấy. Anh chị gõ:"

```
Tóm tắt giúp tôi báo cáo trong tai-lieu/tai-lieu-mau-bao-cao-tong-ket-2026.pdf
```

[Chờ kết quả. Đọc chung 1 bản.]

*Kết quả mong đợi:* một bản tóm tắt chung chung, vài đoạn hoặc dăm gạch đầu dòng - doanh thu tăng, có khó khăn về nhân sự và công nợ. Đọc thì xuôi tai. Nhưng **không bóc đủ số liệu, không gom hạn chót, và gần như chắc chắn không phát hiện con số bị lệch** trong báo cáo.

> "Nghe thì ổn đúng không ạ? Nhưng nếu em mang đúng bản này đi họp, sếp hỏi 'tổng doanh thu bao nhiêu', 'hạn nào sắp tới' - em vẫn phải mở lại 14 trang. Nó **chưa dùng được**. Nên em hỏi tiếp."

**Lượt 2 - Ép liệt kê theo từng phần:**

> "Vấn đề thứ nhất: nó gộp hết vào một cục. Em muốn theo đúng bố cục báo cáo. Anh chị gõ:"

```
Chưa đủ. Liệt kê lại theo từng phần của báo cáo, mỗi phần vài ý chính.
```

*Kết quả mong đợi:* liệt kê theo **9 phần La Mã** của báo cáo (từ I. Đặc điểm tình hình tới IX. Kiến nghị, đề xuất), mỗi phần vài gạch đầu dòng. Giờ đã đầy đủ nhưng còn dài và chưa nổi số.

> [**Ghi lên bảng:** "Lượt 2 -> sau này thành mục **Ý CHÍNH CHI TIẾT**"]

**Lượt 3 - Bóc số liệu và hạn chót:**

> "Thứ hai: cái sếp hỏi luôn là **con số và deadline**. Em bắt nó bóc riêng ra. Anh chị gõ:"

```
Bóc ra mọi con số, mốc thời gian, cam kết quan trọng trong tài liệu.
```

*Kết quả mong đợi:* liệt kê được các con số chính - doanh thu năm **12.450 triệu** (ghi ở mục II.1), lợi nhuận trước thuế **1.885 triệu**, lợi nhuận sau thuế **1.508 triệu**, công nợ phải thu **1.240 triệu** trong đó quá hạn **275 triệu** (22,2%), chi phí marketing **485 triệu** (3,9% doanh thu), nhân sự tăng từ **34 lên 41 người** - và các mốc thời gian rải trong bài: **15/02/2027** (bổ sung nhân sự giao hàng Hà Nội), **31/3/2027**, **30/6/2027**, **31/12/2027**.

> **[ĐIỂM CẦN SOI - giảng viên chú ý]** Kiểm xem Claude có nhặt được mốc **28/02/2027** hay không. Mốc này nằm sâu ở **Phụ lục 2, trang 13**, thân báo cáo không hề nhắc.
> - Nếu **bỏ sót**: "Ngay cả AI cũng phải được dặn kỹ mới moi ra chỗ chôn sâu. Lát nữa mình sẽ dặn nó một lần rồi thôi."
> - Nếu **nhặt được**: "Cả lớp đọc 14 trang trong 10 phút, có ai thấy dòng này không ạ?"

> [**Ghi lên bảng:** "Lượt 3 -> mục **SỐ LIỆU, NGÀY THÁNG, HẠN CHÓT**"]

**Lượt 4 - Hỏi chỗ bất lợi, mâu thuẫn, mập mờ (lượt quan trọng nhất buổi):**

> "Thứ ba, và đây là thứ **đáng tiền nhất**. Em không chỉ muốn biết báo cáo nói gì. Em muốn biết **chỗ nào có vấn đề**. Anh chị gõ:"

```
Trong báo cáo này có điều khoản nào bất lợi, chỗ nào mâu thuẫn, hoặc chỗ nào mập mờ không?
```

[**Dừng lại đủ lâu ở lượt này.** Đây là khoảnh khắc của cả buổi.]

*Kết quả mong đợi - Claude phải bắt được:*
- **Mâu thuẫn số liệu:** mục II.1 ghi tổng doanh thu **12.450 triệu**, nhưng bảng theo quý, bảng theo sản phẩm, bảng theo khu vực và Phụ lục 1 đều cộng ra **12.545 triệu**. **Lệch 95 triệu.** Thêm một dấu hiệu nữa: tỷ lệ "tăng 14,2%" ghi trong bài lại đúng với 12.545 chứ không đúng với 12.450.
- **Điều khoản bất lợi:** hợp đồng Đại Tín (**1.845 triệu**, Phụ lục 2) **tự động gia hạn thêm 12 tháng** nếu Công ty không gửi văn bản từ chối trước **28/02/2027**.
- **Rủi ro:** ba khách hàng lớn nhất chiếm **42,3%** doanh thu; nợ quá hạn **275 triệu** (22,2% công nợ phải thu); tăng trưởng chậm dần từ **9,8% quý II xuống 1,1% quý IV**.
- **Chỗ mập mờ:** ngân sách marketing 2027 được nhắc tới nhưng **không nêu con số**; mức thưởng vượt chỉ tiêu chỉ ghi "theo Quy chế thưởng hiện hành".

> "Cả lớp để ý con số này giúp em. **Báo cáo tự nói vênh nhau 95 triệu.** Em đọc tay 14 trang, thú thật là em không bắt được. Đây mới là chỗ AI đỡ việc thật sự - chứ không phải chỗ nó viết văn hay."

> **[Nếu Claude của một số anh chị chưa nêu chỗ lệch]** cho gõ thêm: `Kiểm tra lại xem các bảng số liệu trong báo cáo có cộng khớp với con số tổng nêu ở phần đầu không.` Rồi nhấn: "Phải hỏi tới nơi nó mới soi. Chính vì vậy mình cần gói câu hỏi này lại thành skill."

> [**Ghi lên bảng:** "Lượt 4 -> mục **ĐIỂM CẦN LƯU Ý / RỦI RO**"]

**Lượt 5 - Chặn suy đoán và rút gọn:**

> "Còn một chuyện phải xử lý. **AI hay có tật thấy thiếu thì tự điền vào cho trơn.** Với báo cáo và hợp đồng thì đó là tai họa. Em hỏi thẳng nó. Anh chị gõ:"

```
Trong những gì bạn vừa trả lời, có chỗ nào bạn tự suy đoán mà tài liệu không nói không? Từ giờ chỉ dùng thông tin có trong tài liệu, chỗ nào tài liệu không nói thì ghi "Tài liệu không đề cập", không được đoán. Rút lại giúp tôi 3 tới 5 gạch đầu dòng quan trọng nhất để tôi gửi sếp.
```

*Kết quả mong đợi:* Claude tự rà lại, **chỉ ra chỗ nào là suy luận của nó** chứ không phải tài liệu nói (ví dụ nhận định về nguyên nhân tăng trưởng chậm), rồi trả về 3 tới 5 gạch đầu dòng cô đọng.

> "Thử một câu nữa cho chắc, anh chị gõ: `ngân sách marketing năm 2027 là bao nhiêu?` - nó phải trả lời **tài liệu không đề cập**, không được bịa ra con số."

> [**Ghi lên bảng:** "Lượt 5 -> mục **QUY TẮC** + mục **TÓM TẮT NHANH**"]

### Phần 5 [33:00 - 41:00] - Đóng gói 5 lượt vừa rồi thành một skill

> "Xong. Giờ em có bản tóm tắt dùng được. **Nhưng nhìn lại xem em vừa mất mấy lượt: năm lượt.**"

[Đọc chậm đoạn này.]

> "Tuần sau có báo cáo khác, em lại mất năm lượt nữa - và chắc gì đã hỏi đúng thứ tự như hôm nay. Cả phòng em năm người, mỗi người hỏi một kiểu, ra năm bản khác nhau. **Đó chính là lý do phải đóng gói.**"

[**Chỉ lên bảng trước khi gõ.**]

> "Anh chị nhìn 5 dòng em vừa ghi trên bảng. Đó chính là 5 mục sắp xuất hiện trong file skill. **Em không bịa ra cấu trúc này - nó là đúng những gì em vừa phải hỏi.** Giờ mình bảo Claude gói lại. Anh chị copy khối này:"

```
Tôi thấy kết quả ổn rồi, giờ hãy đóng gói lại thành skill tóm tắt tài liệu cho tôi, để sau này tôi không phải chat nhiều nữa mà bạn vẫn đưa ra kết quả tốt. Sau này tôi muốn khi bảo bạn "Tóm tắt tài liệu abc" thì bạn sẽ tự động kích hoạt skill này cho tôi.

Khi tôi đưa vào một tài liệu nào đó, làm theo các bước:

1. Đọc toàn bộ tài liệu.
2. Xuất ra đúng cấu trúc sau:
- TÓM TẮT NHANH
+ 3 tới 5 gạch đầu dòng ý chính nhất.

- Ý CHÍNH CHI TIẾT
+ Liệt kê theo từng mục/phần của tài liệu.

- SỐ LIỆU, NGÀY THÁNG, HẠN CHÓT
+ Bóc ra mọi con số, mốc thời gian, cam kết quan trọng.

- ĐIỂM CẦN LƯU Ý / RỦI RO
+ Nếu có điều khoản bất lợi, mâu thuẫn, hoặc chỗ mập mờ.

- QUY TẮC
+ Chỉ dùng thông tin có trong tài liệu. Không có thì ghi "Tài liệu không đề cập", KHÔNG suy đoán.
+ Trích nguyên văn khi cần bằng chứng, đặt trong ngoặc kép.
+ Trả lời bằng tiếng Việt, rõ ràng.
```

*Kết quả mong đợi:* Claude báo đã tạo file `.claude/skills/tom-tat-tai-lieu/SKILL.md`.

**Mở file ra xem - bước không được bỏ:**

> "Anh chị mở file đó ra xem. Gõ: `Mở file .claude/skills/tom-tat-tai-lieu/SKILL.md cho tôi xem` - hoặc mở bằng Notepad cũng được."

[**Chỉ từng mục trong file, đối chiếu với 5 dòng trên bảng:**]

| Trong SKILL.md | Sinh ra từ |
|---|---|
| TÓM TẮT NHANH | Lượt 5 |
| Ý CHÍNH CHI TIẾT | Lượt 2 |
| SỐ LIỆU, NGÀY THÁNG, HẠN CHÓT | Lượt 3 |
| ĐIỂM CẦN LƯU Ý / RỦI RO | Lượt 4 |
| QUY TẮC | Lượt 5 |

> "Nhìn kỹ file này giúp em. **Nó không phải mẫu em tải ở đâu về. Nó là biên bản của 5 lượt em vừa phải hỏi, được ghi lại một lần để khỏi phải hỏi nữa.**"

> "Và đây là câu em muốn anh chị mang về: **skill của anh chị sau này cũng sinh ra đúng kiểu đó - cứ làm tay vài lần, thấy mình lặp lại chỉ dẫn nào thì gói chỉ dẫn đó lại.**"

### Phần 6 [41:00 - 45:00] - Tổng kết và giao bài

> "Chốt lại. Hôm nay anh chị có ba thứ."

- Một **skill thật** nằm trong dự án của mình: `.claude/skills/tom-tat-tai-lieu/SKILL.md`.
- Biết **skill là gì về mặt vật lý**: một thư mục, một file văn bản. Không có gì bí ẩn.
- Quan trọng nhất: biết **skill sinh ra từ đâu** - từ những lượt mình đã phải hỏi đi hỏi lại.

**Bài tập về nhà buổi 8:**
1. Mở lại file `SKILL.md` của mình, đọc hết một lượt. Đối chiếu từng mục với 5 lượt hôm nay xem có khớp không.
2. Lấy **một tài liệu dài trong công việc thật** của mình (hợp đồng, biên bản họp, báo cáo, đề xuất) - **chuẩn bị sẵn để mai dùng ở buổi 9**. Nhớ che thông tin nhạy cảm.
3. Ghi ra 1 dòng: việc lặp lại nào của anh chị đáng được đóng gói thành skill tiếp theo (dựa vào câu trả lời đã ghi trên bảng hôm nay).

> "Ngày mai mình trả lời câu hỏi quan trọng nhất: **skill này có thật sự dùng lại được không, hay chỉ đúng với đúng cái báo cáo hôm nay?** Em sẽ đưa vào một loại tài liệu khác hẳn - hợp đồng mà anh chị đã tóm tắt từ buổi 2 ấy - và chỉ gõ **một câu**, không nhắc gì tới skill. Mình xem nó có tự nhận ra không. Rồi mình sẽ thử **bẫy nó bịa** xem nó có bịa không. Cảm ơn anh chị, hẹn gặp lại ngày mai."

[Kết thúc buổi. Trợ giảng rà lại: mọi máy đều có thư mục `.claude/skills/tom-tat-tai-lieu/`. Nhắc anh chị chuẩn bị 1 tài liệu công việc thật cho buổi 9.]

---

## C. Checklist chuẩn bị của giảng viên

- [ ] **Điểm danh Claude Code trước buổi** - ai chưa cài phải xong trước giờ học.
- [ ] Đã tự đi hết 5 lượt + bước đóng gói ở nhà ít nhất 1 lần.
- [ ] **Bảng/flipchart trống** để ghi 5 dòng trong buổi (bắt buộc - cuối buổi phải đối chiếu).
- [ ] Gửi vào nhóm TRƯỚC giờ học: `tai-lieu-mau-bao-cao-tong-ket-2026.pdf` + hướng dẫn tạo thư mục dự án. **KHÔNG gửi SKILL.md mẫu.**
- [ ] Canh giờ: Phần 4 (5 lượt) là phần dài nhất, 19 phút. Nếu trễ, rút ngắn phần đọc kết quả Lượt 1 và 2, **giữ nguyên Lượt 4** (khoảnh khắc 95 triệu) và Phần 5 (đóng gói).
- [ ] Chuẩn bị sẵn câu chữa cháy khi Claude không nêu chỗ lệch 95 triệu (đã có trong Phần 4).
- [ ] Link ghi hình buổi học.

**Tình huống hay gặp:**

| Tình huống | Cách xử lý |
|---|---|
| Claude Code đứng sai thư mục, không thấy file | Cho gõ `ls` kiểm tra; hướng dẫn mở lại Claude Code đúng trong thư mục `hoc-ai-agent` |
| Claude không đọc được PDF | Kiểm tra đường dẫn có đúng `tai-lieu/tai-lieu-mau-bao-cao-tong-ket-2026.pdf` không; tên file có dấu cách thì cho đổi tên |
| Kết quả mỗi máy một khác | Bình thường - nhấn mạnh ý chính chứ không so từng chữ; đọc chung 1-2 bản làm chuẩn |
| Claude không bắt được chỗ lệch 95 triệu | Cho gõ câu kiểm tra bảng cộng (Phần 4); dùng luôn làm bài học "phải hỏi tới nơi" |
| Học viên đòi file SKILL.md mẫu để chép | Từ chối, giải thích ý đồ buổi học - phải tự sinh ra mới hiểu |

## D. Tiêu chí hoàn thành buổi 8

- Anh chị mở được Claude Code đúng tại thư mục dự án và cho nó đọc được file báo cáo.
- Anh chị đi hết **5 lượt hỏi** và thấy rõ mỗi lượt bổ sung thiếu sót gì của lượt trước.
- Anh chị (hoặc cả lớp) **bắt được chỗ báo cáo tự vênh 95 triệu** và mốc chôn sâu 28/02/2027.
- Anh chị có thư mục `.claude/skills/tom-tat-tai-lieu/` với file `SKILL.md` trong dự án của mình.
- Anh chị **mở file SKILL.md ra xem** và chỉ được mục nào sinh ra từ lượt nào.
- Anh chị nói được: skill sinh ra từ việc làm tay nhiều lần rồi gói chỉ dẫn lặp lại, không phải chép mẫu.
