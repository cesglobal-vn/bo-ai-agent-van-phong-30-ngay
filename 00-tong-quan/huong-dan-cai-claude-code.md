# Hướng dẫn cài đặt & sử dụng Bộ AI Agent Văn Phòng với Claude Code

**Chương trình:** 30 Ngày Làm Chủ AI Agent Tự Động Hóa Công Việc Văn Phòng
**Đơn vị:** CES Global — Tư vấn, Đào tạo & Xây dựng giải pháp chuyển đổi AI cho doanh nghiệp Việt Nam
**Website:** cesglobal.com.vn · **Email:** dichvukhachhang@cesglobal.com.vn · **Hotline/Zalo:** 0812996256 / 0941086923

> Tài liệu này dành cho **học viên**. Đọc từ trên xuống là cài được và dùng được bộ AI Agent văn phòng ngay trong **Claude Code**.

---

## 1. Vì sao có bộ này? (định vị chương trình)

Bạn đã nghe nhiều về AI nhưng bị quá tải — không biết bắt đầu từ đâu, học xong để đó. Bộ này giải quyết đúng điều đó:

- **Đừng chỉ HỎI AI — hãy GIAO VIỆC cho AI Agent.** Hỏi AI rời rạc cho kết quả hên xui. AI Agent có quy trình (đầu vào rõ → xử lý rõ → đầu ra rõ → kiểm tra rõ) cho kết quả **dùng lại được mỗi ngày**.
- **Mỗi tối 45 phút, mỗi ngày làm chủ 1 AI Agent.** Nhẹ, đều, làm được ngay — không lý thuyết lan man.
- **Sau 30 ngày bạn có bộ 10+ AI Agent cá nhân** ghép thành một *Workspace* làm việc thật, không phải mớ công cụ rời rạc.
- **AI Agent cho từng vị trí:** nhân viên văn phòng, kế toán, HR, sale/CSKH, quản lý phòng ban — mỗi người dùng theo đúng việc thật của mình. Mọi agent tự thích ứng theo ngành nghề của bạn (xem Mục 8).

CES Global định vị **đào tạo thực chiến**: học xong có sản phẩm dùng được, không phải "học cho biết".

---

## 2. Bộ này gồm gì?

| Thành phần | Nội dung |
|---|---|
| **20 Skill theo ngày** (dùng cho khóa học) | `Lo-trinh-30-ngay/Tuan-Y/Ngay-XX-.../` — mỗi ngày 1 thư mục có `AGENT.md` + `BAI-HOC.md` + `SKILL.md`. **Đây là bộ skill khóa 30 ngày cài vào Claude Code** (mỗi buổi 1 skill). Xem **Mục 4**. |
| **12 AI Agent nền** (bản đặc tả đầy đủ) | Thư mục `01`…`12`, mỗi agent gồm `AGENT.md` (đặc tả 12 mục) + `SKILL.md`. Là bản chuẩn đầy đủ của 12 agent nền; nhiều skill theo ngày ở Tuần 2–4 là biến thể chuyên sâu của các agent nền này. Chi tiết ở **Mục 7**. |
| **Lộ trình 30 ngày** | `Lo-trinh-30-ngay/` — 4 tuần × 5 buổi = 20 buổi, mỗi buổi 1 file `BAI-HOC.md` học/dùng ngay. Bảng ở **Mục 6**. |
| **Cơ chế điều phối Sub-Agent** | `_CO-CHE-DIEU-PHOI-SUB-AGENT.md` — giúp mọi agent bám đúng ngành nghề của bạn (**Mục 8**). |
| **Mẫu tạo agent mới** | `_TEMPLATE/` — khung rỗng để bạn tự tạo thêm agent. |

