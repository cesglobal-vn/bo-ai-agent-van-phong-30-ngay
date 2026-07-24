# Skill - Dặn một lần, dùng mãi (Buổi 07)

> **Skill là gì:** cách để **lưu lại cách làm một công việc** cho Claude. Anh chị dặn kỹ MỘT LẦN, Claude ghi nhớ lại. Từ đó chỉ cần nói một câu ngắn là nó tự làm đúng như vậy, không phải giải thích lại từ đầu.
>
> **Anh chị KHÔNG cần biết lập trình.** Chỉ cần làm một việc cho ưng ý một lần, rồi nhờ Claude ghi nhớ lại.
>
> **Chuẩn bị:** file logo công ty (PNG hoặc SVG, tốt nhất nền trắng).

---

## Skill làm được gì

- Tạo tài liệu **đúng chuẩn công ty** (Word, Excel, PowerPoint, PDF): đúng màu, đúng logo, đúng mẫu.
- Làm đúng **một quy trình nhiều bước** theo thứ tự cố định, không bỏ sót bước.
- Ghi nhớ **quy định, văn phong, cách trình bày riêng** của công ty.
- **Lặp lại chính xác** một công việc mà không cần dặn lại từ đầu.

## Skill KHÔNG phải là gì

Skill **không phải một phần mềm riêng** phải đi cài, **không tự chạy** khi anh chị chưa nhờ tới, và **không thay anh chị hiểu công việc**. Nó chỉ giúp Claude làm lại đúng cách đã thống nhất từ trước - nhanh hơn và đều tay hơn. Trách nhiệm cuối vẫn là của mình.

---

## Ba bước thực hành (làm đúng thứ tự)

### Bước 1 - Nhờ Claude nghiên cứu một chủ đề

```
Research và cho tôi báo cáo về xu hướng phát triển AI trong năm 2026
```

Claude tự tìm kiếm thông tin từ nhiều nguồn trên internet, rồi trả lời ngay trong khung chat. **Ở bước này chỉ quan tâm nội dung, chưa cần quan tâm hình thức đẹp/xấu.**

### Bước 2 - Nhờ tạo file Word đẹp, đúng thương hiệu

**Trước khi gõ:** kéo **file logo công ty** thả vào khung chat. Không đưa logo thì Claude phải tự đoán màu và không có hình để chèn.

```
Tôi thấy nội dung khá chi tiết rồi, bây giờ hãy tổng hợp và tạo cho tôi 1 file docx cho nội dung trên. Sử dụng tone màu của logo công ty của tôi, trong file docx phải có logo kèm theo luôn. Lưu ý file docx phải chuẩn tiếng Việt và không bị lỗi dấu.
```

Claude tạo file Word (.docx) có logo, đúng màu thương hiệu, tự kiểm tra để không lỗi dấu tiếng Việt. **Tải file về và mở ra kiểm bằng mắt:** logo đúng chỗ chưa, màu đúng chưa, có lỗi dấu không. Chưa ưng thì nói tiếp để sửa (ví dụ *"logo nhỏ lại và đưa lên góc phải"*).

**Chỉ sang bước 3 khi đã thật sự ưng ý** - vì mình chỉ đóng gói cái đã ưng.

### Bước 3 - Đóng gói cách làm này thành một Skill

```
Tôi thấy file này đẹp rồi, bây giờ hãy tạo cho tôi skill đóng gói tài liệu đẹp và đúng tone màu như vậy, sau này khi tôi nói tạo tài liệu theo chuẩn <tên công ty của tôi> thì hãy áp dụng skill này cho tôi (logo tôi sẽ cung cấp).
```

> Thay `<tên công ty của tôi>` bằng tên công ty của anh chị.

Claude sẽ **hỏi lại vài câu cho rõ** (khi nào dùng, cần gì thêm) - cứ trả lời bình thường bằng tiếng Việt. Sau đó nó ghi nhớ toàn bộ cách trình bày ở Bước 2 và đóng gói thành Skill.

**QUAN TRỌNG: bấm nút `Save skill`** hiện trong khung chat. Không bấm là đóng chat xong mất công.

---

## Dùng lại Skill

Mở một **cuộc trò chuyện MỚI**, gõ dấu `/` để hiện danh sách skill, chọn skill vừa tạo. Rồi nhờ việc bằng một câu ngắn:

```
Tạo cho tôi tài liệu giới thiệu dịch vụ theo chuẩn <tên công ty của tôi>.
```

Không cần dặn lại màu, không cần dặn chèn logo, không cần dặn kiểm tra lỗi dấu - vẫn ra đúng kiểu tài liệu cũ.

---

## Hai cách tạo Skill

**Cách 1 - Nhờ Claude đóng gói giúp (khuyến nghị, không cần biết code).** Chính là Bước 3 ở trên: làm một việc tới khi ưng ý -> nói *"Hãy đóng gói cách làm này thành một skill để lần sau dùng lại"* -> trả lời vài câu Claude hỏi -> xong.

**Cách 2 - Tự soạn thủ công (cho ai rành kỹ thuật hơn).** Skill về bản chất là một **thư mục** gồm một file hướng dẫn tên **`SKILL.md`** - ghi rõ hai điều: *skill này làm gì* và *khi nào nên dùng nó*. Có thể kèm file phụ trợ: mẫu tài liệu, logo, hình ảnh. Soạn xong thì thử vài câu lệnh mẫu để chắc Claude tự nhận ra và dùng đúng lúc.

> *Buổi 08 anh chị sẽ tự tay làm theo Cách 2.*

## Cách lưu / cài Skill để tái sử dụng

- **Trong ứng dụng Claude:** khi Claude tạo xong Skill, bấm nút **Save skill** hiện trong khung chat.
- **Trên claude.ai (bản web):** vào **Settings -> Skills**, chọn tải lên (upload) file Skill dạng **.zip**. Skill áp dụng riêng cho tài khoản của anh chị.
- **Dùng chung cho cả công ty (gói Team/Enterprise):** quản trị viên cấp phát Skill cho toàn bộ nhân viên, không cần từng người tự tải.

## Lưu ý an toàn

- **Chỉ dùng Skill từ nguồn tin cậy.** Skill là chỉ dẫn cho AI làm việc thay mình - nhận skill lạ về dùng thì rủi ro.
- **Không đưa thông tin nhạy cảm vào bên trong Skill:** mật khẩu, dữ liệu khách hàng, số tài khoản. Skill là thứ để chia sẻ, mà thứ gì chia sẻ được thì đừng cất bí mật trong đó.
