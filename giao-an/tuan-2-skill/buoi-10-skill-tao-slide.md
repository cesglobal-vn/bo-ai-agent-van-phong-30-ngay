# Buổi 10 - Skill tạo slide: từ tài liệu dài ra bộ slide (giáo án rút gọn)

> **Tuần 2 - Thứ 6** | Thời lượng: 45 phút | Công cụ: **Claude Code**
> **Buổi cuối Tuần 2.** Khép lại phần Skill bằng cách thứ ba để có skill: **cài skill người khác đã viết sẵn**.
> **Định dạng giáo án:** đây là bản **rút gọn** - trọng tâm là **chuỗi 3 câu lệnh**, giảng viên tự dẫn dắt theo văn phong của mình. Các buổi 1-9 có kịch bản chi tiết để tham chiếu văn phong.
> **Xưng hô:** giảng viên xưng **"em"**, gọi học viên là **"anh chị"**.

---

## A. Chuẩn bị trước buổi học

**Giảng viên:**
- Claude Code chạy được; **đã chạy trước trọn 3 bước ở nhà** (đặc biệt bước cài skill - cần mạng, có thể mất một lúc).
- Gửi TRƯỚC vào nhóm: `tai-lieu-mau-bao-cao-xu-huong-ai-2026.md` + file `buoi-10-skill-tao-slide.md` (3 câu lệnh).
- Kiểm tra mạng phòng học - bước 2 phải tải skill từ GitHub về.

**Học viên:**
- Claude Code + thư mục dự án `hoc-ai-agent` (đã có từ buổi 8).
- File `tai-lieu-mau-bao-cao-xu-huong-ai-2026.md` đặt trong thư mục `tai-lieu` (**giữ nguyên tên file**).
- 1 tài liệu thật muốn biến thành slide (hoặc dùng bản tóm tắt do skill buổi 9 tạo ra).

**Mục tiêu:**
- Biến một tài liệu dài thành **dàn ý slide** có cấu trúc, giữ nguyên số liệu, không bịa thêm.
- **Cài được skill của người khác** từ GitHub vào `.claude/skills/` cấp dự án.
- Ra được **bộ slide HTML hoàn chỉnh**, mở bằng trình duyệt, trình chiếu được.

---

## B. Trình tự buổi học (45 phút)

### Bước 0 [00:00 - 05:00] - Điểm đau và ý chính của buổi

**Điểm đau:** báo cáo viết xong rồi vẫn phải ngồi làm slide - chọn bố cục, gõ lại từng ý, canh chữ, chọn màu. Mất 30-45 phút cho một bộ slide, mà nội dung thì đã có sẵn trong tài liệu.

**Hai ý chính cần chốt ngay đầu buổi:**

1. **Tách làm hai việc: nội dung trước, hình thức sau.** Bước 1 chỉ lo *nói gì* (dàn ý). Bước 3 mới lo *trông thế nào* (slide đẹp). Trộn hai việc vào một câu lệnh thì ra slide vừa xấu vừa sai số liệu.
2. **Skill không nhất thiết phải tự viết.** Buổi 7 nhờ Claude đóng gói, buổi 8 tự sinh từ các lượt hỏi. Hôm nay: **cài skill người khác đã viết sẵn** - có cả một kho skill mở ngoài kia.

### Bước 1 [05:00 - 16:00] - Tài liệu dài thành dàn ý slide

Cả lớp cùng chạy trên file mẫu:

```
Đọc file tai-lieu/tai-lieu-mau-bao-cao-xu-huong-ai-2026.md và chuyển thành nội dung slide theo format:

Title: <tên bài ngắn gọn>

Slide N:
<tên slide ngắn, 3-7 chữ>
1. <ý ngắn, giữ số liệu/tên riêng>
2. <ý ngắn>
n. <...>

Không thêm thông tin ngoài file. Thêm 1 slide mở đầu (tóm tắt bối cảnh) và 1 slide kết (khuyến nghị hành động).
```

**Giảng viên giải thích 4 điểm trong câu lệnh này (đây là phần dạy chính của bước 1):**

