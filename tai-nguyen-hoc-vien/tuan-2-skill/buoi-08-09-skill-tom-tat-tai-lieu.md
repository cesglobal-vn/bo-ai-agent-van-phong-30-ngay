# Skill tóm tắt tài liệu - Các câu lệnh (Buổi 08 + 09)

> **File này CỐ Ý không kèm sẵn nội dung `SKILL.md` để anh chị chép.**
> Skill phải do chính anh chị sinh ra từ 5 lượt hỏi ở Buổi 08 - đó mới là bài học. Chép một file mẫu rơi từ trên trời xuống thì anh chị sẽ không biết vì sao nó có từng mục, và sau này không tự làm được skill cho việc của mình.
>
> **Công cụ:** Claude Code (đã cài từ bài tập Buổi 07).
> **Chuẩn bị:** thư mục dự án (ví dụ `hoc-ai-agent`), bên trong có thư mục `tai-lieu` chứa:
> - `tai-lieu-mau-bao-cao-tong-ket-2026.pdf` (14 trang - dùng ở Buổi 08)
> - `tai-lieu-mau-hop-dong-dich-vu.pdf` (hợp đồng mẫu từ Buổi 02 - dùng ở Buổi 09)
>
> **Giữ nguyên tên file, đừng đổi tên** - các câu lệnh bên dưới trỏ đúng theo tên này.

---

## Skill trong Claude Code là gì

- Skill là một **thư mục** trong dự án: `.claude/skills/<tên-skill>/`, bên trong có file **`SKILL.md`**. **Tên thư mục chính là tên skill.**
- Trong `SKILL.md`: phần đầu ghi `name` (tên) và `description` (mô tả **dùng khi nào**); phần thân là các bước chỉ dẫn cho AI.
- **Claude tự nạp skill nhờ dòng `description`.** Mô tả càng rõ "dùng khi nào" thì Claude càng biết lúc nào lôi skill ra dùng. Mô tả mờ thì phải gọi thẳng tên skill.

---

# BUỔI 08 - Sinh ra skill từ 5 lượt hỏi

Làm lần lượt, không nhảy cóc. Mỗi lượt sẽ trở thành một mục trong skill.

### Lượt 1 - Tóm tắt kiểu thông thường

```
Tóm tắt giúp tôi báo cáo trong tai-lieu/tai-lieu-mau-bao-cao-tong-ket-2026.pdf
```

Kết quả sẽ chung chung, chưa bóc đủ số liệu, chưa gom hạn chót. **Đó là chủ ý** - để thấy nó chưa dùng được.

### Lượt 2 - Ép liệt kê theo từng phần

```
Chưa đủ. Liệt kê lại theo từng phần của báo cáo, mỗi phần vài ý chính.
```

> Lượt này sau sẽ thành mục **Ý CHÍNH CHI TIẾT**.

### Lượt 3 - Bóc số liệu và hạn chót

```
Bóc ra mọi con số, mốc thời gian, cam kết quan trọng trong tài liệu.
```

> Lượt này sau sẽ thành mục **SỐ LIỆU, NGÀY THÁNG, HẠN CHÓT**.
> *Để ý xem nó có nhặt được mốc nằm sâu trong phụ lục không.*

### Lượt 4 - Hỏi chỗ bất lợi, mâu thuẫn, mập mờ (lượt đáng tiền nhất)

```
Trong báo cáo này có điều khoản nào bất lợi, chỗ nào mâu thuẫn, hoặc chỗ nào mập mờ không?
```

> Lượt này sau sẽ thành mục **ĐIỂM CẦN LƯU Ý / RỦI RO**.
> *Nếu nó chưa nêu chỗ số liệu vênh nhau, hỏi thêm:*

```
Kiểm tra lại xem các bảng số liệu trong báo cáo có cộng khớp với con số tổng nêu ở phần đầu không.
```

### Lượt 5 - Chặn suy đoán và rút gọn

```
Trong những gì bạn vừa trả lời, có chỗ nào bạn tự suy đoán mà tài liệu không nói không? Từ giờ chỉ dùng thông tin có trong tài liệu, chỗ nào tài liệu không nói thì ghi "Tài liệu không đề cập", không được đoán. Rút lại giúp tôi 3 tới 5 gạch đầu dòng quan trọng nhất để tôi gửi sếp.
```

> Lượt này sau sẽ thành mục **QUY TẮC** + mục **TÓM TẮT NHANH**.

### Bước cuối - Đóng gói 5 lượt thành skill

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

Claude sẽ tạo file `.claude/skills/tom-tat-tai-lieu/SKILL.md`. **Mở file đó ra xem:**

```
Mở file .claude/skills/tom-tat-tai-lieu/SKILL.md cho tôi xem
```

Đối chiếu từng mục với 5 lượt vừa hỏi:

