# Buổi 05 - AI Agent viết báo cáo (kịch bản hands-on)

> **Tuần 1 - Thứ 6** | Thời lượng: 45 phút | Công cụ: Claude Project (claude.ai)
> **Mô tả trên landing page:** "Viết báo cáo tuần từ ghi chú hoặc dữ liệu".
> **Mô hình buổi học:** HANDS-ON. Trình tự: Giới thiệu -> điểm đau -> rồi mới vào thực hành từng bước. Giảng viên và học viên làm SONG SONG.
> **Buổi TỔNG HỢP - cuối Tuần 1:** hôm nay KHÔNG học tính năng mới, mà GHÉP cả 4 tính năng đã học (Instructions + Context + Memory + Scheduled) vào một trợ lý viết báo cáo hoàn chỉnh. Kết thúc buổi, anh chị làm chủ trọn bộ Project (Mức 1). Vẫn không cài đặt gì.
> **Xưng hô:** giảng viên xưng **"em"**, gọi học viên là **"anh chị"**.
> **Định dạng script:** ngoặc vuông `[ ]` là chỉ dẫn thao tác (không đọc to); ngoặc kép `"..."` là lời giảng viên nói gần như nguyên văn; mỗi khối ``` là nội dung copy-dán được.

---

## A. Chuẩn bị trước buổi học

**Giảng viên chuẩn bị:**
- Claude đăng nhập sẵn; một Project có sẵn để demo cả 4 tính năng (Instructions, Context, Memory, Scheduled).
- Gửi TRƯỚC vào nhóm lớp: file agent viết báo cáo (khối "bộ não" ở Phần 2) + FILE số liệu tuần mẫu `tai-lieu-mau-so-lieu-kinh-doanh.pdf` (Phần 3, để anh chị tải về nạp vào Context - giống file hợp đồng buổi 2).
- Nên tự chạy thử trước 1 lần: nạp file PDF số liệu vào Context rồi bảo trợ lý viết báo cáo, xem nó bắt được insight "doanh số tăng nhưng tỷ lệ chốt giảm" và nối "tồn kho thấp -> giao trễ" hay không.
- Slide tiêu đề + slide "bài toán viết báo cáo mất cả buổi chiều" + 1 slide sơ đồ ôn 4 tính năng Project.

**Học viên cần có sẵn (nhắn nhóm trước 1 tiếng):**
- Máy tính, tài khoản Claude (đã có các Project và đã bật Memory từ buổi 3, biết đặt Scheduled từ buổi 4).
- Chuẩn bị sẵn số liệu/ghi chú công việc tuần này của mình (doanh số, tiến độ, đầu việc đã xong/còn treo...), đã ẩn thông tin nhạy cảm.

**Mục tiêu buổi học:**
- Anh chị có 1 trợ lý viết báo cáo: đưa số liệu thô, ra báo cáo 5 phần (Tóm tắt nhanh / Kết quả chính có so sánh / Nổi bật - cần cải thiện / Vấn đề - nguyên nhân / Đề xuất).
- Anh chị GHÉP được cả 4 tính năng vào một trợ lý: Context (nạp FILE số liệu nhiều bảng), Memory (nhớ bối cảnh của mình), Scheduled (tự chạy báo cáo tuần).
- Viết được 1 báo cáo cho công việc thật của mình ngay trong buổi. Mốc: làm chủ Project.

---

## B. Kịch bản hands-on (45 phút)

### Phần 1 [00:00 - 06:00] - Giới thiệu và điểm đau

[Chào lớp, nối buổi 4.]

> "Em chào anh chị, mình đến buổi thứ năm - buổi cuối của Tuần 1. Bốn buổi qua anh chị đã có bốn trợ lý: viết email, tóm tắt tài liệu, ghi biên bản họp, lập kế hoạch. Hôm nay là trợ lý thứ năm - viết báo cáo. Và đặc biệt: buổi này mình sẽ GHÉP cả bốn tính năng đã học vào một trợ lý duy nhất."

[Slide "bài toán viết báo cáo".]

> "Em hỏi thật: đến kỳ báo cáo - báo cáo tuần, báo cáo tháng - anh chị mất bao lâu? [Chờ vài phản hồi.] Nhiều anh chị mất cả buổi chiều: gom số liệu mỗi nơi một ít, rồi ngồi viết, viết xong đọc lại thấy rối, gửi sếp thì sếp hỏi lại 'rốt cuộc tuần này vượt hay không vượt mục tiêu', 'vấn đề gì cần xử lý'."

> "Em kể một tình huống rất đời. Anh Sơn trưởng nhóm, cứ chiều Thứ 6 là mất gần hai tiếng làm báo cáo tuần: mở file doanh số, mở ghi chú họp, cộng trừ so sánh với tuần trước, rồi viết. Tuần nào cũng vậy, lặp đi lặp lại. Mà báo cáo xong sếp vẫn phải hỏi thêm vì nó dài, không nêu bật cái quan trọng."

> "Hôm nay mình giải đúng bài đó: dựng một trợ lý biến số liệu thô thành báo cáo gọn - kết luận đặt trước, số có so sánh, nêu rõ vấn đề và đề xuất. Và vì đây là buổi cuối Tuần 1, mình sẽ cắm vào trợ lý này cả bốn tính năng: bộ não, tài liệu, trí nhớ, và tự chạy. Xong hôm nay, anh chị làm chủ trọn bộ Project. Mình bắt đầu, anh chị mở máy ra nhé."

### Phần 2 [06:00 - 14:00] - Nạp agent viết báo cáo (bộ não)

> "Đầu tiên, giống các buổi trước, mình cho trợ lý một bộ não. Anh chị vào claude.ai, bấm 'Projects', tạo project mới, đặt tên 'Trợ lý Viết báo cáo'. Rồi copy khối em gửi trong nhóm, dán vào ô Instructions, lưu lại. Ai xong gõ '1'."

[Chiếu khối bộ não để đối chiếu - không đọc to hết.]

```
VAI TRÒ
Bạn là trợ lý viết báo cáo công việc cho nhân viên văn phòng Việt Nam. Bạn biến ghi chú, số liệu, đầu việc rời rạc thành báo cáo có cấu trúc rõ ràng, đúng đối tượng đọc, giúp người đọc nắm nhanh và ra quyết định.

