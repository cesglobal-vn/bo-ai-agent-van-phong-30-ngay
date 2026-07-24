# Buổi 06 - Artifact: biến mô tả thành ứng dụng dùng được (kịch bản hands-on)

> **Tuần 2 - Thứ 2** | Thời lượng: 45 phút | Công cụ: Claude Artifacts (claude.ai)
> **Mô hình buổi học:** HANDS-ON. Trình tự: Giới thiệu -> điểm đau -> rồi mới vào thực hành từng bước. Giảng viên và học viên làm SONG SONG.
> **Buổi mở đầu Tuần 2:** vẫn trên claude.ai, VẪN KHÔNG CÀI GÌ. Tuần 1 anh chị dạy trợ lý *viết ra chữ*; tuần này bắt đầu bằng việc bảo nó *làm ra công cụ dùng được*. Claude Code chỉ xuất hiện từ buổi 8, đừng nhắc sớm kẻo lớp lo lắng.
> **Xưng hô:** giảng viên xưng **"em"**, gọi học viên là **"anh chị"**.
> **Định dạng script:** ngoặc vuông `[ ]` là chỉ dẫn thao tác (không đọc to); ngoặc kép `"..."` là lời giảng viên nói gần như nguyên văn; mỗi khối ``` là nội dung copy-dán được.

---

## A. Chuẩn bị trước buổi học

**Giảng viên chuẩn bị:**
- Claude đăng nhập sẵn, đã mở sẵn mục **Artifacts** ở thanh bên trái.
- **Tự dựng trước cả 4 ứng dụng mẫu** ở nhà, mỗi cái giữ lại 1 link chia sẻ để chiếu nhanh khi giới thiệu. Quan trọng: biết trước cái nào Claude hay dựng chậm để canh giờ.
- Gửi TRƯỚC vào nhóm lớp: file `buoi-06-thu-vien-prompt-artifact.md` (4 câu lệnh mẫu đầy đủ, học viên chỉ copy-dán).
- Slide tiêu đề + slide "bảng Excel theo dõi việc và những lần quên follow-up".

**Học viên cần có sẵn (nhắn nhóm trước 1 tiếng):**
- Máy tính, tài khoản Claude (đã dùng suốt Tuần 1).
- Nghĩ trước 1 việc mình đang theo dõi thủ công bằng Excel/giấy nhớ/Zalo (danh sách khách, đơn hàng, bài đăng, chi phí...).

**Mục tiêu buổi học:**
- Anh chị hiểu Artifact là gì và khác câu trả lời chat ở chỗ nào (đọc được vs **dùng được**).
- Anh chị tự tay dựng ít nhất 2 ứng dụng: 1 cái làm chung cả lớp, 1 cái tự chọn theo nghề của mình.
- Anh chị biết chỉnh ứng dụng bằng tiếng Việt, chia sẻ link cho đồng nghiệp, và tải về máy dùng offline.

---

## B. Kịch bản hands-on (45 phút)

### Phần 1 [00:00 - 06:00] - Giới thiệu và điểm đau

[Chào lớp, chúc mừng đã qua Tuần 1.]

> "Em chào anh chị, mình bước sang Tuần 2. Tuần vừa rồi anh chị đã có 5 trợ lý và làm chủ cả 4 tính năng của Project. Tin vui cho buổi hôm nay: vẫn chạy trên claude.ai, vẫn không phải cài đặt gì cả."

[Slide "bảng Excel theo dõi việc".]

> "Em hỏi anh chị một câu. Việc theo dõi hằng ngày của anh chị đang nằm ở đâu? [Chờ vài phản hồi.] Đa số là: một file Excel, vài tờ giấy nhớ dán màn hình, với một đoạn chat Zalo tự gửi cho chính mình. Nó chạy được, nhưng nó không nhắc mình, không tự tính, và mỗi lần muốn xem tổng thì phải ngồi cộng tay."

> "Em kể một tình huống. Chị Thu làm kinh doanh, cùng lúc chăm mười mấy khách. Khách nào đã báo giá, khách nào đang chờ ký, khách nào lâu rồi chưa gọi lại - tất cả nằm trong đầu chị và một file Excel. Tháng trước chị mất một hợp đồng, lý do đơn giản: quên follow-up đúng hai tuần. Không phải chị lười, chỉ là cái file Excel đó không biết nhắc."

> "Thứ chị Thu cần không phải một câu trả lời hay. Chị cần một cái bảng biết tự tô đỏ khách nào lâu chưa liên hệ. Tức là cần một ứng dụng. Và đây là chỗ khác biệt của buổi hôm nay."

> "Tuần 1 anh chị bảo Claude viết ra CHỮ: email, tóm tắt, biên bản, kế hoạch, báo cáo. Đọc xong là xong. Hôm nay anh chị sẽ bảo nó làm ra một thứ DÙNG ĐƯỢC: bấm nút được, nhập số vào được, nó tự tính, tự tô màu. Cái đó gọi là **Artifact**."

> "Và điều em muốn anh chị nhớ nhất: mình không viết một dòng code nào. Mình chỉ mô tả bằng tiếng Việt, y như đang nhắn cho một bạn lập trình viên ngồi cạnh. Mình bắt đầu, anh chị mở máy ra nhé."

### Phần 2 [06:00 - 09:00] - Mở khu Artifacts

> "Anh chị vào claude.ai. Nhìn thanh bên trái, tìm mục **Artifacts**, bấm vào. Đây là nơi chứa mọi ứng dụng anh chị tạo ra - giống như Projects là nơi chứa các trợ lý ở Tuần 1 vậy."

> "Bấm tiếp nút **New artifact**. Anh chị sẽ thấy một ô để mô tả. Toàn bộ công việc hôm nay chỉ là: gõ mô tả vào ô đó, nhấn Enter, rồi chờ."

[Chờ cả lớp mở đúng màn hình. Đi kiểm nhanh vài máy.]

> "Ai đang thấy ô mô tả trống thì gõ '1' vào chat lớp cho em biết nhé."

> "Một điều để anh chị yên tâm về bố cục màn hình: bên TRÁI vẫn là khung chat như mọi khi, bên PHẢI là khung ứng dụng. Muốn sửa gì thì nói ở khung trái, kết quả đổi ở khung phải. Không có nút bấm phức tạp nào cả."

### Phần 3 [09:00 - 21:00] - Cùng làm ứng dụng đầu tiên: Máy tính báo giá nhanh

> "Ứng dụng đầu tiên cả lớp làm chung, để ai cũng chắc chắn ra kết quả. Em chọn cái gần với nhiều anh chị nhất: một máy tính báo giá. Nhập hạng mục, số lượng, đơn giá - nó tự tính thành tiền, tự cộng, tự trừ chiết khấu, tự tính VAT, ra tổng thanh toán. Và có nút sao chép để gửi khách qua Zalo."

> "Anh chị copy nguyên khối này, dán vào ô mô tả, nhấn Enter:"

```
Tạo cho tôi một máy tính báo giá nhanh cho khách hàng. Tôi nhập từng hạng mục gồm: tên hạng mục, số lượng, đơn giá - nó tự tính thành tiền từng dòng. Ở dưới hiện: tạm tính, ô nhập % chiết khấu, ô nhập % VAT, và TỔNG THANH TOÁN (số thật to, đơn vị đồng có dấu chấm phân cách). Cho tôi thêm/xóa hạng mục, và một nút sao chép báo giá thành văn bản để gửi khách qua Zalo. Giao diện gọn gàng, chuyên nghiệp, tất cả chữ tiếng Việt.
```

[Chờ Claude dựng xong. Mất khoảng 30 giây tới hơn 1 phút - nói tiếp trong lúc chờ.]

> "Trong lúc chờ, anh chị để ý khung bên phải: Claude đang tự viết mã. Anh chị không cần đọc, không cần hiểu dòng nào cả. Cứ coi như đang xem người ta lắp ráp, mình chỉ nghiệm thu."

> "Xong rồi. Anh chị **dùng thử ngay** đi: nhập một hạng mục bất kỳ, ví dụ 'Máy in laser', số lượng 3, đơn giá 5.000.000. Rồi thêm một dòng nữa. Nhập chiết khấu 5, VAT 10. Nhìn ô TỔNG THANH TOÁN."

[Chờ cả lớp nhập. Gọi 1 anh chị đọc to con số tổng của họ.]

> "Đây là điểm em muốn anh chị dừng lại một giây. Cái vừa hiện ra không phải một đoạn văn mô tả cách tính báo giá. Nó là một cái máy tính báo giá thật, anh chị bấm vào là nó chạy. Mình vừa mô tả bằng tiếng Việt trong 30 giây và có một công cụ dùng được."

**Chỉnh sửa - nói tiếp là nó sửa:**

> "Giờ tới phần hay nhất: mình chỉnh nó bằng tiếng Việt. Anh chị gõ câu này vào **khung chat bên trái** (không phải trong ứng dụng):"

```
Thêm ô nhập tên khách hàng và ngày báo giá ở đầu trang.
```

> "Nó sẽ dựng lại và thêm đúng hai ô đó. Cứ như vậy, thiếu gì nói nấy. Đây là lý do em nói anh chị không cần biết code: cái nút 'sửa' của mình chính là tiếng Việt."

> "Một quy tắc quan trọng em nhắc luôn ở đây: **chỉnh từng bước, mỗi lần một tính năng**. Đừng gõ một câu dài đòi thêm năm thứ cùng lúc - ứng dụng dễ lỗi và mình không biết lỗi ở chỗ nào. Thêm một cái, thử một cái."

### Phần 4 [21:00 - 33:00] - Anh chị tự chọn 1 ứng dụng theo nghề của mình

> "Đến lượt anh chị tự làm. Em có 3 câu lệnh sẵn trong file gửi nhóm. Anh chị **chọn 1 cái gần với công việc của mình nhất**, tạo artifact mới rồi dán vào. Ai xong trước có thể làm thêm cái thứ hai."

**Lựa chọn 1 - Bảng Kanban theo dõi hợp đồng** (hợp với kinh doanh, freelancer, ai chạy nhiều khách cùng lúc):

```
Tôi là freelancer thiết kế đồ họa và đang cùng lúc làm việc với nhiều khách hàng. Vấn đề của tôi là hay quên follow-up khách, dẫn đến mất hợp đồng. Làm cho tôi một bảng Kanban để theo dõi các hợp đồng với các giai đoạn sau: Tiếp cận -> Đã báo giá -> Đang thực hiện -> Chờ thanh toán -> Hoàn thành. Mỗi thẻ dự án cần hiển thị: tên khách hàng; loại dự án; giá trị hợp đồng (đơn vị VNĐ, có dấu chấm phân cách cho dễ đọc); deadline dự kiến; đã bao nhiêu ngày kể từ lần cuối liên hệ - nếu quá 7 ngày thì tô đỏ để nhắc tôi follow-up. Ở đầu trang hiện tổng giá trị tất cả dự án đang hoạt động. Ở dưới có biểu đồ cột doanh thu 3 tháng gần nhất. Tất cả chữ bằng tiếng Việt.
```

Nâng cấp gợi ý: *"thêm nút 'Đã liên hệ hôm nay' cho mỗi thẻ - bấm là reset đồng hồ đếm ngày về 0"*.

**Lựa chọn 2 - Trang trình bày kết quả tháng** (hợp với ai phải báo cáo sếp; nối thẳng buổi 5):

```
Tạo cho tôi một trang trình bày kết quả công việc trong tháng để báo cáo sếp, đẹp và gọn như một trang infographic. Hiển thị: tiêu đề lớn 'Kết quả tháng 7'; 3 con số nổi bật (số thật to): Doanh thu, Số hợp đồng ký mới, Số khách hàng mới; một dòng 'Điểm sáng' và một dòng 'Cần cải thiện'; 3 mục tiêu cho tháng sau (gạch đầu dòng). Cho tôi tự sửa mọi con số và chữ. Giao diện chuyên nghiệp, màu xanh dương chủ đạo, tiếng Việt.
```

Nâng cấp gợi ý: *"thêm biểu đồ cột so sánh doanh thu 3 tháng gần đây và một nút trình chiếu toàn màn hình"*.

**Lựa chọn 3 - Lịch nội dung mạng xã hội** (hợp với marketing, chủ shop, người làm content):

```
Tạo cho tôi một lịch nội dung mạng xã hội để lên kế hoạch bài đăng trong tuần. Mỗi bài gồm: ngày đăng, nền tảng (Facebook / TikTok / Zalo), nội dung/chủ đề, và trạng thái (Ý tưởng / Đang làm / Đã đăng - mỗi trạng thái một màu). Cho tôi thêm, sửa, xóa bài; và lọc theo nền tảng. Ở đầu trang đếm: tổng số bài trong tuần và số bài đã đăng. Giao diện gọn, nhiều màu dễ nhìn, tất cả chữ tiếng Việt.
```

Nâng cấp gợi ý: *"thêm cột ghi chú link hoặc hình cho mỗi bài"*.

[Đi một vòng lớp. Gọi tên 1-2 anh chị, xem màn hình, gỡ vướng.]

> "Anh Tuấn ơi, cái Kanban của anh chưa có khách nào phải không? Anh nhập đại 3 khách giả vào cho nó có dữ liệu đã, rồi mới thấy được chỗ tô đỏ. Còn chị Mai, trang trình bày của chị đang là tháng 7 - chị gõ 'đổi thành tháng 8 và cho tôi tự sửa tiêu đề' là được."

> "Ai đã dùng thử được ứng dụng của mình thì gõ 'xong' vào chat lớp."

### Phần 5 [33:00 - 40:00] - Mang ứng dụng đi dùng thật

> "Ứng dụng đẹp mà nằm trong Claude thì chưa đủ. Em chỉ anh chị ba cách mang nó ra dùng thật."

**Cách 1 - Chia sẻ bằng link (dễ nhất, dùng nhiều nhất):**

> "Ở góc phải trên khung ứng dụng có nút **Chia sẻ / Publish**. Bấm vào, Claude tạo cho anh chị một đường link. Copy link đó gửi Zalo cho đồng nghiệp - người ta mở link là dùng được ngay, không cần tài khoản Claude. Chính anh chị cũng nên mở link đó để dùng toàn màn hình cho thoải mái."

> "Anh chị làm luôn đi, rồi gửi link vào nhóm lớp cho cả lớp xem sản phẩm của nhau."

**Cách 2 - Tải mã về, mở offline:**

> "Trên khung ứng dụng có tab **Code**. Bấm vào, copy toàn bộ mã, dán vào một file trống, lưu lại với đuôi **.html**. Nhấp đúp vào file đó là nó mở bằng trình duyệt và chạy được, không cần mạng, không cần Claude. Cái này hợp khi anh chị muốn giữ một bản trên máy công ty."

**Cách 3 - Mở lại trong Claude:**

> "Artifact tự lưu trong mục Artifacts và trong cuộc trò chuyện đã tạo ra nó. Lúc nào cần dùng hoặc muốn chỉnh thêm, anh chị vào đó mở lại, gõ tiếng Việt để sửa tiếp. Không mất đi đâu cả."

**Ba lưu ý bắt buộc nhắc:**

> "Trước khi qua phần cuối, em nhắc ba điều - anh chị ghi lại giúp em:"

- **Chỉnh từng bước.** Mỗi lần thêm một tính năng thôi. Dồn năm yêu cầu vào một câu là ứng dụng dễ lỗi.
- **Luôn kiểm tra lại số liệu quan trọng.** Cái máy tính báo giá kia tính đúng hay sai, anh chị phải tự cộng lại một lần trước khi gửi khách. AI có thể hiển thị hoặc tính sai. Sai số của mình thì mình chịu, không đổ cho AI được.
- **Cẩn thận thông tin nhạy cảm.** Số tài khoản, danh sách khách hàng, giá vốn - cân nhắc kỹ trước khi nhập vào. Đặc biệt là khi anh chị đã bấm chia sẻ link: link đó ai có cũng mở được.

### Phần 6 [40:00 - 45:00] - Tổng kết và giao bài

> "Mình chốt lại buổi hôm nay. Anh chị vừa làm được một việc mà tuần trước nghe còn xa: tự tạo ra phần mềm dùng được cho công việc của mình, bằng tiếng Việt, trong vài phút, không cài gì và không code."

- **Artifact** khác câu trả lời chat: chat để **đọc**, artifact để **dùng** (bấm, nhập, tự tính, tự tô màu).
- Cách làm luôn là ba bước: **mô tả bằng tiếng Việt -> xem thử -> nói tiếp để chỉnh**.
- Mang đi dùng bằng **link chia sẻ**, hoặc **tải mã về file .html**.

**Bài tập về nhà buổi 6:**
1. Dựng 1 ứng dụng cho đúng việc anh chị đang theo dõi thủ công (cái đã nghĩ trước khi vào lớp). Không dùng câu lệnh mẫu - tự viết mô tả bằng lời của mình.
2. Chỉnh nó thêm **ít nhất 2 lần** bằng tiếng Việt, mỗi lần một tính năng.
3. Bấm chia sẻ, gửi link vào nhóm lớp kèm 1 dòng: ứng dụng này thay cho việc gì mình đang làm tay.
4. Ai muốn thử thêm: tải mã về, lưu thành file .html, mở offline xem có chạy không.

> "Buổi sau mình sang một chuyện khác. Hôm nay anh chị mô tả một lần, được một ứng dụng. Nhưng có những việc anh chị làm đi làm lại hằng tuần - và mỗi lần lại phải dặn Claude y hệt từ đầu: dùng màu này, chèn logo kia, trình bày kiểu nọ. Buổi 7 mình học cách **dặn một lần rồi thôi** - cái đó gọi là **Skill**. Vẫn chưa phải cài gì đâu, anh chị yên tâm. Cảm ơn anh chị, hẹn gặp lại ngày mai."

[Kết thúc buổi. Trợ giảng gửi lại file thư viện 4 câu lệnh vào nhóm lớp; nhắc anh chị đăng link ứng dụng để cả lớp tham khảo chéo.]

---

## C. Checklist chuẩn bị của giảng viên

- [ ] Slide tiêu đề + slide "bảng Excel theo dõi việc và những lần quên follow-up".
- [ ] Claude đăng nhập sẵn, đã mở sẵn mục Artifacts; **đã tự dựng trước cả 4 ứng dụng mẫu** và giữ link để chiếu.
- [ ] Gửi vào nhóm TRƯỚC giờ học: `buoi-06-thu-vien-prompt-artifact.md` (4 câu lệnh đầy đủ).
- [ ] Canh giờ: Claude dựng ứng dụng mất 30 giây tới hơn 1 phút. Chuẩn bị sẵn lời nói lấp khoảng chờ (đã có trong Phần 3).
- [ ] Nhắc trợ giảng trực chat: lỗi hay gặp nhất là học viên gõ yêu cầu sửa **vào trong ứng dụng** thay vì vào khung chat bên trái.
- [ ] Chuẩn bị teaser buổi 7 (Skill) - nhấn mạnh **vẫn chưa phải cài đặt gì**, tránh làm lớp lo.
- [ ] Link ghi hình buổi học.

## D. Tiêu chí hoàn thành buổi 6

- Anh chị nói được artifact khác câu trả lời chat ở chỗ nào (dùng được vs chỉ đọc).
- Anh chị dựng xong máy tính báo giá và **đã nhập thử số liệu ra được tổng thanh toán**.
- Anh chị dựng thêm 1 ứng dụng tự chọn theo nghề và chỉnh được nó ít nhất 1 lần bằng tiếng Việt.
- Anh chị tạo được link chia sẻ và biết đường tải mã về thành file .html.
- Anh chị nhắc lại được 3 lưu ý: chỉnh từng bước, kiểm tra số liệu, cẩn thận thông tin nhạy cảm.
