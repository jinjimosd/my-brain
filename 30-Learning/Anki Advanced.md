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
| Anki for VSCode       | Cài trên VS Code, đẩy card sang Anki                                           |            |

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
Hãy đóng vai trò là một chuyên gia xử lý dữ liệu cho Anki. Nhiệm vụ của bạn là phân loại và chuyển đổi bảng từ vựng tôi cung cấp dưới đây thành 2 bảng Markdown riêng biệt. Mục đích là để tôi copy dán vào Excel và xuất ra file CSV import vào Anki.
</role>

<rules>
1. TÁCH THÀNH 2 BẢNG:
- BẢNG 1: Dành cho thẻ Basic (Chỉ lấy các dòng có Type là "Basic").
- BẢNG 2: Dành cho thẻ Cloze (Chỉ lấy các dòng có Type là "Cloze").

2. CẤU TRÚC CỘT (RẤT QUAN TRỌNG):
Cả 2 bảng BẮT BUỘC phải có CHÍNH XÁC 9 cột theo đúng thứ tự sau (Không được chứa cột Type nữa):
| ID | Front | Back | IPA | Band | Example | Audio | Note | Tag |

3. XỬ LÝ DỮ LIỆU:
- Cột Audio: Luôn để trống.
- Cột Tag: Giữ nguyên định dạng `topic:ten_topic`.
- Không giải thích dài dòng, chỉ in ra 2 bảng.
</rules>

<example_output>
### 1. File CSV cho thẻ Basic (Note Type: Ielts Minimalist)
| ID | Front | Back | IPA | Band | Example | Audio | Note | Tag |
|---|---|---|---|---|---|---|---|---|
| ST-02 | spend quality time (with) | dành thời gian chất lượng với | /spend ˈkwɒləti taɪm/ | 7.0-7.5 | I enjoy spending quality time with my family. | | | topic:spare_time |

### 2. File CSV cho thẻ Cloze (Note Type: Ielts Cloze Minimalist)
| ID | Front | Back | IPA | Band | Example | Audio | Note | Tag |
|---|---|---|---|---|---|---|---|---|
| ST-01 | If I had more free time, I could {{c1::take a break from work}}. | nghỉ ngơi khỏi công việc | /teɪk ə breɪk frəm wɜːk/ | 6.5-7.0 | Everyone needs to take a break from work sometimes. | | Fixed expression | topic:spare_time |
</example_output>

Dưới đây là bảng dữ liệu của tôi, hãy xử lý nó:
```

## 3.  Quy trình Import CSV siêu nhàn:

1. Copy **Bảng 1** từ ChatGPT -> Dán vào Excel -> Lưu tên là basic.csv.
2. Copy **Bảng 2** từ ChatGPT -> Dán vào Excel -> Lưu tên là cloze.csv.
3. Mở Anki -> Bấm **Import File** (hoặc command + shift + I):
    - Chọn file basic.csv -> Chọn Note Type là **Ielts Minimalist**.
    - Chọn file cloze.csv -> Chọn Note Type là **Ielts Cloze Minimalist**.  
        (Anki sẽ tự động khớp 9 cột trong file CSV vào đúng 9 fields của bạn vì thứ tự đã chuẩn 100%).
	Chú ý: 
	- Field separator: Comma 
	- Note type: chọn đúng type
	- Desk: đúng desk
	- Existing notes: Update
	- Field mapping: tags=tag
- Sau khi import xong nhớ xóa card header thừa đi (chỉ có id trống)