NHIỆM VỤ
Từ dữ liệu/ghi chú tôi cung cấp, tạo một báo cáo mạch lạc: kết luận đặt trước, số liệu có so sánh, nêu rõ điểm tốt và điểm cần cải thiện, kèm đề xuất việc tiếp theo - để người đọc hiểu "chuyện gì, tốt xấu ra sao, cần làm gì" mà không phải đọc lại dữ liệu thô.

ĐẦU VÀO (thông tin tôi sẽ cung cấp)
Bắt buộc:
- Dữ liệu/ghi chú/kết quả cần báo cáo.
- Loại báo cáo (tuần/tháng/dự án/tổng kết).
Tùy chọn:
- Người đọc (sếp/khách/nhóm); mục tiêu hoặc KPI; số liệu kỳ trước để so sánh; vấn đề đã gặp; kế hoạch tới; độ dài mong muốn.
Nếu tôi đã nạp tài liệu vào Context (số liệu nguồn, báo cáo kỳ trước, mẫu báo cáo công ty), hãy dùng để bám form và tự so sánh. Nếu thiếu thông tin, hỏi loại báo cáo và người đọc; phần khác suy luận và ghi rõ giả định, tuyệt đối không bịa số.

QUY TRÌNH XỬ LÝ
1. Xác định người đọc và quyết định họ cần ra, từ đó chọn độ chi tiết và giọng.
2. Sắp xếp dữ liệu: kết quả nổi bật trước, giải thích sau; so sánh với kỳ trước hoặc mục tiêu.
3. Tách rõ số liệu (dữ kiện) và nhận định (ý kiến/dự đoán).
4. Chỉ rõ điểm tốt và điểm cần cải thiện, kèm nguyên nhân nếu có.
5. Viết kết luận và đề xuất/việc tiếp theo cụ thể.
6. Trình bày theo ĐỊNH DẠNG ĐẦU RA; tự rà BẢNG KIỂM trước khi giao.

ĐỊNH DẠNG ĐẦU RA
BÁO CÁO <LOẠI> - <kỳ/dự án>
Người gửi: <...> | Người nhận: <...> | Ngày: <...>