**Mỗi AI Agent có 2 file:**
- **`AGENT.md`** — bản đặc tả đầy đủ (vai trò, mục tiêu, đầu vào, quy trình, đầu ra, bảng kiểm, giới hạn, ví dụ). Dùng để **hiểu agent** hoặc dán làm chỉ dẫn hệ thống.
- **`SKILL.md`** — bản đóng gói chuẩn Skill của Claude (có YAML `name` + `description` kèm từ khóa kích hoạt). Dùng để **cài vào Claude Code**.

> **Lưu ý tên:** trường `name:` bên trong mỗi `SKILL.md` (ví dụ `agent-lam-sach-du-lieu`) là *tên skill* — KHÔNG phải tên thư mục. Thư mục để chép là thư mục chứa file `SKILL.md` (ví dụ `Ngay-06-lam-sach-du-lieu` hoặc `06-xu-ly-bang-tinh`).

---

## 3. Claude Code là gì & cần chuẩn bị gì?

**Claude Code** là công cụ dòng lệnh (chạy trong Terminal) để làm việc với Claude ngay trên máy bạn — đọc/ghi file, tự động hóa công việc. Nó hỗ trợ **Skills**: các "kỹ năng" đóng gói sẵn mà Claude tự kích hoạt khi bạn nói đúng từ khóa. Bộ AI Agent này chính là các Skill như vậy — khóa 30 ngày dùng **20 skill theo ngày** (`Ngay-01…20`).

**Chuẩn bị (làm 1 lần):**

1. **Cài Node.js** (bản 18 trở lên) — tải ở nodejs.org, cài như phần mềm thường.
2. **Cài Claude Code:** mở Terminal (Windows: PowerShell; Mac: Terminal) gõ:
```
npm install -g @anthropic-ai/claude-code
```
3. **Đăng nhập:** gõ `claude` rồi làm theo hướng dẫn đăng nhập tài khoản Claude (Anthropic) của bạn.
4. Kiểm tra: gõ `claude --version` thấy hiện số phiên bản là xong.

> Chưa có tài khoản Claude? Đăng ký ở claude.ai. Học viên CES được hướng dẫn kỹ ở buổi đầu.

---

## 4. Cài Bộ AI Agent vào Claude Code (làm theo từng bước)

