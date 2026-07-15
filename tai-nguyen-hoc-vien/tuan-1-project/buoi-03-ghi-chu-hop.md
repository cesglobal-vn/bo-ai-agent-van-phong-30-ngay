# Buổi 03 - Trợ lý Ghi chú họp (Memory) - File cho học viên

> **Tuần 1 - Mức 1: Trợ lý Project** | Tính năng trọng tâm: **MEMORY** (trí nhớ bối cảnh).
> Buổi 1 học Instructions (bộ não), buổi 2 học Context (nạp tài liệu); buổi 3 thêm Memory để trợ lý nhớ phòng ban, dự án, đồng nghiệp mà không phải khai lại.

---

## BƯỚC 1 — TẠO PROJECT VÀ NẠP "BỘ NÃO" CHO TRỢ LÝ

Vào claude.ai, đăng nhập (Hoặc dùng claude desktop)

Nhìn cột bên trái, bấm Projects → Create project (tạo project mới).

Đặt tên: Trợ lý Ghi chú họp.

Mở ô Instructions

Copy toàn bộ khối "bộ não" bên dưới, dán vào ô Instructions, rồi Save.

> 📌 Dán nội dung vào ô Instructions
> của Project "Trợ lý Ghi chú họp". Chỉ dán MỘT LẦN duy nhất. Đây KHÔNG phải ô chat.

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

> ✅ Dấu hiệu thành công:
> sau khi Save, quay lại ô chat, Claude sẽ báo đã sẵn sàng và hỏi anh/chị vài thông tin nền. Đừng bỏ qua câu hỏi đó — mình dùng ngay ở Bước 3.

## BƯỚC 2 — BẬT MEMORY (TRÍ NHỚ)

Bấm biểu tượng Settings (bánh răng, thường ở góc trên hoặc menu tài khoản).

Chọn mục Capabilities sau đó bật nút “Generate memory from chat history”

Bật tính năng này lên.

Vì sao cần Memory? Vì mỗi tuần anh/chị họp nhiều, mở nhiều cuộc trò chuyện mới. Nếu không có Memory, lần nào cũng phải khai lại "tôi làm phòng X, dự án Y, nhóm có A B C". Có Memory, trợ lý nhớ sẵn — mở chat mới vẫn gọi đúng tên người, đúng tên dự án mà chúng ta đã từng trao đổi trước đó

## VÍ DỤ 1 — TỪ GHI CHÚ LỘN XỘN RA BIÊN BẢN (HỌP NỘI BỘ)

Đây là ví dụ đầy đủ để anh/chị chạy thử. Làm theo đúng thứ tự.

1.1 — Gửi ghi chú họp thô vào trợ lý

> 📌 Dán vào ô chat
> của Project "Trợ lý Ghi chú họp" (cùng cuộc trò chuyện đã giới thiệu bối cảnh ở Bước 3). Dán NGUYÊN CẢ KHỐI dưới đây — gồm câu lệnh + phần ghi chú thô.

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

1.2 — Đọc kết quả trợ lý trả về

Trợ lý sẽ trả ra biên bản theo nội dung đã yêu cầu

> 👉 Để ý ba điểm hay:
> (1) việc "chốt phương án 2" nằm ở mục Quyết định, còn "ngân sách 20 triệu" chưa chốt nên nằm ở Thảo luận — nó phân biệt đúng; (2) chỗ nào thiếu hạn hoặc thiếu người, nó ghi [cần xác nhận] chứ không bịa; (3) vụ tên miền chưa ai nhận được đẩy xuống Tồn đọng để không bị quên.

1.3 — Chỉnh sửa cho vừa ý (tùy chọn)

Muốn biến phần đầu việc thành tin nhắn gửi nhóm luôn? Gõ tiếp nội dung sau:

```
Chuyển phần Đầu việc thành tin nhắn ngắn để tôi gửi luôn vào nhóm Zalo.
```

Muốn gom các chỗ chưa rõ thành danh sách câu hỏi để đi hỏi lại đồng nghiệp? Gõ nội dung:

```
Chỗ nào [cần xác nhận], liệt kê lại thành danh sách câu hỏi tôi cần hỏi lại đồng nghiệp.
```

## VÍ DỤ 2 — KIỂM CHỨNG MEMORY HOẠT ĐỘNG (MỞ CUỘC TRÒ CHUYỆN MỚI)

Ví dụ này cho thấy điểm đặc biệt của buổi hôm nay: trợ lý nhớ bối cảnh kể cả ở cuộc trò chuyện mới toanh.

2.1 — Mở một cuộc trò chuyện MỚI

Trong cùng Project "Trợ lý Ghi chú họp", bấm New chat (cuộc trò chuyện mới). Đừng dùng lại đoạn chat cũ — mục đích là kiểm tra xem trợ lý có tự nhớ không.