| Chi tiết trong câu lệnh | Vì sao cần |
|---|---|
| **Format cố định** (Title / Slide N / ý đánh số) | Để bước 3 máy đọc được và dựng đúng từng slide. Dàn ý viết tự do thì skill phải đoán. |
| **"giữ số liệu/tên riêng"** | Slide mất số là slide vô dụng. Bắt nó giữ nguyên 285.9 tỷ USD, 88%, 5.427 trung tâm dữ liệu... |
| **"Không thêm thông tin ngoài file"** | Đúng quy tắc chống bịa của buổi 9. Slide bịa số mang đi họp là tai họa. |
| **Thêm slide mở đầu + slide kết** | Chuẩn trình bày: mở bằng bối cảnh, đóng bằng khuyến nghị hành động. Tài liệu gốc không có sẵn hai slide này. |

**Kiểm kết quả cùng lớp:** đối chiếu vài con số trong dàn ý với file gốc (đầu tư Mỹ **285.9 tỷ USD** gấp 23 lần Trung Quốc; **88%** tổ chức đã áp dụng AI; **5.427** trung tâm dữ liệu; sự cố AI **362** vụ so với 233 vụ năm 2024). Sai một số là dừng lại sửa ngay.

> **Anh chị giữ lại kết quả này** - lát nữa bước 3 sẽ dán vào.

### Bước 2 [16:00 - 27:00] - Cài skill tạo slide từ GitHub

```
https://github.com/zarazhangrui/frontend-slides cài đặt skill này vào folder skill cấp project (.claude/skills/) vào folder hiện tại cho tôi đi
```

**Giảng viên nói rõ 3 điều:**

1. **Skill này làm gì:** tạo bài trình chiếu dạng **một file HTML duy nhất** - tỷ lệ 16:9, không cần cài thêm phần mềm nào, mở bằng trình duyệt là chạy, xuất PDF được. Nó còn cho **chọn phong cách** trước khi dựng.
2. **Cấp dự án vs cấp người dùng:**
   - `.claude/skills/` (trong thư mục dự án) = skill **chỉ dùng cho dự án này** - đúng cái mình đang làm.
   - `~/.claude/skills/` (trong thư mục người dùng) = skill dùng được ở **mọi dự án**.
   - Ai muốn dùng skill slide ở mọi nơi thì lát nữa copy sang thư mục người dùng.
3. **Lưu ý an toàn - phải nhắc:** cài skill từ internet là nhận chỉ dẫn của người lạ cho AI của mình. Nhắc lại nguyên tắc buổi 7: **chỉ dùng skill từ nguồn tin cậy**. Trước khi dùng, bảo Claude đọc qua:

```
Tóm tắt cho tôi skill vừa cài làm gì, cần những gì để chạy, và có yêu cầu gì đáng lưu ý không.
```

### Bước 3 [27:00 - 38:00] - Dùng skill tạo slide

Dán nguyên dàn ý ở Bước 1 vào sau câu lệnh:

```
Sử dụng skill frontend-slides để tạo slide cho tôi. Đây là nội dung:

<dán nguyên dàn ý Title / Slide 1 / Slide 2... ở Bước 1 vào đây>
```

**Diễn biến cần biết trước để không lúng túng:**
- Skill thường **hỏi chọn phong cách** trước khi dựng - cứ chọn một cái, không có đáp án đúng sai.
- Kết quả là **một file HTML**. Mở bằng trình duyệt, bấm mũi tên để chuyển slide, trình chiếu toàn màn hình.
- **Chỉnh bằng tiếng Việt**, mỗi lần một ý: *"đổi màu chủ đạo sang xanh dương"*, *"slide 4 chữ hơi nhỏ, tăng cỡ chữ"*, *"thêm số trang ở góc dưới"*.
- Muốn bản gửi sếp: *"xuất giúp tôi ra PDF"*.

**Nhắc lại:** vẫn phải tự kiểm số liệu trên slide trước khi mang đi họp - qua ba bước máy làm, sai một chỗ là sai cả bộ.

### Bước 4 [38:00 - 43:00] - Thực hành với tài liệu thật

Lặp lại đúng 3 bước với tài liệu của mình.

**Ai chưa có tài liệu:** dùng luôn **bản tóm tắt mà skill buổi 9 đã tạo ra**. Đây là điểm đáng nhấn mạnh:

> Skill tóm tắt (buổi 9) ra nội dung -> Skill slide (buổi 10) ra bộ slide. **Hai skill nối thành một dây chuyền**: tài liệu 14 trang vào đầu này, bộ slide ra đầu kia. Đó chính là thứ Tuần 3 sẽ dạy thành bài bản.

