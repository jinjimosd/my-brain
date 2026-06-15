---
title: Anki Advanced
aliases:
  - Anki Advanced
tags:
  - learning/anki
  - ielts
  - templates
status: done
created: 2026-06-10
source:
  - https://ankivn.com/guides/nang-cao/
---

# Hành trình trở thành Cao thủ Anki 😎

---
## 1. Các plugin cần thiết và cấu hình
| Plugin                | Mục đích                                                                       | Code       |
| --------------------- | ------------------------------------------------------------------------------ | ---------- |
| Anki Preview Reloader | Tự Động Tải Lại Màn Xem Trước Khi Code Sửa Đổi Template Thẻ                    | 571150035  |
| Anki Connect          | Cổng Kết Nối API Thần Thánh Ép Anki Giao Tiếp Với App Ngoài (Yomichan, VSCode) | 2055492159 |
| AnkiWebView Inspector | Móc Khóa Debug F12 Thần Thánh Dành Cho Dev Anki                                | 31746032   |
| Anki Editor           | Cài trên VS Code, chỉnh sửa Anki card templates                                |            |

---

## 2. Thiết lập AI Studio
- AI Studio là công cụ miễn phí từ Google cho phép bạn sử dụng các mô hình AI mạnh mẽ như Gemini để tạo template Anki. Đây là công cụ không thể thiếu trong quy trình tạo template bằng AI.
- Các step
	- Tạo tài khoản Gmail
	- Truy cập AI Studio
	- Bật Auto Save trong Playground (bây giờ là default)
	- Chọn Model Gemini 3.1 Pro Preview (latest)
	- Thiết lập Temperature: Điều chỉnh giá trị về **0.3 - 0.5** (khuyến nghị: 0.4)

---

## 3. Tạo thẻ ANki (Template) bằng AI để học không nhàm chán (như Duolingo, Quizlet ...)

### Chuẩn bị:
- **VS Code (Visual Studio Code):** Trình soạn thảo code giúp bạn nhìn mọi thứ rõ ràng hơn.
- **Anki Editor (Extension):** Tiện ích mở rộng trong VS Code giúp đồng bộ code trực tiếp sang Anki.
- **Google AI Studio (Gemini):** “Kiến trúc sư” sẽ viết code thay cho bạn.

### Kiến trúc Dữ liệu - “Căn Cước Công Dân” Cho Thẻ
- Bạn cần thiết kế “ngôi nhà” (Fields) trước khi sơn tường.
- Một bộ thẻ tiêu chuẩn cần các trường (Fields) sau:
	- **id (Quan trọng nhất):** Đây là mã định danh duy nhất (giống số CCCD). Dù bạn sửa lỗi chính tả, đổi nghĩa, đổi giao diện, cái `id` này giúp Anki hiểu “đây vẫn là thẻ cũ” để cập nhật thay vì tạo thẻ mới trùng lặp.
	- **word:** Từ vựng.
	- **ipa:** Phiên âm.
	- **meaning:** Nghĩa tiếng Việt.
	- **example:** Ví dụ minh họa.
	- **audio_word:** Âm thanh của từ.
	- **note_extra:** Ghi chú thêm/Từ đồng nghĩa.
	- **tag**: Phân loại/nhóm các nội dung

> ⚠️ **Lưu ý quan trọng:** Hãy thống nhất đặt tên Field bằng **chữ thường** và dùng **dấu gạch dưới** `_` thay cho khoảng trắng (ví dụ: `audio_word` thay vì `Audio Word` hay `AudioWord`). Sự kỷ luật này (quy tắc snake_case) cực kỳ quan trọng để giúp AI viết code chính xác 100% và tránh lỗi không nhận diện được Field khi chạy code.

### Quy trình “Order” AI Thiết Kế Giao Diện
### 1. Viết Prompt (Câu lệnh) “Thần thánh”
```
Tôi muốn tạo Anki Note Template cho học tiếng Anh. Các Fields của tôi gồm: id, word, ipa, meaning, example, audio_word, note_extra, tag. Hãy viết cho tôi code Front Template, Back Template và Styling (CSS). Yêu cầu phong cách: Tối giản (Minimalist), bo tròn góc, màu sắc hiện đại (hoặc phong cách Aurora).
```

## 2. Prompt tạo anki card từ table kết quả của chatgpt
```
<role>
Hãy đóng vai trò là một chuyên gia xử lý dữ liệu cho Anki. Nhiệm vụ của bạn là chuyển đổi bảng từ vựng tôi cung cấp dưới đây thành định dạng Markdown chuẩn xác dành cho extension "Anki Editor" trên VS Code.
</role>

<rules>
1. TÊN DECK: 
Bắt đầu bằng `## IELTS_speaking_tunganh_p1` (Hoặc tên deck bạn muốn, giữ nguyên dấu ##).

2. PHÂN LOẠI MODEL (Rất quan trọng):
- Nếu cột Type trong bảng là "Basic" -> Ghi `- model: Ielts Minimalist`
- Nếu cột Type trong bảng là "Cloze" -> Ghi `- model: Ielts Cloze Minimalist`

3. XỬ LÝ TAGS:
Lấy dữ liệu từ cột Tag trong bảng và đưa vào dòng `- tags: ...`

4. CẤU TRÚC CÁC TRƯỜNG (FIELDS):
Mỗi thẻ phải bắt đầu bằng `### [ID của thẻ]` và bao gồm CHÍNH XÁC 9 fields sau (không được tự ý thêm bớt):
- ID: [Dữ liệu cột ID]
- Front: [Dữ liệu cột Front]
- Back: [Dữ liệu cột Back]
- IPA: [Dữ liệu cột IPA]
- Band: [Dữ liệu cột Band]
- Example: [Dữ liệu cột Example]
- Audio: (Luôn để trống)
- Note: [Dữ liệu cột Note]
- Tag: [Dữ liệu cột Tag]

5. ĐỊNH DẠNG ĐẦU RA:
- Chỉ xuất ra DUY NHẤT một block code Markdown (nằm trong dấu ```markdown ... ```).
- Không giải thích gì thêm, không viết văn bản thừa ở ngoài block code để tôi có thể copy nhanh nhất.
</rules>

<example_output>
```markdown
## IELTS Speaking

### ST-01
- model: Ielts Cloze Minimalist
- tags: topic:spare_time
- ID: ST-01
- Front: If I had more free time, I could {{c1::take a break from work}}.
- Back: nghỉ ngơi khỏi công việc
- IPA: /teɪk ə breɪk frəm wɜːk/
- Band: 6.5-7.0
- Example: Everyone needs to take a break from work sometimes.
- Audio: 
- Note: Fixed expression
- Tag: topic:spare_time

### ST-02
- model: Ielts Minimalist
- tags: topic:spare_time
- ID: ST-02
- Front: spend quality time (with)
- Back: dành thời gian chất lượng với
- IPA: /spend ˈkwɒləti taɪm/
- Band: 7.0-7.5
- Example: I enjoy spending quality time with my family.
- Audio: 
- Note: One of the best Family chunks
- Tag: topic:spare_time
```