2.2 — Gửi ghi chú, nhưng KHÔNG nhắc lại tên dự án hay tên đồng nghiệp

> 📌 Dán vào ô chat của cuộc trò chuyện MỚI vừa mở. Cố tình KHÔNG khai lại bối cảnh, để thử trí nhớ.

```
Họp nhanh sáng nay xong rồi, ghi biên bản giúp tôi: Long báo cáo tiến độ ổn, banner sắp
xong. Mai xin thêm 2 ngày để hoàn thành phần liên hệ khách. Còn lại chưa có gì mới.
```

2.3 — Đọc kết quả và kiểm tra trí nhớ

> ✅ Bài kiểm tra Memory:
> anh/chị KHÔNG hề nhắc đây là dự án Website, cũng không nói Long/Mai là ai. Nếu biên bản vẫn tự điền đúng tên dự án "Website" và nhận ra Long, Mai — nghĩa là Memory đã hoạt động. Đây chính là khác biệt lớn nhất so với Context ở buổi 2.

> Nếu nó quên hoặc gọi sai: quay lại Settings → Memory kiểm tra đã bật chưa, rồi vào chat gõ lại tin nhắn giới thiệu bối cảnh ở Bước 3 một lần nữa.

## Bước 4 — Thực hành với ghi chú họp THẬT của anh/chị

Giờ tới lượt anh/chị. Lấy một ghi chú họp thật gần đây (hoặc tự chép tay lại một cuộc họp trong tuần).

> ⚠️ Bảo mật: nếu họp có thông tin nhạy cảm (lương, số liệu khách hàng, hợp đồng), che hoặc xóa phần đó TRƯỚC KHI dán vào.

> 📌 Dán vào đâu:
> ô chat của Project "Trợ lý Ghi chú họp" (chat cũ hay mới đều được, vì đã có Memory). Dán câu lệnh + ghi chú thật của anh/chị vào chỗ [...].

```
Ghi biên bản họp giúp tôi từ nội dung dưới đây. Nếu thiếu người phụ trách hoặc hạn chót
ở việc nào, đánh dấu [cần xác nhận] thay vì đoán.
 
[dán ghi chú họp thật của anh/chị vào đây]
```

Chưa có ghi chú thật? Dùng lại một trong hai ví dụ ở trên, thử thêm biến thể: họp với khách hàng, hoặc họp có nhiều việc còn treo chưa chốt.

## 3 lỗi hay gặp tuần này (và cách xử)

Ghi chú viết tắt tên, trợ lý gán nhầm người. → Bổ sung tên đầy đủ, ví dụ gõ thêm: "Tên đầy đủ của 'a.T' là anh Tuấn, trưởng phòng." Hoặc lưu luôn vào Memory ở Bước 3.

Họp nhiều nội dung rời rạc, không rõ cái nào đã chốt. → Nhắc trợ lý: "Phân biệt rõ giúp tôi phần đã chốt và phần còn đang bàn."

Quên kiểm tra bảng Đầu việc trước khi gửi cả nhóm. → Luôn đọc lại cột người phụ trách và hạn chót. Cả nhóm làm việc theo bảng này, nên anh/chị là người chịu trách nhiệm cuối cùng, không phải AI.

## Trợ lý được lưu ở đâu?

Cả bộ não (Instructions) lẫn trí nhớ bối cảnh (Memory) đều tự lưu trong tài khoản Claude của anh/chị. Mai mở lại Project "Trợ lý Ghi chú họp" là dùng ngay, không cần giới thiệu lại từ đầu.

## Bài tập về nhà Buổi 3

Dùng trợ lý ghi 2 biên bản họp thật (họp gần đây, hoặc ghi chú tự chép lại từ một cuộc họp trong tuần).

Với 1 biên bản, mở cuộc trò chuyện mới và kiểm tra xem trợ lý có nhớ đúng tên dự án / đồng nghiệp mà không cần nhắc lại không. Nếu sai, giới thiệu lại bối cảnh cho Memory.

Đối chiếu bảng Đầu việc với thực tế cuộc họp: đủ người - việc - hạn chưa, có chỗ nào bị gán nhầm không.

## Xong buổi 3, anh/chị đã có thể

Tạo Project "Trợ lý Ghi chú họp" và nạp bộ não vào Instructions.

Bật Memory và dạy trợ lý nhớ bối cảnh phòng ban, dự án, đồng nghiệp.

Biến ghi chú họp lộn xộn thành biên bản đủ 4 phần: Quyết định / Đầu việc / Thảo luận / Tồn đọng.

Kiểm chứng Memory hoạt động qua một cuộc trò chuyện mới.