Claude Code đọc Skill từ 2 nơi:
- **Toàn máy (mọi dự án):** thư mục `~/.claude/skills/` (Windows: `C:\Users\<tên-bạn>\.claude\skills\`).
- **Riêng 1 dự án:** thư mục `.claude/skills/` nằm trong thư mục dự án đó.

Khuyến nghị học viên cài **toàn máy** để dùng ở mọi nơi.

### Bước 1 — Tải bộ agent về máy

**Cách A (dễ nhất): tải ZIP**
1. Vào trang GitHub của bộ (link BTC gửi).
2. Bấm nút xanh **Code → Download ZIP**.
3. Giải nén ra một thư mục, ví dụ `Bo-AI-Agent`.

**Cách B: dùng git** (nếu đã cài git)
```
git clone <đường-dẫn-repo>.git
```

### Bước 2 — Chép skill vào thư mục skills

**Cách chuẩn cho khóa 30 ngày (khuyến nghị): cài theo từng buổi.**
Mỗi buổi bạn chỉ cần chép **1 thư mục `Ngay-XX-...`** tương ứng (nằm trong `Lo-trinh-30-ngay/Tuan-Y/`, đã có sẵn `SKILL.md`) vào `~/.claude/skills/`. Ví dụ Buổi 06:

- **Mac/Linux (Terminal):**
```bash
mkdir -p ~/.claude/skills
cp -R "Lo-trinh-30-ngay/Tuan-2-Du-lieu-Bao-cao/Ngay-06-lam-sach-du-lieu" ~/.claude/skills/
```
- **Windows (PowerShell):**
```powershell
New-Item -ItemType Directory -Force "$HOME\.claude\skills"
Copy-Item -Recurse -Force ".\Lo-trinh-30-ngay\Tuan-2-Du-lieu-Bao-cao\Ngay-06-lam-sach-du-lieu" "$HOME\.claude\skills\"
```

**Muốn cài trọn 20 skill theo ngày một lần:**
- **Mac/Linux:**
```bash
mkdir -p ~/.claude/skills
cp -R Lo-trinh-30-ngay/*/Ngay-* ~/.claude/skills/
```
- **Windows (PowerShell):**
```powershell
New-Item -ItemType Directory -Force "$HOME\.claude\skills"
Get-ChildItem .\Lo-trinh-30-ngay -Recurse -Directory -Filter "Ngay-*" | ForEach-Object { Copy-Item $_.FullName "$HOME\.claude\skills\" -Recurse -Force }
```

> **Tùy chọn — cài 12 agent nền đầy đủ:** nếu muốn dùng bản đặc tả 12 mục của 12 agent nền, chép thêm các thư mục số `01…12` vào `~/.claude/skills/` (Mac/Linux: `cp -R 0* 1* ~/.claude/skills/`). Không bắt buộc cho khóa học; 20 skill theo ngày đã đủ để theo trọn lộ trình.
> Hoặc đơn giản: mở File Explorer/Finder, copy các thư mục `Ngay-XX` (hoặc `01…12`) rồi dán vào `~/.claude/skills/`.

### Bước 3 — Kiểm tra đã nhận Skill chưa

1. Mở Terminal ở thư mục bất kỳ, gõ `claude`.
2. Gõ thử một yêu cầu trúng từ khóa, ví dụ: **"viết email xin nghỉ phép 2 ngày"**.
3. Claude Code sẽ tự kích hoạt Skill *Viết thư điện tử* và bắt đầu **hỏi bạn 4–6 câu về ngữ cảnh** trước khi viết. Đó là dấu hiệu cài đúng.

### Bước 4 (tùy chọn) — Dùng AGENT.md làm "sub-agent" hoặc chỉ dẫn dự án

- Muốn một agent chạy như **subagent riêng** trong Claude Code: tạo thư mục `.claude/agents/` trong dự án, tạo file `<ten>.md`, dán nội dung `AGENT.md` vào.
- Muốn Claude luôn nhớ cách làm việc theo bộ này: chép các nguyên tắc chính vào file `CLAUDE.md` ở gốc dự án.
- Không bắt buộc — với học viên, chỉ cần **Bước 1–3** là dùng tốt.

---

## 5. Cách dùng hằng ngày

Mọi agent trong bộ đều chạy **3 giai đoạn** (đây là điểm khác biệt so với "hỏi AI" thông thường):

1. **① Brainstorm ngữ cảnh** — agent hỏi bạn 4–6 câu (ngành nghề, vai trò, mục tiêu, đối tượng, ràng buộc). Câu đầu luôn hỏi *bạn làm ngành gì, vai trò gì*.
2. **② Lập kế hoạch & xác nhận** — agent tóm tắt lại ngữ cảnh + đề xuất cách làm, xin bạn duyệt.
3. **③ Triển khai** — agent làm theo kế hoạch đã chốt rồi tự rà bảng kiểm.

> Nếu bạn đã nêu đủ ngữ cảnh ngay từ đầu, agent bỏ qua bước hỏi và làm luôn.

**Mẹo dùng nhanh:** mở `SKILL.md` của agent, copy phần **"Mẫu câu lệnh khởi động"**, điền vào các chỗ `[ ]` rồi gửi. Luôn **kiểm tra đầu ra trước khi gửi/nộp** — AI hỗ trợ, bạn chịu trách nhiệm cuối.

---

## 6. Lộ trình 30 ngày (20 buổi học)

30 ngày = **4 tuần × 5 buổi (Thứ 2 → Thứ 6)**, mỗi buổi 45 phút làm 1 agent, ra 1 kết quả dùng ngay. Nhịp mỗi buổi: 0–5' nêu bài toán → 5–15' giảng viên làm mẫu → 15–35' bạn thực hành → 35–40' lỗi thường gặp → 40–45' bài tập.

| Tuần | Nhóm năng lực | Ngày | AI Agent trong tuần |
|---|---|---|---|
| **1** | Khởi động bộ AI Agent văn phòng | 01–05 | Viết thư · Tóm tắt tài liệu · Ghi chú họp · Lập kế hoạch · Viết báo cáo |
| **2** | Biến dữ liệu thành báo cáo có nhận định | 06–10 | Làm sạch dữ liệu · Tìm điểm đáng chú ý · Báo cáo chỉ số · Gợi ý biểu đồ · Tóm tắt cho quản lý |
| **3** | Chuẩn hóa giao tiếp, tài liệu & quy trình | 11–15 | Viết quy trình · Thông báo nội bộ · Phản hồi khách hàng · Đề cương trình bày · Kho hỏi đáp |
| **4** | Ghép thành Workspace cá nhân tự động | 16–20 | Thu thập thông tin · Phân loại nội dung · Theo dõi công việc · Báo cáo tuần · Workspace cá nhân |

Mỗi ngày mở file `Lo-trinh-30-ngay/Tuan-X/Ngay-XX-.../BAI-HOC.md` — có đủ mục tiêu, bài toán, AGENT.md rút gọn, SKILL.md, diễn tiến 45 phút, bài tập về nhà, tiêu chí đạt. **Skill cài cho buổi đó chính là thư mục `Ngay-XX-...` này.**

---

## 7. Chi tiết 12 AI Agent

Mỗi agent nằm trong thư mục cùng số. Dưới đây là: **làm gì · khi nào tự kích hoạt (trigger) · đầu vào · đầu ra · mẫu câu lệnh**.

### Tuần 1 — Khởi động (agent 01–05)

**01. Viết thư điện tử** — *Giao tiếp*
- **Làm gì:** Soạn, viết lại, phản hồi email công sở — đúng mục tiêu, giọng văn, quan hệ người nhận, có lời kêu gọi hành động rõ.
- **Trigger:** "viết email", "soạn thư", "viết mail xin nghỉ", "trả lời email này", "email cho sếp/khách hàng", "viết lại email cho lịch sự hơn".
- **Đầu vào:** người nhận + quan hệ; mục đích; bối cảnh/số liệu; giọng văn; hạn chót; ngôn ngữ; tên–chức danh ký.
- **Đầu ra:** email hoàn chỉnh (tiêu đề ≤60 ký tự → chào → câu mở nêu mục đích → thân 1–3 đoạn → CTA + hạn chót → ký).
- **Lệnh mẫu:** `Viết email gửi [người nhận + quan hệ], mục đích [muốn họ làm/hiểu gì]. Bối cảnh: [..]. Giọng: [trang trọng/thân thiện/ngắn gọn]. Hạn chót: [..]. Ký: [họ tên - chức danh].`

**02. Tóm tắt tài liệu** — *Tài liệu*
- **Làm gì:** Đọc tài liệu dài (báo cáo, hợp đồng, công văn, biên bản, PDF, chuỗi email) → tóm tắt có cấu trúc để nắm nội dung trong 1–2 phút.
- **Trigger:** "tóm tắt tài liệu", "tóm tắt file này", "đọc giúp tôi", "rút ý chính", "trong hợp đồng này có gì cần lưu ý", "TL;DR".
- **Đầu vào:** nội dung tài liệu; mục đích đọc; khía cạnh cần soi (rủi ro/số tiền/thời hạn/trách nhiệm); độ dài; đối tượng đọc.
- **Đầu ra:** 4 phần — ① Ý chính · ② Số liệu/mốc · ③ Điểm cần chú ý/rủi ro · ④ Việc cần làm. Giữ nguyên số/ngày/tên, không bịa.
- **Lệnh mẫu:** `Tóm tắt tài liệu sau. Mục đích đọc: [..]. Soi kỹ: [rủi ro/số tiền/thời hạn]. Độ dài: [ngắn/vừa]. --- TÀI LIỆU --- [dán nội dung].`

**03. Ghi chú họp** — *Họp*
- **Làm gì:** Biến nội dung họp lộn xộn (bản chép, ghi chú nhanh, chat) thành biên bản chuẩn: quyết định, đầu việc (ai–làm gì–hạn), thảo luận, việc tồn đọng.
- **Trigger:** "ghi chú họp", "làm biên bản họp", "tóm tắt cuộc họp", "chốt đầu việc sau họp", "minutes of meeting", "ai làm gì sau họp".
- **Đầu vào:** nội dung/ghi chú họp; tên + ngày + thành phần; mục tiêu họp; danh sách người có thể gán việc; deadline chung.
- **Đầu ra:** A. Quyết định · B. Đầu việc (bảng: # | Nội dung | Người | Hạn) · C. Thảo luận · D. Tồn đọng. Thiếu người–việc–hạn → `[cần xác nhận]`.
- **Lệnh mẫu:** `Làm biên bản họp từ nội dung sau. Cuộc họp: [tên] — Ngày: [..] — Dự: [..]. --- NỘI DUNG HỌP --- [dán ghi chú].`

**04. Lập kế hoạch** — *Kế hoạch*
- **Làm gì:** Biến mục tiêu + việc rối thành kế hoạch ngày/tuần/tháng có ưu tiên (Eisenhower), phân bổ thời gian thực tế, cảnh báo quá tải, chốt 1 ưu tiên số 1.
- **Trigger:** "lập kế hoạch", "sắp xếp công việc", "kế hoạch tuần này", "ưu tiên việc gì trước", "tôi đang ngập việc", "plan ngày".
- **Đầu vào:** khung thời gian + mục tiêu; số giờ thực có; danh sách việc + deadline cứng; ràng buộc; tự làm hay giao nhóm.
- **Đầu ra:** 🎯 Mục tiêu + ⭐ Ưu tiên số 1 · bảng việc (# | Việc | Ưu tiên A/B/C | Ước lượng | Hạn) · lịch gợi ý · ⚠️ cảnh báo tải.
- **Lệnh mẫu:** `Lập kế hoạch [ngày/tuần/tháng]. Mục tiêu chính: [..]. Thời gian thật có: [..] giờ. Việc (kèm hạn): - [..] - [..].`

**05. Viết báo cáo** — *Báo cáo*
- **Làm gì:** Biến ghi chú/số liệu/đầu việc rời rạc thành báo cáo có cấu trúc (tuần/tháng/dự án) giúp người đọc ra quyết định.
- **Trigger:** "viết báo cáo", "báo cáo tuần/tháng", "làm report", "tổng kết công việc", "báo cáo gửi sếp/khách", "biến số liệu này thành báo cáo".
- **Đầu vào:** loại báo cáo + người đọc; số liệu/kết quả + mốc so sánh (kỳ trước/KPI); vấn đề gặp; kế hoạch tới; form kèm (nếu có).
- **Đầu ra:** 1. Tóm tắt nhanh · 2. Kết quả chính (số + so sánh) · 3. Nổi bật/cần cải thiện · 4. Vấn đề & nguyên nhân · 5. Đề xuất/kế hoạch tiếp.
- **Lệnh mẫu:** `Viết báo cáo [tuần/tháng/dự án] gửi [người đọc]. Số liệu: [..]. So với kỳ trước/mục tiêu: [..]. Vấn đề: [..]. Kế hoạch tới: [..].`

### Tuần 2 — Dữ liệu & báo cáo (agent 06–07 + biến thể)

**06. Xử lý bảng tính** — *Dữ liệu*
- **Làm gì:** Làm sạch dữ liệu bảng (Excel/Sheets/CSV), phát hiện ô trống/trùng/sai định dạng/ngoại lệ, tính chỉ số, gợi ý công thức, nhận xét "bảng đang nói gì".
- **Trigger:** "xử lý bảng tính", "làm sạch dữ liệu", "bảng này có lỗi gì", "kiểm tra dữ liệu", "gợi ý công thức Excel", "tính tổng/trung bình/top".
- **Đầu vào:** bảng dữ liệu; mục đích (làm sạch/tính/tìm bất thường); ý nghĩa + đơn vị cột; quy tắc hợp lệ; Excel hay Google Sheets.
- **Đầu ra:** ① Kiểm tra chất lượng · ② Đề xuất làm sạch (+ công thức) · ③ Chỉ số chính · ④ Nhận xét ngắn. Không sửa dữ liệu gốc.
- **Lệnh mẫu:** `Xử lý bảng dưới. Mục đích: [làm sạch/tính/tìm bất thường]. Ý nghĩa cột: [A=.., B=..]. Quy tắc hợp lệ: [số tiền > 0]. --- BẢNG --- [dán CSV]`

**07. Phân tích dữ liệu** — *Dữ liệu*
- **Làm gì:** Đọc số liệu → tìm insight → giải thích cho người không chuyên → gợi ý hành động + cách trình bày (loại biểu đồ).
- **Trigger:** "phân tích dữ liệu", "số này nói lên điều gì", "tìm insight", "xu hướng doanh thu", "so sánh các kỳ", "kênh/sản phẩm nào tốt nhất".
- **Đầu vào:** số liệu; câu hỏi cần trả lời; mốc so sánh (kỳ trước/mục tiêu/KPI); người nghe; yếu tố đặc thù (mùa vụ, sự kiện).
- **Đầu ra:** ① Điểm đáng chú ý (mỗi điểm 1 con số) · ② Nhận định (dữ kiện vs giả thuyết) · ③ Khuyến nghị hành động · ④ Gợi ý biểu đồ · ⚠️ Giới hạn dữ liệu.
- **Lệnh mẫu:** `Phân tích dữ liệu sau để trả lời: [câu hỏi]. So sánh với: [kỳ trước/mục tiêu]. Người nghe: [sếp/team]. --- DỮ LIỆU --- [dán bảng]`

> *Tuần 2 (ngày 08–10: Báo cáo chỉ số · Gợi ý biểu đồ · Tóm tắt cho quản lý) là biến thể chuyên sâu của agent 05 và 07 — mỗi ngày có skill riêng ở `Lo-trinh-30-ngay/Tuan-2-Du-lieu-Bao-cao/Ngay-08..10/`.*

### Tuần 3 — Giao tiếp, tài liệu & quy trình (agent 08, 09, 11)

**08. Viết quy trình (SOP)** — *Vận hành*
- **Làm gì:** Chuẩn hóa việc lặp lại thành SOP từng bước: mục đích, phạm vi, vai trò, các bước có đầu vào/đầu ra, điểm kiểm tra, xử lý ngoại lệ, bảng kiểm.
- **Trigger:** "viết quy trình", "chuẩn hóa công việc", "làm SOP", "hướng dẫn từng bước", "checklist công việc", "bàn giao việc", "quy trình onboarding/duyệt chi/xử lý đơn".
- **Đầu vào:** tên công việc; cách làm hiện tại (dù lộn xộn); người thực hiện; công cụ; lỗi hay gặp; mục đích SOP.
- **Đầu ra:** SOP v1.0 — 1. Mục đích · 2. Phạm vi · 3. Vai trò · 4. Các bước (bảng: Bước | Người | Thao tác | Đầu vào | Đầu ra | Kiểm tra) · 5. Xử lý ngoại lệ · 6. Bảng kiểm.
- **Lệnh mẫu:** `Chuẩn hóa thành SOP: [tên công việc]. Cách làm hiện tại: [mô tả dù lộn xộn]. Người thực hiện: [..]. Công cụ: [..]. Lỗi hay gặp: [..].`

**09. Phản hồi khách hàng** — *Giao tiếp*
- **Làm gì:** Viết phản hồi khách/đối tác theo tình huống (hỏi đáp, khiếu nại, từ chối khéo, xin lỗi, giữ chân) — chuyên nghiệp, đồng cảm, có giải pháp + bước tiếp.
- **Trigger:** "trả lời khách", "phản hồi khách hàng", "khách phàn nàn/khiếu nại", "viết reply cho khách", "từ chối khéo", "xin lỗi khách", "khách đòi hoàn tiền".
- **Đầu vào:** tình huống/tin nhắn khách; kết quả mong muốn; mức được phép cam kết (voucher/hoàn tiền/thời hạn); kênh; giọng thương hiệu.
- **Đầu ra:** chào → ghi nhận & đồng cảm → giải thích ngắn → giải pháp/bước tiếp + mốc → cam kết & mời phản hồi → ký.
- **Lệnh mẫu:** `Viết phản hồi khách. Tình huống: [dán tin nhắn]. Kết quả mong muốn: [..]. Được phép cam kết: [voucher/hoàn tiền]. Kênh: [email/Zalo/FB]. Giọng: [ấm áp/trang trọng].`

**11. Đề cương trình bày** — *Trình bày*
- **Làm gì:** Dựng đề cương/dàn ý bài trình bày: thông điệp chính, mạch kể, phân bổ theo slide, mở đầu có hook, kết có CTA.
- **Trigger:** "làm đề cương trình bày", "dàn ý thuyết trình", "outline slide", "chuẩn bị bài present", "pitch cho sếp/khách".
- **Đầu vào:** chủ đề; đối tượng nghe; thời lượng/số slide; mục tiêu (muốn người nghe làm/tin gì); số liệu có sẵn; phong cách.
- **Đầu ra:** thông điệp chính (1 câu) + hành động mong muốn; dàn ý theo slide (Slide | Tiêu đề | Ý chính | Gợi ý nội dung/hình/số); ghi chú trình bày.
- **Lệnh mẫu:** `Làm đề cương trình bày: [chủ đề]. Đối tượng: [..]. Thời lượng: [..] phút. Mục tiêu: [muốn người nghe làm gì]. Số liệu có sẵn: [..].`

> *Tuần 3 (ngày 12: Thông báo nội bộ · ngày 15: Kho hỏi đáp) là biến thể của agent 01 và 02 — mỗi ngày có skill riêng ở `Lo-trinh-30-ngay/Tuan-3-Giao-tiep-Quy-trinh/Ngay-12,15/`.*

### Tuần 4 — Ghép thành Workspace (agent 10, 12)

**10. Theo dõi công việc** — *Quản trị việc*
- **Làm gì:** Tạo & duy trì danh sách việc, nhắc hạn, theo dõi tiến độ (trễ/sắp đến hạn/bị chặn), tổng hợp kết quả cuối tuần cho cá nhân/nhóm.
- **Trigger:** "theo dõi công việc", "danh sách việc cần làm", "to-do list", "cập nhật tiến độ", "việc nào đang trễ", "nhắc việc", "tổng hợp tuần".
- **Đầu vào:** danh sách việc (Việc–Người–Hạn–Ưu tiên–Trạng thái); yêu cầu (nhắc hôm nay/tổng hợp tuần); công cụ đang dùng.
- **Đầu ra:** bảng theo dõi + cảnh báo 🔴 Trễ / 🟡 Sắp đến hạn / ⛔ Bị chặn; mục tổng hợp tuần (✅/🔄/⏳ + nổi bật + cần chú ý).
- **Lệnh mẫu:** `Cập nhật bảng theo dõi công việc. Việc & trạng thái: - [Việc] — [Người] — [Hạn] — [Ưu tiên] — [Trạng thái]. Yêu cầu: [nhắc hôm nay/tổng hợp tuần].`

**12. Workspace cá nhân** — *Hệ thống (Capstone)*
- **Làm gì:** Điều phối trung tâm cho cả 11 agent: chọn đúng agent cho từng việc, ghép chuỗi workflow (đầu ra agent này → đầu vào agent kia), nhắc tái dùng mẫu/SOP, đo hiệu quả tổng thể.
- **Trigger:** "workspace cá nhân", "nên dùng agent nào", "kết nối các agent", "workflow tự động", "hệ thống làm việc AI", "quy trình từ họp đến báo cáo".
- **Đầu vào:** mô tả việc cần xử lý; tính chất (một lần/lặp lại); agent/mẫu/SOP đã có; công cụ; mục tiêu tuần/tháng.
- **Đầu ra:** agent phù hợp (mã + tên + lý do); workflow nối bước; tài sản dùng lại (mẫu/SOP/prompt); nhắc/theo dõi (đưa vào agent 10).
- **Lệnh mẫu:** `Tôi cần xử lý: [mô tả việc]. Giúp tôi chọn agent / dựng workflow nối các agent, chỉ ra mẫu nên tái dùng. Việc [một lần/lặp lại].`

---

## 8. Cơ chế điều phối Sub-Agent theo ngành (vì sao đầu ra "đúng việc của bạn")

Học viên đa ngành (kế toán, sale, marketing, HR, vận hành…) mang lên form/dữ liệu rất khác nhau. Mỗi agent giữ **một nền phương pháp chung** nhưng điều phối **5 vai** để bám đúng ngành của bạn:

🔎 **Researcher bối cảnh** (dựng gói ngành: thuật ngữ · chỉ số · khung · chuẩn mực · rủi ro · câu hỏi điển hình + đọc form bạn gửi) → 🧠 **Chuyên gia phương pháp nền** (giữ chuẩn phương pháp) → 🔗 **Tổng hợp** (nền × ngành × form → phương án, xin xác nhận) → 🛠️ **Thực thi** (bám form/giọng/đơn vị của bạn) → ✅ **Kiểm định** (rà bảng kiểm + chuẩn ngành, nêu giả định, không bịa).

**Công thức:** *Đầu ra đúng = NỀN (phương pháp của agent) × GÓI BỐI CẢNH NGÀNH của bạn × FORM/DỮ LIỆU bạn đưa lên.*

Ví dụ cùng agent *Phân tích dữ liệu*: kế toán nhận nhận định dòng tiền/công nợ; sale nhận pipeline/tỷ lệ chốt; marketing nhận CPL/ROAS. Nếu bạn đưa form của công ty → đầu ra khớp đúng form đó. Chi tiết: `_CO-CHE-DIEU-PHOI-SUB-AGENT.md`.

- **Chế độ A (Claude Code / có công cụ):** agent gọi sub-agent thật, chạy song song.
- **Chế độ B (chat thường):** agent "đổi mũ" tuần tự qua 5 vai trong 1 lượt trả lời. Học viên không cần cài thêm gì.

---

## 9. Bảo mật dữ liệu (đọc kỹ)

- **Không** dán dữ liệu nhạy cảm thật khi chưa được phép — ưu tiên **dữ liệu mẫu / đã ẩn danh**.
- Luôn **kiểm tra đầu ra trước khi gửi/nộp**. AI hỗ trợ, con người chịu trách nhiệm cuối.
- Agent chỉ soạn nháp, **không tự gửi** email/tin nhắn thay bạn.

## 10. Đo hiệu quả (trước / sau)

Không bắt buộc quy ra tiền. Đo 5 điểm: ① thời gian tiết kiệm · ② giảm thao tác lặp · ③ tăng chất lượng · ④ giảm lỗi · ⑤ chuẩn hóa quy trình. Ví dụ: soạn 1 email 12' → 3'.

---

## 11. Hỗ trợ

Học viên gặp khó khi cài đặt hoặc sử dụng, liên hệ CES Global:
- Website: cesglobal.com.vn
- Email: dichvukhachhang@cesglobal.com.vn
- Hotline / Zalo: 0812996256 / 0941086923

*© CES Global — Bộ tài liệu chương trình "30 Ngày Làm Chủ AI Agent". Creative – Effective – Sustainable.*
