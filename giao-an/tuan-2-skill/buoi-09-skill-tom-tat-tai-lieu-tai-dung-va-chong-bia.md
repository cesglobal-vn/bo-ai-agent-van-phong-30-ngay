# Buổi 09 - Skill tóm tắt tài liệu (2): tái dùng và chống bịa (kịch bản hands-on)

> **Tuần 2 - Thứ 5** | Thời lượng: 45 phút | Công cụ: **Claude Code**
> **Mô hình buổi học:** HANDS-ON. Giảng viên và học viên làm SONG SONG.
> **Buổi nối tiếp buổi 8:** buổi 8 skill được **sinh ra**; buổi 9 chứng minh nó **tái dùng được** trên loại tài liệu khác hẳn, và **không bịa**. Điểm nhấn cả buổi là bài thử chống bịa ở Phần 3 - đừng cắt.
> **Xưng hô:** giảng viên xưng **"em"**, gọi học viên là **"anh chị"**.
> **Định dạng script:** ngoặc vuông `[ ]` là chỉ dẫn thao tác (không đọc to); ngoặc kép `"..."` là lời giảng viên nói gần như nguyên văn; mỗi khối ``` là nội dung copy-dán được.

---

## A. Chuẩn bị trước buổi học

**Giảng viên chuẩn bị:**
- Claude Code chạy được; **đã tự chạy trước skill trên hợp đồng và đã thử câu bẫy bịa ở nhà** - phải biết chắc Claude trả lời thế nào.
- Nhắc anh chị copy lại **file hợp đồng mẫu của buổi 2** (`tai-lieu-mau-hop-dong-dich-vu.pdf`) vào thư mục `tai-lieu` của dự án. Ai làm mất thì trợ giảng gửi lại trong nhóm.
- Slide/bảng ghi lại **so sánh: báo cáo mất 5 lượt - hợp đồng chỉ 1 câu**.
- Xem lại 5 dòng đã ghi trên bảng ở buổi 8 (nếu cùng phòng học thì giữ nguyên bảng).

**Học viên cần có sẵn:**
- Skill `tom-tat-tai-lieu` đã tạo ở buổi 8 (trong `.claude/skills/`).
- File hợp đồng mẫu buổi 2 đặt tại `tai-lieu/tai-lieu-mau-hop-dong-dich-vu.pdf`.
- **1 tài liệu công việc THẬT** của mình (bài tập buổi 8), đã che thông tin nhạy cảm.

**Mục tiêu buổi học:**
- Anh chị chứng kiến skill **tự nạp** nhờ dòng description, chỉ với một câu ngắn.
- Anh chị dùng skill để bóc hợp đồng: số tiền, ngày tháng, hạn chót, **điều khoản bất lợi**.
- Anh chị hiểu và **tự kiểm chứng** quy tắc chống bịa: tài liệu không nói thì ghi "không đề cập".
- Anh chị chạy skill trên tài liệu công việc thật và biết cách **sửa skill cho hợp nghề mình**.

---

## B. Kịch bản hands-on (45 phút)

### Phần 1 [00:00 - 05:00] - Câu hỏi của buổi hôm nay

> "Em chào anh chị. Hôm qua anh chị đã tự tay sinh ra một skill từ 5 lượt hỏi. Nhưng em đoán trong đầu nhiều anh chị còn một câu hỏi chưa nói ra: **cái skill đó có thật sự dùng lại được không, hay nó chỉ đúng với đúng cái báo cáo hôm qua thôi?**"

> "Hôm nay mình trả lời câu đó bằng cách thử thật. Và em sẽ thử theo cách khó nhất có thể: đưa vào một loại tài liệu **khác hẳn** báo cáo - một bản hợp đồng. Báo cáo thì có doanh thu, có phần La Mã; hợp đồng thì có điều khoản, có phạt, có ngày hiệu lực. Hai loại chẳng liên quan gì nhau."

> "Và em sẽ **chỉ gõ đúng một câu, không nhắc gì tới skill cả**. Xem nó có tự nhận ra không."

> "Hợp đồng em dùng chính là hợp đồng anh chị đã tóm tắt hồi buổi 2, bằng trợ lý Project. Anh chị còn nhớ chứ ạ? Hôm nay mình làm lại đúng việc đó, nhưng bằng skill - để anh chị tự so hai cách."

### Phần 2 [05:00 - 18:00] - Chạy skill trên hợp đồng: chỉ một câu

> "Anh chị mở Claude Code tại thư mục dự án. Đảm bảo file hợp đồng đang nằm trong `tai-lieu`. Rồi gõ đúng một câu này thôi:"

```
Tóm tắt hợp đồng trong tai-lieu/tai-lieu-mau-hop-dong-dich-vu.pdf
```

> "Để ý: em **không** nói 'dùng skill', **không** nhắc 5 mục, **không** dặn chống bịa. Chỉ một câu như nhờ việc bình thường."

[Chờ kết quả.]

> "Anh chị nhìn dòng đầu tiên Claude trả lời - nó thường **báo là đang dùng skill `tom-tat-tai-lieu`**. Đó chính là bằng chứng skill tự nạp. Nhờ cái gì? Nhờ **dòng description** hôm qua em có nhắc - nó ghi rõ skill này dùng khi nào, nên Claude tự nhận ra đây là việc tóm tắt tài liệu."

**Kiểm kết quả - đối chiếu với hợp đồng thật:**

> "Giờ mình nghiệm thu. Anh chị dò bản tóm tắt xem có đúng mấy điểm này không:"

*Kết quả mong đợi - bản tóm tắt phải đủ 5 mục của skill, và các con số phải khớp hợp đồng:*

- **Số liệu:** tổng giá trị **1.320.000.000 đồng** (đã gồm VAT 10%; trước thuế 1.200.000.000, VAT 120.000.000); thanh toán **3 đợt** - 40% = **528.000.000**, 40% = **528.000.000**, 20% = **264.000.000**; gói Doanh nghiệp **tối đa 50 người dùng đồng thời**; đào tạo **5 lớp**, mỗi lớp 20 người, 4 giờ.
- **Ngày tháng, hạn chót:** ký **05/01/2026**; triển khai từ **06/01/2026**; golive **10/04/2026**; bảo hành 12 tháng tới **10/04/2027**; đợt 1 hạn **14/01/2026**.
- **Điểm cần lưu ý / rủi ro** - đây là phần đáng tiền nhất:
  - **Tự động gia hạn:** hạng mục bảo trì **tự động gia hạn thêm 12 tháng**, đơn giá tăng không quá 8%/năm, TRỪ KHI một bên báo bằng văn bản **trước 30 ngày**. Không để ý là bị gia hạn.
  - **Nghiệm thu ngầm:** Bên A phải nghiệm thu trong **05 ngày làm việc**; quá hạn mà không có ý kiến bằng văn bản thì **coi như đã nghiệm thu**.
  - **Phạt không cân xứng:** Bên A chậm thanh toán chịu **0,5%/ngày**, trong khi Bên B chậm tiến độ chỉ **0,3%/ngày** (tối đa 10% giá trị hạng mục).
  - **Bảo mật:** hiệu lực **03 năm** sau khi chấm dứt; vi phạm phạt **200.000.000 đồng**.
  - Đơn phương chấm dứt trái quy định: bồi thường **10% giá trị hợp đồng còn lại**.

> **[Giảng viên dừng lại ở ý 'phạt không cân xứng']** "Anh chị để ý chỗ này. Bên mình chậm trả tiền thì bị phạt 0,5% một ngày; bên kia chậm giao hàng thì chỉ 0,3% một ngày. Đọc lướt hợp đồng thì hai con số nằm cách nhau mấy dòng, chẳng ai đặt cạnh nhau để so. Skill nó đặt cạnh nhau giúp mình."

**So sánh - đây là chốt của phần này:**

[Chỉ lên bảng ghi so sánh.]

> "Anh chị so giúp em hai con số. Với báo cáo hôm qua, em mất **5 lượt** mới ra đủ 5 mục. Với hợp đồng hôm nay - một loại tài liệu hoàn toàn khác - em gõ **1 câu**, ra ngay đủ 5 mục, đúng cấu trúc, không sót phần nào."

> "**Đó là toàn bộ giá trị của skill.** Công sức 5 lượt hôm qua không mất đi đâu cả - nó nằm trong file SKILL.md và làm việc thay mình từ giờ trở đi."

### Phần 3 [18:00 - 26:00] - Bẫy nó bịa (điểm nhấn của buổi)

> "Giờ tới phần em thích nhất. Skill chạy ngon rồi, nhưng ngon chưa đủ - mình phải biết **nó có bịa không**. Vì với hợp đồng và số liệu, một con số bịa còn nguy hơn không có số nào."

> "Em sẽ hỏi một câu mà hợp đồng **hoàn toàn không trả lời được**. Anh chị gõ:"

```
Trong hợp đồng này, nếu tôi muốn tăng từ 50 lên 80 người dùng thì phải trả thêm bao nhiêu tiền?
```

[Chờ kết quả. **Đọc chung ít nhất 2 bản của học viên.**]

*Kết quả mong đợi:* Claude trả lời đại ý **"Hợp đồng không đề cập đơn giá cho người dùng bổ sung"**, và có thể dẫn thêm Điều 2.4 - việc bổ sung phạm vi phải được hai bên thống nhất bằng văn bản qua phụ lục bổ sung. **Không được đưa ra một con số.**

> **[Giảng viên nói rõ cái bẫy]** "Anh chị thấy cái bẫy chưa? Trong Phụ lục 02 có dòng: bản quyền gói 50 người dùng, giá 480 triệu. Một cái máy tính nhanh nhảu sẽ lấy 480 chia 50 ra 9,6 triệu một người, rồi nhân 30 người thành 288 triệu, trả lời rất trơn tru và rất tự tin. **Nghe cực kỳ hợp lý. Và hoàn toàn bịa.** Hợp đồng chưa bao giờ nói giá tính theo đầu người."

> "Nếu anh chị mang con số 288 triệu đó đi đàm phán với đối tác, anh chị mất mặt. Đó là lý do trong skill của mình có mục **QUY TẮC**, và đó là mục do chính lượt thứ 5 hôm qua sinh ra."

> **[Nếu có máy nào Claude vẫn bịa ra con số]** - dùng luôn làm bài học: "Máy của chị Hoa vừa cho ra một con số. Cả lớp nhìn: đây chính là thứ mình phải đề phòng. Chị Hoa mở file SKILL.md, xem mục QUY TẮC đã ghi rõ 'không suy đoán' chưa; nếu ghi rồi thì mình nhắc lại nó một câu - và đây là bài học: **skill giảm rủi ro chứ không xóa được rủi ro. Người đọc vẫn phải kiểm.**"

**Thử thêm một câu cho chắc:**

```
Hợp đồng này có cho phép Bên A chuyển nhượng hợp đồng cho công ty con không?
```

> "Câu này hợp đồng cũng không nói. Nó phải trả lời là tài liệu không đề cập, chứ không được suy ra từ điều khoản khác."

> "Anh chị nhớ giúp em một câu: **với hợp đồng và số liệu, thà nói không có còn hơn đoán sai.**"

### Phần 4 [26:00 - 37:00] - Thực hành: tài liệu công việc thật của anh chị

> "Skill của anh chị đã chạy tốt với báo cáo và với hợp đồng mẫu. Giờ mới là phần đáng tiền nhất: **đưa tài liệu thật trong công việc của anh chị vào**. Vẫn cùng một skill đó, không phải tạo lại cái gì cả."

**Các bước anh chị làm:**
1. Đặt tài liệu của mình vào thư mục `tai-lieu` trong dự án (hoặc chỉ cho Claude đường dẫn tới file).
2. Gõ một câu:

```
Tóm tắt tài liệu trong tai-lieu/[tên-file-của-anh-chị]
```

3. Nếu Claude không tự dùng skill, gọi thẳng tên:

```
Dùng skill tom-tat-tai-lieu để tóm tắt tài liệu trong tai-lieu/[tên-file-của-anh-chị]
```

4. **Đọc lại bản tóm tắt và kiểm hai thứ:** số liệu có đúng không; có chỗ nào skill ghi "không đề cập" mà thực ra tài liệu **có** nói không.

> "Bước 4 là bước quan trọng nhất, anh chị đừng bỏ. Mình là người chịu trách nhiệm cuối, không phải AI."

[Đi một vòng, gọi tên 1-2 anh chị, xem kết quả.]

> "Anh Nam ơi, tài liệu của anh là biên bản họp phải không? Anh để ý mục 'Số liệu, ngày tháng, hạn chót' - nó có gom đúng các deadline mà cuộc họp giao không? Còn chị Yến, tài liệu của chị dài quá thì bảo nó 'rút mục Ý chính chi tiết còn mỗi phần 2 gạch đầu dòng' là gọn ngay."

> "Ai có bản tóm tắt ưng ý thì gõ 'xong' vào chat lớp."

### Phần 5 [37:00 - 42:00] - Skill lớn dần theo nghề của anh chị

> "Một điều cuối, và đây là thứ làm skill khác hẳn một file mẫu cứng: **skill lớn dần theo nhu cầu của mình.**"

**Sửa phần thân - thêm mục hợp với nghề:**

> "Nếu anh chị thấy 5 mục chưa đủ cho nghề mình, cứ thêm. Ví dụ ai làm hợp đồng hay cần biết ai chịu trách nhiệm phần nào, thì gõ:"

```
Sửa skill tom-tat-tai-lieu: thêm một mục "BÊN CHỊU TRÁCH NHIỆM" liệt kê rõ nghĩa vụ của từng bên.
```

> "Ai làm nhân sự có thể thêm mục 'Điều khoản liên quan tới người lao động'. Ai làm kế toán thêm mục 'Nghĩa vụ thuế và hóa đơn'. **Đó chính là cách skill lớn dần - mỗi lần thấy thiếu thì bồi thêm một mục, chứ không phải viết lại từ đầu.**"

**Sửa dòng description - dạy Claude biết khi nào nạp:**

> "Anh chị nào làm nhanh thì thử thêm cái này, nó cho anh chị hiểu sâu về description. Sửa dòng mô tả cho **hẹp đúng nghề mình**, ví dụ 'Dùng khi tóm tắt hợp đồng thuê mặt bằng'. Rồi thử lại xem Claude còn tự nạp skill khi anh chị đưa vào một loại tài liệu khác không."

> "Anh chị sẽ thấy: **mô tả càng hẹp thì nó càng ít tự nạp; mô tả càng rõ 'dùng khi nào' thì nó càng nạp đúng lúc.** Đây là nghề chỉnh skill, làm nhiều sẽ quen."

### Phần 6 [42:00 - 45:00] - Tổng kết và giao bài

> "Chốt lại hai buổi 8 và 9. Anh chị đã đi trọn một vòng: từ hỏi tay 5 lượt, tới đóng gói thành skill, tới dùng lại chỉ bằng một câu trên tài liệu khác hẳn, và tự kiểm chứng nó không bịa."

- Skill **tự nạp** nhờ dòng `description` - nên mô tả phải ghi rõ *dùng khi nào*.
- Cùng một skill dùng được cho **nhiều loại tài liệu** khác nhau: báo cáo, hợp đồng, biên bản.
- **Chống bịa là mục bắt buộc**: tài liệu không nói thì ghi "không đề cập". Nhưng skill giảm rủi ro chứ không xóa rủi ro - **người đọc vẫn phải kiểm**.
- Skill **lớn dần**: thấy thiếu mục nào thì bồi thêm mục đó.

**Bài tập về nhà buổi 9:**
1. Chạy skill trên **thêm 2 tài liệu thật** khác loại nhau (ví dụ 1 hợp đồng + 1 biên bản họp).
2. **Bồi thêm ít nhất 1 mục** vào skill cho hợp nghề mình, rồi chạy lại để xem mục mới có ra không.
3. Thử **bẫy bịa** trên tài liệu của mình: hỏi một câu mà tài liệu chắc chắn không trả lời được, xem skill có ghi "không đề cập" không. Chụp màn hình đăng nhóm lớp.
4. Nhớ lại việc lặp lại anh chị đã kể ở buổi 8 (còn ghi trên bảng) - viết ra **5 câu hỏi** anh chị thường phải hỏi cho việc đó. Đó chính là phôi của skill tiếp theo.

> "Ngày mai là buổi cuối Tuần 2, mình khép lại phần Skill. Rồi sang Tuần 3 mình bước lên một mức nữa: thay vì một trợ lý làm một việc, anh chị sẽ có **cả một đội trợ lý**, mỗi trợ lý giỏi một việc và phối hợp với nhau. Cảm ơn anh chị, hẹn gặp lại."

[Kết thúc buổi. Trợ giảng thu lại các ảnh chụp bài "bẫy bịa" để lớp học chéo; ghi nhận anh chị nào skill đã có mục riêng theo nghề.]

---

## C. Checklist chuẩn bị của giảng viên

- [ ] **Đã tự chạy trước** skill trên hợp đồng + đã thử câu bẫy bịa ở nhà, biết chắc Claude trả lời ra sao.
- [ ] Nhắc anh chị copy hợp đồng mẫu buổi 2 vào `tai-lieu/tai-lieu-mau-hop-dong-dich-vu.pdf`; trợ giảng gửi lại file cho ai mất.
- [ ] Kiểm trước giờ học: mọi máy còn thư mục `.claude/skills/tom-tat-tai-lieu/` từ buổi 8.
- [ ] Slide/bảng ghi so sánh **"báo cáo 5 lượt - hợp đồng 1 câu"**.
- [ ] Canh giờ: nếu trễ, rút ngắn Phần 5 (skill lớn dần) và giao thành bài tập. **Tuyệt đối không cắt Phần 3 (bẫy bịa)** - đó là điểm nhấn cả buổi.
- [ ] Chuẩn bị cách xử lý khi có máy Claude vẫn bịa ra con số (đã có trong Phần 3) - biến thành bài học, đừng lúng túng.
- [ ] Link ghi hình buổi học.

**Tình huống hay gặp:**

| Tình huống | Cách xử lý |
|---|---|
| Claude không tự nạp skill | Cho gọi thẳng tên skill; giải thích do dòng description chưa rõ "dùng khi nào" - dùng luôn làm bài học Phần 5 |
| Claude vẫn bịa ra con số ở câu bẫy | Biến thành bài học: skill giảm rủi ro chứ không xóa; kiểm lại mục QUY TẮC trong SKILL.md |
| Tài liệu thật của học viên có thông tin nhạy cảm | Nhắc che/ẩn trước; hoặc dùng tạm tài liệu mẫu của lớp |
| Bản tóm tắt tài liệu thật quá dài | Cho gõ yêu cầu rút gọn từng mục; không sửa skill vội |
| Học viên hỏi skill này có dùng được trên claude.ai không | Giải thích: cùng khái niệm, khác chỗ lưu - buổi 7 là bản Claude tự gói, buổi 8-9 là bản file trong dự án |

## D. Tiêu chí hoàn thành buổi 9

- Anh chị chạy được skill trên hợp đồng **chỉ bằng một câu**, không nhắc tên skill, và thấy Claude tự nạp.
- Bản tóm tắt hợp đồng đủ 5 mục, số liệu khớp: **1,32 tỷ**, 3 đợt **528/528/264**, **50 người dùng**, golive **10/04/2026**.
- Anh chị chỉ ra được ít nhất 2 điều khoản bất lợi (tự động gia hạn; nghiệm thu ngầm 5 ngày; hoặc phạt 0,5% so với 0,3%).
- Anh chị tự chạy bài **bẫy bịa** và thấy skill trả lời "tài liệu không đề cập" (hoặc hiểu vì sao nó bịa và phải kiểm).
- Anh chị chạy skill trên **tài liệu công việc thật** của mình và đã kiểm lại số liệu.
- Anh chị biết cách **bồi thêm mục** vào skill và hiểu vai trò của dòng `description`.
