# Hướng dẫn giảng viên - Khóa "30 Ngày Làm Chủ AI Agent"

Tài liệu này giúp mọi giảng viên dạy khóa một cách nhất quán: cùng triết lý, cùng khung buổi, cùng quy ước. Đọc hết một lần trước khi đứng lớp buổi đầu.

---

## 1. Triết lý dạy: HANDS-ON, làm cùng nhau

- **Không giảng lý thuyết suông.** Giảng viên và học viên làm SONG SONG từng bước: giảng viên hướng dẫn 1 thao tác, cả lớp làm ngay trên máy mình, xong mới qua bước sau.
- **KHÔNG phải "giảng viên làm mẫu hết rồi học viên thực hành sau".** Mỗi bước làm chung.
- **Tư duy xuyên suốt:** giao việc cho AI có cấu trúc theo công thức **đầu vào - đầu ra - cách kiểm tra**. Đây là thứ học viên mang theo suốt 30 ngày, dù ở mức công cụ nào.
- **Mỗi buổi ra 1 sản phẩm dùng được:** kết thúc buổi, học viên có 1 agent chạy được + 1 kết quả thật (email, biên bản, báo cáo...).

---

## 2. Khung 45 phút (mọi buổi dùng chung)

| Phút | Nội dung |
|---|---|
| 0 - 8 | Giới thiệu + điểm đau (câu chuyện thực tế, nêu vấn đề văn phòng) |
| 8 - 15 | Nạp / dựng agent của buổi (theo mức tương ứng) |
| 15 - 23 | Cùng chạy thử 1 tình huống chung để thấy kết quả |
| 23 - 35 | Học viên thực hành với việc thật của mình |
| 35 - 41 | Tinh chỉnh + kiểm tra + lỗi thường gặp |
| 41 - 45 | Lưu agent + giao bài về nhà |

**Buổi "đổi mức/công cụ" dành thêm thời gian cho phần công cụ mới, rút gọn phần thực hành:** Buổi 1 (vào Project), Buổi 6 (cài Claude Code), Buổi 11 (vào subagent), Buổi 17 (ghép đội).

---

## 3. Ba mức nâng cấp dần

| Mức | Công cụ | Tuần / Buổi | Ghi chú |
|---|---|---|---|
| **Mức 1** | Trợ lý **Project** (claude.ai) | Tuần 1 . B1-5 | Không cài đặt. Tuần 1 học đủ 4 tính năng: Instructions, Context, Memory, Scheduled. |
| **Mức 2** | Trợ lý tự bật - **Skill** (Claude Code) | Tuần 2 . B6-10 | Buổi 6 dành thời gian onboarding Claude Code. Giữ "lối thoát" Project cho ai chưa cài. |
| **Mức 3** | Đội trợ lý - **Agent team** | Tuần 3-4 . B11-20 | Tuần 3 xây từng subagent (mỗi con 1 vai); Tuần 4 ghép thành đội phối hợp + Workspace. |

Bản đồ đầy đủ: `00-tong-quan/lo-trinh-20-buoi.html`. Bảng so sánh 3 mức: `00-tong-quan/3-muc-agent-project-skill-subagent.md`.

---

## 4. Quy ước bắt buộc (giữ nhất quán giữa các giảng viên)

- **Xưng hô:** giảng viên xưng **"em"**, gọi học viên là **"anh chị"** (không dùng "cả nhà", "các bạn").
- **Prompt đặt inline tại từng bước** trong kịch bản - tới bước nào đưa prompt bước đó, không dồn một cục.
- **Nói thẳng ở Phần 1 các buổi Mức 1:** công cụ hôm nay là Claude Project = một trợ lý cấu hình sẵn, đủ cho việc văn phòng; đây là bước khởi động, "agent" đúng chuẩn kỹ thuật (subagent, agent team) sẽ nâng ở các buổi sau. Đừng để học viên hiểu lầm Project là agent đầy đủ.
- **Đối tượng chính là dân văn phòng** (kế toán, HR, hành chính). Ưu tiên ngôn ngữ đời thường, ví von (người phụ việc, cả nhóm) thay cho thuật ngữ kỹ thuật.
- **Dấu câu ASCII** trong mọi tài liệu (dùng `-` không dùng gạch dài, `->` không dùng mũi tên), nhưng **giữ đầy đủ dấu tiếng Việt**.
- **Bảo mật dữ liệu:** luôn nhắc học viên dùng dữ liệu mẫu / đã ẩn thông tin nhạy cảm; AI hỗ trợ, người dùng chịu trách nhiệm cuối, không để agent tự gửi thay.

---

## 5. Chuẩn bị trước mỗi buổi (checklist chung)

- [ ] Đọc kỹ file kịch bản buổi trong `giao-an/tuan-X/`.
- [ ] Tài khoản Claude đăng nhập sẵn; kiểm tra tính năng buổi đó cần (Projects / Context / Scheduled / Claude Code).
- [ ] Gửi TRƯỚC vào nhóm lớp: file agent/prompt của buổi (trong `tai-nguyen-hoc-vien/tuan-X/`) để học viên copy nhanh.
- [ ] Slide tiêu đề + slide bài toán thực tế của buổi.
- [ ] Từ Tuần 2: gửi trước video/tài liệu cài Claude Code, bố trí trợ giảng hỗ trợ 1-1.

---

## 6. Cấu trúc thư mục (điều hướng nhanh)

```
bo-ai-agent-van-phong-30-ngay/
├── README.md                       Cổng vào + mục lục
├── HUONG-DAN-GIANG-VIEN.md         File này
├── 00-tong-quan/                   Bức tranh lớn (lộ trình HTML, tổng quan, 3 mức, cài Claude Code)
├── giao-an/                        KỊCH BẢN GIẢNG theo tuần (tuan-1-project ... tuan-4-agent-team)
├── tai-nguyen-hoc-vien/            FILE PHÁT CHO HỌC VIÊN theo tuần
└── thu-vien-agent-tham-chieu/      Bản đặc tả đầy đủ 12 AGENT.md + SKILL.md + _TEMPLATE
```

**Quy ước đặt tên file:** kebab-case, mô tả rõ. Kịch bản buổi: `buoi-XX-<ten-agent>.md`. File cho học viên: `agent-<ten>.md` (Project) hoặc `SKILL.md` (Skill) hoặc `.claude/agents/<ten>.md` (subagent).

---

*© CES Global - Bộ tài liệu chương trình "30 Ngày Làm Chủ AI Agent".*
