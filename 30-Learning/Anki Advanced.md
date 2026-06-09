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

> ⚠️ **Lưu ý quan trọng:** Hãy thống nhất đặt tên Field bằng **chữ thường** và dùng **dấu gạch dưới** `_` thay cho khoảng trắng (ví dụ: `audio_word` thay vì `Audio Word` hay `AudioWord`). Sự kỷ luật này (quy tắc snake_case) cực kỳ quan trọng để giúp AI viết code chính xác 100% và tránh lỗi không nhận diện được Field khi chạy code.

