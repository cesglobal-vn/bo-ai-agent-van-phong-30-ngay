# Ba mức trợ lý AI: Project - Skill - Subagent

Tài liệu giải thích 3 mức "agent" mà khóa đi qua. Dùng cho giảng viên nắm, và có thể gửi học viên đọc thêm. Viết bằng ngôn ngữ đời thường, không cần biết lập trình.

> **Điểm cần hiểu đúng:** claude.ai **Project** thực ra Anthropic gọi là "Project", KHÔNG phải "agent". Đúng nghĩa "agent/subagent" là bản Claude Code. Gọi Project là "AI Agent" là nghĩa rộng/marketing - chấp nhận được cho việc nhẹ, vì một Project cấu hình sẵn cũng đã là một trợ lý. Khóa dùng Project làm bước khởi động (bộ đệm), rồi nâng dần lên agent đúng nghĩa.

---

## Ví von cho dễ nhớ

- **Mức 1 - Trợ lý riêng:** như thuê MỘT người phụ việc quen tay. Mình giao rõ việc, họ làm gọn.
- **Mức 2 - Trợ lý tự bật:** người phụ việc đó TỰ BIẾT việc - gặp đúng loại là tự ra tay, không cần nhắc.
- **Mức 3 - Đội trợ lý:** cả một NHÓM, mỗi người lo một khâu, phối hợp chạy trọn một quy trình.

---

## Bảng so sánh đầy đủ

| Tiêu chí | Mức 1 - Trợ lý Project | Mức 2 - Trợ lý tự bật (Skill) | Mức 3 - Đội trợ lý (Agent team) |
|---|---|---|---|
| Tên chính thức | Project (không gọi là agent) | Skill | Subagent / Agent (đúng nghĩa) |
| Chạy ở đâu, cài gì | Web/app claude.ai, KHÔNG cài gì | Cần cài Claude Code trên máy | Cũng cài Claude Code |
| Mình phải làm gì để có | Tạo 1 Project, dán bộ hướng dẫn | Bỏ "kỹ năng" vào máy, AI tự bật theo từ khóa | Dựng nhiều trợ lý con + cách phối hợp |
| Làm 1 việc hay cả đội | 1 trợ lý lo 1 việc | 1 kỹ năng, tự kích hoạt | Nhiều trợ lý con phối hợp trọn quy trình |
| Tự nhớ + tự làm nhiều bước | Nhớ trong Project; có thêm chạy định kỳ (Scheduled) | Theo kỹ năng đã cài | Mạnh nhất: mỗi con có bộ nhớ riêng, tự dùng công cụ, bàn giao con kế |
| Độ khó cho dân văn phòng | Rất dễ | Trung bình | Cao hơn |
| Ví dụ trong khóa | Buổi 1-5 (trợ lý email, tóm tắt...) | Buổi 6-10 (Skill làm sạch dữ liệu, SOP...) | Buổi 11-20 (đội thu thập -> phân tích -> báo cáo -> slide) |

Còn 1 mức thứ 4 - **Managed Agents / Agent SDK** (qua API, cho lập trình viên) - ngoài phạm vi khóa văn phòng này.

---

## Bốn tính năng của Claude Project (Mức 1 học trong Tuần 1)

Một Project trên claude.ai có 4 phần, khóa dạy trọn trong Tuần 1:

1. **Instructions** - "bộ não": bộ hướng dẫn nói cho Claude biết vai trò, cách làm (Buổi 1).
2. **Context** - nạp tài liệu (PDF, văn bản) để agent tham chiếu đúng nội dung công ty (Buổi 2).
3. **Memory** - Project nhớ bối cảnh (vai trò, dự án, phong cách) qua nhiều phiên (Buổi 3).
4. **Scheduled** - đặt tác vụ định kỳ, agent tự chạy theo lịch - chạm "tự động hóa" ngay ở Mức 1 (Buổi 4).

---

## Vì sao đi theo thứ tự Project -> Skill -> Subagent

Cùng một tư duy "giao việc có cấu trúc" (đầu vào - đầu ra - cách kiểm tra), chỉ khác công cụ. Học Mức 1 để ai cũng theo được và thắng nhanh; khi đã quen tư duy, lên Mức 2 - 3 rất nhẹ vì chỉ đổi cách hiện thực. Cuối khóa (Tuần 4) ghép mọi thứ thành "AI Agent Workspace cá nhân" - đúng nghĩa AI Agent nhất.

*© CES Global - Bộ tài liệu chương trình "30 Ngày Làm Chủ AI Agent".*