### Bước 5 [43:00 - 45:00] - Tổng kết Tuần 2 và giao bài

**Ba cách để có một skill (chốt cả Tuần 2):**

| Cách | Học ở buổi | Khi nào dùng |
|---|---|---|
| Nhờ Claude đóng gói việc mình vừa làm | Buổi 07 | Việc mình đã làm ưng ý, muốn lặp lại y hệt |
| Tự sinh từ các lượt mình phải hỏi đi hỏi lại | Buổi 08 | Việc phức tạp, cần đúng thứ tự và đủ bước |
| **Cài skill người khác viết sẵn** | Buổi 10 | Việc chuyên môn cao (làm slide, xử lý ảnh...) - có người làm tốt rồi |

**Bài tập về nhà buổi 10:**
1. Làm 1 bộ slide từ **tài liệu thật** của mình, đủ 3 bước. Xuất PDF, đăng nhóm lớp.
2. Thử **nối 2 skill**: lấy 1 tài liệu dài -> skill tóm tắt (buổi 9) -> skill slide (buổi 10).
3. Nếu thấy dùng nhiều: copy skill slide sang thư mục người dùng để mọi dự án đều dùng được.
4. Viết 1 dòng tổng kết Tuần 2: skill nào tiết kiệm cho mình nhiều thời gian nhất.

**Teaser Tuần 3:** hôm nay anh chị đã nối tay 2 skill với nhau - copy kết quả cái này dán sang cái kia. Tuần 3 mình dạy cách để **chúng tự chuyển việc cho nhau**: mỗi trợ lý giỏi một vai, hợp thành một đội chạy trọn quy trình.

---

## C. Checklist chuẩn bị của giảng viên

- [ ] Đã chạy trước trọn 3 bước ở nhà, **đặc biệt bước cài skill** (cần mạng, có thể lâu).
- [ ] Kiểm tra mạng phòng học trước giờ dạy - bước 2 tải skill từ GitHub.
- [ ] Gửi vào nhóm TRƯỚC giờ học: `tai-lieu-mau-bao-cao-xu-huong-ai-2026.md` + file 3 câu lệnh.
- [ ] Chuẩn bị sẵn **1 bộ slide mẫu đã dựng** để chiếu ngay đầu buổi cho lớp thấy đích đến.
- [ ] Canh giờ: nếu bước 2 (cài skill) chậm, rút ngắn Bước 4 và giao thành bài tập. Không cắt phần giải thích 4 điểm ở Bước 1.
- [ ] Chuẩn bị lời tổng kết Tuần 2 (bảng "ba cách có skill") + teaser Tuần 3.
- [ ] Link ghi hình buổi học.

**Tình huống hay gặp:**

| Tình huống | Cách xử lý |
|---|---|
| Cài skill lỗi / mạng chậm | Cho ghép cặp với máy đã cài xong; hoặc GV chia sẻ màn hình làm chung |
| Skill không tự nạp khi tạo slide | Gọi thẳng tên: "dùng skill frontend-slides để..." |
| Dàn ý bước 1 sai/thiếu số liệu | Dừng lại sửa ngay ở bước 1, đừng để lỗi trôi sang bước 3 |
| Slide ra tiếng Anh | Yêu cầu: "toàn bộ slide bằng tiếng Việt" |
| Học viên muốn dùng skill ở dự án khác | Hướng dẫn copy sang `~/.claude/skills/` (cấp người dùng) |

## D. Tiêu chí hoàn thành buổi 10

- Anh chị ra được **dàn ý slide đúng format**, giữ nguyên số liệu, không thêm thông tin ngoài tài liệu.
- Anh chị **cài được skill từ GitHub** vào `.claude/skills/` của dự án và biết khác biệt cấp dự án / cấp người dùng.
- Anh chị có **1 file slide HTML** mở được bằng trình duyệt và trình chiếu được.
- Anh chị chỉnh được slide bằng tiếng Việt ít nhất 1 lần và biết cách xuất PDF.
- Anh chị nói được **ba cách để có một skill** (đóng gói / tự sinh / cài sẵn).
- Anh chị hiểu nguyên tắc **tách nội dung và hình thức** và vì sao phải kiểm số liệu ở từng bước.
