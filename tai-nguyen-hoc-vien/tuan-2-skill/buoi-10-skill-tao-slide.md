# Skill tạo slide - Các câu lệnh (Buổi 10)

> **Công cụ:** Claude Code (đã cài từ buổi 08).
> **Chuẩn bị:** thư mục dự án `hoc-ai-agent`, bên trong thư mục `tai-lieu` chứa `tai-lieu-mau-bao-cao-xu-huong-ai-2026.md` (**giữ nguyên tên file**).
>
> **Nguyên tắc của buổi này: tách làm hai việc.**
> Bước 1 lo **nội dung** (nói gì). Bước 3 lo **hình thức** (trông thế nào). Gộp hai việc vào một câu lệnh thì slide vừa xấu vừa dễ sai số liệu.

---

## Bước 1 - Biến tài liệu dài thành dàn ý slide

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

> Dùng cho tài liệu của mình thì đổi đường dẫn file, giữ nguyên phần format phía dưới.

**Vì sao câu lệnh phải có từng chi tiết đó:**

| Chi tiết | Vì sao |
|---|---|
| Format cố định (Title / Slide N / ý đánh số) | Để bước 3 dựng đúng từng slide, khỏi phải đoán |
| "giữ số liệu/tên riêng" | Slide mất số là slide vô dụng |
| "Không thêm thông tin ngoài file" | Quy tắc chống bịa - slide bịa số mang đi họp là tai họa |
| Thêm slide mở đầu + slide kết | Chuẩn trình bày: mở bằng bối cảnh, đóng bằng khuyến nghị |

**Kiểm ngay:** dò vài con số trong dàn ý với tài liệu gốc. Sai một số thì sửa ngay tại bước này, đừng để trôi sang bước sau.

**Giữ lại kết quả bước này** - bước 3 sẽ dán vào.

---

## Bước 2 - Cài skill tạo slide

```
https://github.com/zarazhangrui/frontend-slides cài đặt skill này vào folder skill cấp project (.claude/skills/) vào folder hiện tại cho tôi đi
```

**Skill này làm gì:** tạo bài trình chiếu dạng **một file HTML duy nhất** - tỷ lệ 16:9, không cần cài thêm phần mềm, mở bằng trình duyệt là chạy, xuất PDF được. Nó cho **chọn phong cách** trước khi dựng.

**Cấp dự án hay cấp người dùng:**
- `.claude/skills/` (trong thư mục dự án) = skill **chỉ dùng cho dự án này**.
- `~/.claude/skills/` (thư mục người dùng) = skill dùng được ở **mọi dự án**. Nếu hay làm slide, copy sang đây.

**An toàn - đọc trước khi dùng:** cài skill từ internet là nhận chỉ dẫn của người lạ cho AI của mình. **Chỉ dùng skill từ nguồn tin cậy.** Nên bảo Claude đọc qua trước:

```
Tóm tắt cho tôi skill vừa cài làm gì, cần những gì để chạy, và có yêu cầu gì đáng lưu ý không.
```

---

## Bước 3 - Tạo slide từ dàn ý

```
Sử dụng skill frontend-slides để tạo slide cho tôi. Đây là nội dung:

<dán nguyên dàn ý Title / Slide 1 / Slide 2... ở Bước 1 vào đây>
```

**Những gì sẽ xảy ra:**
- Skill thường **hỏi chọn phong cách** trước khi dựng - chọn cái nào cũng được, không có đúng sai.
- Kết quả là **một file HTML**. Mở bằng trình duyệt, bấm mũi tên để chuyển slide, trình chiếu toàn màn hình.

**Chỉnh bằng tiếng Việt, mỗi lần một ý:**

```
Đổi màu chủ đạo sang xanh dương.
```
```
Slide 4 chữ hơi nhỏ, tăng cỡ chữ lên.
```
```
Thêm số trang ở góc dưới mỗi slide.
```
```
Toàn bộ slide bằng tiếng Việt.
```

**Xuất bản gửi sếp:**

```
Xuất giúp tôi ra PDF.
```

---

## Mẹo: nối 2 skill thành dây chuyền

Tài liệu dài -> **skill tóm tắt** (buổi 09) ra nội dung -> **skill slide** (buổi 10) ra bộ slide.

Một tài liệu 14 trang vào đầu này, bộ slide trình chiếu ra đầu kia. Ai chưa có tài liệu để tập thì lấy luôn bản tóm tắt skill buổi 09 đã tạo.

## Nhắc cuối

Qua ba bước đều là máy làm - **sai một chỗ là sai cả bộ slide**. Trước khi mang đi họp, tự dò lại các con số quan trọng trên slide với tài liệu gốc. AI dựng nháp, người trình bày chịu trách nhiệm.