1. TÓM TẮT NHANH (3-5 dòng, đọc là hiểu ngay)
- ...
2. KẾT QUẢ CHÍNH (số liệu + so sánh kỳ trước/mục tiêu)
- ...
3. ĐIỂM NỔI BẬT / ĐIỂM CẦN CẢI THIỆN
- ...
4. VẤN ĐỀ & NGUYÊN NHÂN (nếu có)
- ...
5. ĐỀ XUẤT / KẾ HOẠCH TIẾP THEO
- ...

QUY TẮC & AN TOÀN
- Không bịa, không làm đẹp số liệu. Thiếu số nào thì ghi "chưa có dữ liệu", đừng đoán.
- Tách rõ số liệu (dữ kiện) và nhận định (ý kiến/dự đoán) - không trộn lẫn.
- Kết luận đặt trước, dữ liệu chi tiết đặt sau; đúng độ dài và giọng theo người đọc.
- Nhắc tôi bảo mật nếu báo cáo chứa số liệu nội bộ nhạy cảm; chỉ soạn nháp, không tự gửi.

BẢNG KIỂM (tự rà trước khi giao)
- [ ] Có tóm tắt nhanh ở đầu (kết luận trước).
- [ ] Số liệu đúng theo đầu vào, có so sánh kỳ trước/mục tiêu.
- [ ] Phân biệt rõ dữ kiện và nhận định.
- [ ] Có kết luận và đề xuất cụ thể, làm được.
- [ ] Đúng độ dài và giọng theo người đọc.

ĐẦU RA MẪU (tham khảo cách trình bày, không sao chép cứng)
BÁO CÁO TUẦN - Tuần <...>
Người gửi: <tên> | Người nhận: <cấp trên> | Ngày: <...>

1. TÓM TẮT NHANH
- Doanh số vượt mục tiêu và tăng so tuần trước; nhưng tỷ lệ chốt giảm - cần chú ý.
2. KẾT QUẢ CHÍNH
- Doanh số: <số> / mục tiêu <số> (đạt). So tuần trước: tăng <%>.
- Số đơn: <số> (tăng). Tỷ lệ chốt: <%> (giảm so tuần trước).
3. ĐIỂM NỔI BẬT / CẦN CẢI THIỆN
- Nổi bật: vượt mục tiêu doanh số.
- Cần cải thiện: tỷ lệ chốt giảm dù tiếp cận nhiều hơn.
4. VẤN ĐỀ & NGUYÊN NHÂN
- 2 đơn giao trễ do kho thiếu hàng; 1 khách phàn nàn phản hồi chậm.
5. ĐỀ XUẤT / KẾ HOẠCH TIẾP THEO
- Làm việc với kho về tồn hàng; đặt mốc phản hồi khách trong 24h; chạy khuyến mãi giữa tháng.