| Trong SKILL.md | Sinh ra từ |
|---|---|
| TÓM TẮT NHANH | Lượt 5 |
| Ý CHÍNH CHI TIẾT | Lượt 2 |
| SỐ LIỆU, NGÀY THÁNG, HẠN CHÓT | Lượt 3 |
| ĐIỂM CẦN LƯU Ý / RỦI RO | Lượt 4 |
| QUY TẮC | Lượt 5 |

> **Câu cần nhớ:** skill không phải mẫu tải ở đâu về - nó là **biên bản của những lượt mình đã phải hỏi**, ghi lại một lần để khỏi phải hỏi nữa.

---

# BUỔI 09 - Tái dùng skill và kiểm chống bịa

### 1. Chạy skill trên hợp đồng - chỉ một câu

```
Tóm tắt hợp đồng trong tai-lieu/tai-lieu-mau-hop-dong-dich-vu.pdf
```

Không nhắc tới skill, không dặn 5 mục. Claude tự nạp skill nhờ dòng `description`.

**Tự nghiệm thu - bản tóm tắt phải bóc đúng:**
- Tổng giá trị **1.320.000.000 đồng** (đã gồm VAT 10%); thanh toán **3 đợt**: 528 / 528 / 264 triệu.
- Gói Doanh nghiệp **tối đa 50 người dùng đồng thời**; đào tạo **5 lớp**.
- Ký **05/01/2026**; golive **10/04/2026**; bảo hành 12 tháng tới **10/04/2027**.
- **Điều khoản bất lợi cần bắt được:**
  - Bảo trì **tự động gia hạn thêm 12 tháng** trừ khi báo bằng văn bản **trước 30 ngày**.
  - Nghiệm thu trong **5 ngày làm việc**, quá hạn không ý kiến thì **coi như đã nghiệm thu**.
  - Phạt chậm thanh toán **0,5%/ngày** trong khi chậm tiến độ chỉ **0,3%/ngày** - không cân xứng.
  - Bảo mật hiệu lực **3 năm** sau chấm dứt; vi phạm phạt **200.000.000 đồng**.

> **So sánh:** báo cáo hôm trước mất **5 lượt**; hợp đồng này chỉ **1 câu**. Đó là toàn bộ giá trị của skill.

### 2. Bẫy chống bịa (bắt buộc thử)

```
Trong hợp đồng này, nếu tôi muốn tăng từ 50 lên 80 người dùng thì phải trả thêm bao nhiêu tiền?
```

**Đáp án đúng:** hợp đồng **không đề cập** đơn giá cho người dùng bổ sung (Điều 2.4 chỉ nói bổ sung phạm vi phải thống nhất bằng văn bản qua phụ lục). **Không được đưa ra con số nào.**

> **Cái bẫy:** Phụ lục 02 có dòng "bản quyền gói 50 user - 480.000.000". Một câu trả lời nhanh nhảu sẽ lấy 480 chia 50 rồi nhân 30, ra một con số nghe rất hợp lý và hoàn toàn bịa. Hợp đồng chưa bao giờ nói giá tính theo đầu người.

Thử thêm:

```
Hợp đồng này có cho phép Bên A chuyển nhượng hợp đồng cho công ty con không?
```

> **Nhớ:** với hợp đồng và số liệu, **thà nói không có còn hơn đoán sai**. Và skill giảm rủi ro chứ không xóa rủi ro - người đọc vẫn phải kiểm.

### 3. Chạy trên tài liệu công việc thật

```
Tóm tắt tài liệu trong tai-lieu/[tên-file-của-anh-chị]
```

Nếu Claude không tự dùng skill, gọi thẳng tên:

```
Dùng skill tom-tat-tai-lieu để tóm tắt tài liệu trong tai-lieu/[tên-file-của-anh-chị]
```

**Rồi kiểm hai thứ:** số liệu có đúng không; có chỗ nào skill ghi "không đề cập" mà thực ra tài liệu **có** nói không.

> Nhớ che thông tin nhạy cảm trước khi đưa tài liệu công việc vào.

### 4. Cho skill lớn dần theo nghề mình

Thêm mục hợp với nghề:

```
Sửa skill tom-tat-tai-lieu: thêm một mục "BÊN CHỊU TRÁCH NHIỆM" liệt kê rõ nghĩa vụ của từng bên.
```

Gợi ý theo nghề: nhân sự thêm *"Điều khoản liên quan tới người lao động"*; kế toán thêm *"Nghĩa vụ thuế và hóa đơn"*; hành chính thêm *"Việc cần làm và hạn chót"*.

**Thử với dòng `description`:** sửa mô tả cho hẹp đúng nghề (ví dụ *"Dùng khi tóm tắt hợp đồng thuê mặt bằng"*), rồi thử lại xem Claude còn tự nạp skill khi đưa vào loại tài liệu khác không. Mô tả càng hẹp thì càng ít tự nạp; càng rõ "dùng khi nào" thì càng nạp đúng lúc.