KHỞI ĐỘNG
Khi đã hiểu, hãy trả lời ngắn gọn rằng bạn đã sẵn sàng và hỏi tôi: (1) loại báo cáo và người đọc, (2) dữ liệu/kết quả của kỳ này. Nếu là lần đầu làm việc cùng tôi, hỏi thêm tôi làm bộ phận gì và các chỉ số chính tôi thường theo dõi, để những lần sau viết cho nhất quán.
```

> "Nạp xong Claude báo sẵn sàng. Điểm khác của hôm nay: bốn buổi trước, mỗi buổi mình cắm THÊM một tính năng. Hôm nay mình có đủ cả bốn rồi, nên buổi này là ráp chúng lại thành một trợ lý báo cáo hoàn chỉnh. Mình ráp lần lượt, bắt đầu từ tài liệu."

### Phần 3 [14:00 - 24:00] - GHÉP Context: nạp FILE số liệu rồi cùng viết báo cáo

> "Giờ vào phần đặc biệt của buổi tổng hợp: mình cắm dần các tính năng đã học vào chính trợ lý này. Đầu tiên là Context - buổi 2 anh chị đã học nạp tài liệu cho trợ lý cầm đọc."

> "Vì sao báo cáo rất cần Context? Số liệu thật của mình đâu phải vài dòng - nó là cả bảng dài: doanh số theo ngày, theo nhân viên, theo sản phẩm, chi phí, tồn kho... Dán hết vào ô chat vừa rối vừa dễ sót. Cách gọn là nạp thẳng cả FILE số liệu vào Context, y như buổi 2 mình nạp file hợp đồng để tóm tắt."

> "Em gửi trong nhóm một file mẫu: `tai-lieu-mau-so-lieu-kinh-doanh.pdf` - bảng tổng hợp số liệu kinh doanh Tuần 28, gồm cả chục bảng. Anh chị tải về, mở Project 'Trợ lý Viết báo cáo', bấm dấu '+' ở khu Context, tải file đó lên. Ai nạp xong gõ '2'."

[Mở nhanh file PDF chiếu cho cả lớp thấy nó gồm những bảng gì: chỉ số tổng hợp, doanh số theo ngày/nhân viên/sản phẩm, chi phí, tồn kho, sự cố...]

> "Nạp xong, anh chị gõ yêu cầu này vào chat - để ý mình KHÔNG gõ lại số nào, chỉ trỏ tới file:"

```
Viết báo cáo tuần giúp tôi, gửi trưởng phòng. Số liệu tuần này nằm trong file tôi vừa nạp ở Context ("Bảng tổng hợp số liệu kinh doanh - Tuần 28"). Hãy đọc file đó và viết báo cáo.
```

[Chờ cả lớp chạy. Đọc chung 1 kết quả.]

> "Anh chị nhìn kết quả. Trợ lý ĐỌC cả file số liệu mấy trang, rồi VIẾT THÀNH BÁO CÁO đủ 5 phần - mình không phải gõ lại con số nào. Em muốn anh chị để ý ba điểm hay:"

> "Một: nó đặt KẾT LUẬN LÊN ĐẦU. Phần Tóm tắt nhanh 3-4 dòng, sếp đọc là hiểu ngay tuần này thế nào, khỏi phải lật hết mấy trang bảng."

> "Hai: nó biết SO SÁNH. Trong file có cột 'Tuần trước (T27)' ngay cạnh 'Tuần này', nên trợ lý tự tính: doanh số 850 triệu vượt mục tiêu 800 và tăng so với 780 tuần trước. Và nó phát hiện một điểm mà đọc bảng thô rất dễ bỏ qua: doanh số tăng nhưng tỷ lệ chốt lại GIẢM từ 25% xuống 22% - tiếp cận nhiều khách hơn mà chốt kém hơn. Nó xếp vào 'cần cải thiện'."

> "Ba: nó NỐI được các bảng rời với nhau. Bảng tồn kho báo mấy mã hàng thiết bị đang dưới định mức; bảng sự cố báo 2 đơn giao trễ do kho thiếu hàng. Trợ lý ghép hai cái đó thành một cảnh báo: tồn kho thấp đang gây trễ đơn. Người đọc lướt bảng khó thấy ngay, mà trợ lý cầm cả file thì thấy. Nó cũng TÁCH rõ số liệu với nhận định và không tự chế thêm con số nào ngoài file."

> "Sức mạnh nữa là hỏi tiếp mà không nạp lại gì. Sếp thích ngắn thì anh chị gõ:"

```
Rút gọn còn nửa trang để gửi sếp, chỉ giữ Tóm tắt và Đề xuất.
```

> "Muốn phần đề xuất cụ thể hơn thì gõ tiếp:"

```
Viết lại phần Đề xuất thành 3 việc cụ thể, mỗi việc kèm người phụ trách và hạn.
```

### Phần 4 [24:00 - 33:00] - GHÉP Memory + thực hành với số liệu thật

**Cắm Memory (tính năng buổi 3):**

> "Trợ lý giờ đã có bộ não (Instructions) và biết đọc tài liệu (Context). Cắm tiếp Memory - trí nhớ bối cảnh, buổi 3 mình đã học. Anh chị gõ cho trợ lý một câu giới thiệu để nó nhớ mình là ai:"

```
Ghi nhớ giúp tôi: tôi là trưởng nhóm Kinh doanh. Các chỉ số chính tôi luôn theo dõi là doanh số, số đơn, tỷ lệ chốt. Sếp tôi thích báo cáo ngắn gọn 1 trang, tập trung vào việc cần quyết. Từ nay viết báo cáo theo đúng bối cảnh này.
```

> "Nhờ Memory đã bật từ buổi 3, trợ lý nhớ điều này qua các cuộc trò chuyện. Tuần sau mở chat mới viết báo cáo, nó tự viết đúng phong cách sếp thích, đúng các chỉ số mình quan tâm, khỏi dặn lại. Báo cáo các tuần vì thế nhất quán một kiểu."

> "Vậy là ba viên gạch đã vào chỗ: Instructions cho nó biết cách viết, Context cho nó số liệu để đọc, Memory cho nó nhớ mình là ai. Giờ tới lượt anh chị làm trên số liệu của chính mình."

**Thực hành với số liệu thật của anh chị:**

> "Anh chị nào có sẵn file số liệu tuần này - bảng Excel xuất ra PDF, hay báo cáo dài - thì nạp thẳng vào Context như file mẫu mình vừa làm, rồi bảo trợ lý đọc file và viết. Ai chỉ có vài dòng thì copy khung này, điền vào chat rồi gửi:"

```
Viết báo cáo [tuần/tháng] giúp tôi, gửi [người đọc].
Số liệu/kết quả kỳ này:
- [...]
- [...]
So với kỳ trước / mục tiêu (nếu có): [...]
Vấn đề gặp phải: [...]
```

> "Anh chị nào chưa có số liệu thật thì dùng lại file mẫu ở Phần 3, thử đổi người đọc thành 'khách hàng' xem trợ lý đổi giọng thế nào."

[Đi một vòng, gọi tên 1-2 anh chị, gỡ vướng.]

> "Anh Hùng ơi, số của anh nhiều mà chưa có mục tiêu để so đúng không? Anh cứ nói 'chưa có mục tiêu, so với tháng trước giúp tôi' là được. Còn chị Lan, nếu báo cáo dài quá, chị gõ 'gói lại trong 1 trang, phần chi tiết để phụ lục'. Ai có báo cáo ưng ý rồi thì gõ 'xong'."

### Phần 5 [33:00 - 40:00] - GHÉP Scheduled + tổng kết trợ lý hoàn chỉnh

**Cắm Scheduled (tính năng buổi 4):**

> "Tính năng cuối cùng cắm nốt vào - Scheduled, buổi 4 mình đã học. Báo cáo tuần là việc lặp lại đều đặn mỗi Thứ 6, quá hợp để tự chạy. Anh chị mở tính năng đặt lịch, tạo tác vụ lặp mỗi Thứ 6 lúc 16 giờ, dán câu này làm nội dung:"

```
Chiều Thứ 6 rồi. Hãy hỏi tôi số liệu công việc tuần này (hoặc file số liệu tôi nạp vào Context), sau đó viết báo cáo tuần theo đúng cấu trúc và bối cảnh bạn đã biết về tôi, tự so sánh với số liệu kỳ trước. Nếu tôi chưa đưa số liệu, nhắc tôi những chỉ số cần cập nhật.
```

> "Đặt xong, cứ chiều Thứ 6 là trợ lý tự nhắc và bắt đầu dựng báo cáo, mình chỉ việc đưa số và duyệt. Ai chưa thấy nút đặt lịch thì như buổi 4 - lưu câu lệnh này lại, chiều Thứ 6 dán vào chạy tay."

**Tổng kết - một trợ lý dùng cả 4 tính năng:**

[Slide sơ đồ 4 tính năng.]

> "Anh chị nhìn lại điều mình vừa làm. Chỉ MỘT Project 'Trợ lý Viết báo cáo' thôi, mà dùng cả bốn tính năng đã học suốt tuần:"

- **Instructions** (buổi 1) - bộ não: biết viết báo cáo 5 phần, kết luận trước.
- **Context** (buổi 2) - tài liệu: nạp cả FILE số liệu nhiều bảng để trợ lý đọc và tự so sánh, khỏi gõ lại số.
- **Memory** (buổi 3) - trí nhớ: nhớ mình là ai, chỉ số nào quan trọng, sếp thích kiểu gì.
- **Scheduled** (buổi 4) - tự chạy: mỗi Thứ 6 tự nhắc và dựng báo cáo.

> "Đây mới là một trợ lý Project HOÀN CHỈNH. Bốn buổi trước mình học từng viên gạch; hôm nay ráp lại thành một ngôi nhà. Và cách ghép này áp dụng được cho MỌI trợ lý - anh chị hoàn toàn có thể cắm Context, Memory, Scheduled vào cả trợ lý email, tóm tắt, biên bản họp của mình."

### Phần 6 [40:00 - 45:00] - Lưu, ôn tập Tuần 1 và giao bài

> "Tin vui: mọi thứ - bộ não, tài liệu trong Context, trí nhớ, lịch tự chạy - đều lưu trong tài khoản Claude của anh chị. Mai mở lại là dùng ngay."

> "Mình cùng nhìn lại Tuần 1. Anh chị đã đi qua một chặng lớn:"

- 5 trợ lý dùng hằng ngày: **viết email, tóm tắt tài liệu, ghi biên bản họp, lập kế hoạch, viết báo cáo**.
- Làm chủ cả **4 tính năng của Project**: Instructions, Context, Memory, Scheduled.
- Đây là **Mức 1 - Trợ lý Project**, nền tảng vững để tuần sau đi tiếp.

**Bài tập về nhà buổi 5 (và tổng kết Tuần 1):**
1. Viết **báo cáo tuần thật** của mình bằng trợ lý, có nạp số liệu và so sánh kỳ trước.
2. **Cắm đủ 4 tính năng** vào ít nhất 1 trợ lý: nạp 1 tài liệu vào Context, giới thiệu bối cảnh cho Memory, đặt 1 lịch Scheduled.
3. Chọn **trợ lý mình dùng nhiều nhất trong 5 cái** và viết 1 dòng: nó giúp mình tiết kiệm khoảng bao nhiêu phút mỗi ngày/tuần.
4. Đăng kết quả vào nhóm lớp.

> "Tuần sau mình bước lên MỨC 2. Trợ lý Project rất tiện nhưng vẫn phải mở đúng project để dùng. Ở Mức 2, mình biến trợ lý thành 'Skill' - nó tự bật khi mình cần, dùng công cụ tên là Claude Code. Có phần cài đặt một chút, nên đầu tuần em sẽ gửi trước video hướng dẫn cài để buổi 6 mình vào việc luôn. Anh chị đã hoàn thành Tuần 1 xuất sắc. Hẹn gặp lại anh chị tuần sau. Cảm ơn anh chị."

[Kết thúc buổi. Trợ giảng gửi lại file agent + FILE số liệu mẫu (PDF) vào nhóm lớp, kèm lời chúc mừng hoàn thành Tuần 1.]

---

## C. Checklist chuẩn bị của giảng viên

- [ ] Slide tiêu đề + slide "bài toán viết báo cáo mất cả buổi chiều" + slide sơ đồ ôn 4 tính năng Project.
- [ ] Claude đăng nhập sẵn; đã thử trước việc ghép cả 4 tính năng trong 1 Project (nạp file PDF vào Context, kiểm Memory, đặt Scheduled).
- [ ] Gửi vào nhóm TRƯỚC giờ học: file agent viết báo cáo (Phần 2) + FILE số liệu tuần mẫu `tai-lieu-mau-so-lieu-kinh-doanh.pdf` (Phần 3, để nạp vào Context).
- [ ] Chuẩn bị lời tổng kết Tuần 1 + giới thiệu ngắn về Tuần 2 (Mức 2 - Claude Code); hẹn gửi trước hướng dẫn cài đặt.
- [ ] Trợ giảng trực chat hỗ trợ khi cả lớp cắm Context/Memory/Scheduled.
- [ ] Link ghi hình buổi học (gửi anh chị ca không dự trực tiếp được).

## D. Tiêu chí hoàn thành buổi 5 (đối chiếu cam kết "đo được hiệu quả")

- Anh chị nạp được bộ não và cho ra báo cáo đủ 5 phần, kết luận đặt trước, số liệu có so sánh.
- Anh chị ghép được Context (nạp FILE số liệu nhiều bảng để trợ lý đọc và tự so sánh) và Memory (nhớ bối cảnh) vào trợ lý báo cáo.
- Anh chị đặt được lịch Scheduled cho báo cáo tuần (hoặc nắm cách chạy tay thay thế).
- Anh chị viết được báo cáo cho công việc thật + nêu được ước lượng thời gian tiết kiệm.
- Mốc Tuần 1: anh chị có 5 trợ lý và làm chủ cả 4 tính năng của Project.
