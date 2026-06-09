---
title: Anki Fundamentals
aliases:
  - Anki Basics
tags:
  - learning/anki
  - learning/fsrs
  - learning/spaced-repetition
  - ielts
status: done
created: 2026-06-04
source:
  - https://ankivn.com/guides/co-ban/
---

# Anki Fundamentals

> [!summary]
> - Anki là công cụ học dựa trên Spaced Repetition hiệu quả nhất hiện nay.
> - FSRS là thuật toán mới, nên dùng thay cho SM-2.
> - Desired Retention nên đặt khoảng 80-90% (tôi dùng 85% cho IELTS).
> - Review trước, học mới sau.
> - Display Order ảnh hưởng trải nghiệm học, không ảnh hưởng FSRS.

---
# 1. Tại sao chọn Anki?

## Thuật toán SRS thực thụ
- Dựa trên Spaced Repetition System (SRS).
- Được chứng minh hiệu quả bởi nghiên cứu về trí nhớ.
- Có thể tùy chỉnh theo khả năng ghi nhớ cá nhân.

## Hỗ trợ nhiều loại thẻ học

### Cloze Deletion
Ví dụ:
```text
Paris là thủ đô của {{c1::Pháp}}
```

- Ghi nhớ trong ngữ cảnh.
- Hiệu quả hơn học thuộc lòng.

### Image Occlusion
- Che một phần hình ảnh để tự kiểm tra.
- Hữu ích cho sơ đồ, biểu đồ, hình minh họa.

## Hệ sinh thái Add-on mạnh

- Nhiều plugin mở rộng.
- Tùy biến rất cao.

## Miễn phí & mã nguồn mở

- Windows, macOS, Linux, Android: miễn phí.
- iOS: trả phí một lần.

---
# 2. Anki vs Quizlet vs Memrise

> [!tip]
> Microsoft Paint vs Adobe Photoshop:
>
> - Quizlet = dễ dùng
> - Memrise = thân thiện với người mới học ngoại ngữ
> - Anki = khó hơn lúc đầu nhưng mạnh hơn rất nhiều

| Công cụ | Phù hợp                 |
| ------- | ----------------------- |
| Anki    | Học dài hạn, chuyên sâu |
| Quizlet | Ôn tập ngắn hạn         |
| Memrise | Người mới học ngôn ngữ  |

**Kết luận:**
- Anki = lựa chọn tốt nhất cho việc học nghiêm túc.

---

# 3. Thuật toán SM-2

SM-2 là thuật toán mặc định của Anki trước khi FSRS xuất hiện.
Nguyên lý:

> Khoảng cách ôn tập mới = Khoảng cách cũ × Ease Factor

## Hạn chế

### 1. Gộp nhiều khái niệm vào Ease Factor
- Độ khó thẻ.
- Tốc độ quên.
=> Không chính xác.

### 2. Không tận dụng toàn bộ lịch sử học
Chỉ tập trung nhiều vào lần review gần nhất.

### 3. Mô hình tăng trưởng chưa thực tế
Khoảng cách ôn tập đôi khi tăng hoặc giảm không hợp lý.

### 4. Easy Hell
- Trả lời sai nhiều lần.
- Ease giảm mạnh.
- Thẻ xuất hiện liên tục.
- Gây mệt mỏi.

---

# 4. FSRS

FSRS (Free Spaced Repetition Scheduler) là thuật toán mới thay thế SM-2.

## Ưu điểm

- Giảm 20-30% số review/ngày.
- Tự học từ dữ liệu của người dùng.
- Cá nhân hóa tốt hơn.
- Cấu hình đơn giản hơn.

## Mô hình DSR

| Thành phần | Ý nghĩa |
|------------|----------|
| D | Difficulty |
| S | Stability |
| R | Retrievability |

---
## FSRS vs SM-2

| Tiêu chí | SM-2 | FSRS |
|-----------|-------|-------|
| Độ chính xác | ⭐⭐⭐ | ⭐⭐⭐⭐⭐ |
| Cá nhân hóa | Thấp | Cao |
| Số review | 100% | Giảm 20-30% |
| Điều khiển retention | Gián tiếp | Trực tiếp |
| Độ phức tạp | Cao | Thấp hơn |

---
## Cấu hình FSRS

### Bật FSRS
```text
Deck Options
→ FSRS
→ Enable
```

### Desired Retention

| Giá trị | Mục đích |
|----------|----------|
| 80-85% | Ít review hơn |
| 85-90% | Cân bằng |
| 90%+ | Nhớ chắc hơn nhưng review nhiều |

Tôi sử dụng:
```text
85%
```

### Learning Steps

Giữ mặc định:
```text
1m 10m
```

### Relearning Steps
Giữ mặc định:

```text
10m
```

---
# 5. Display Order

> [!info]
> Display Order quyết định thứ tự hiển thị thẻ.
>
> Không ảnh hưởng thuật toán FSRS.

## Cấu hình khuyến nghị

| Setting | Giá trị | Lý do |
|----------|----------|----------|
| New Card Gather Order | Deck (default) | Học theo cấu trúc deck |
| New Card Sort Order | Card type, then random | Tránh Linear Guessing |
| New / Review Order | Show after reviews | Ôn cũ trước |
| Interday Order | Show before reviews | Củng cố thẻ mới tốt hơn |
| Review Sort Order | Ascending retrievability | Phù hợp triết lý FSRS |

---

## Cấu hình học cấp tốc (Scramming)

| Setting               | Giá trị             | Mục đích             |
| --------------------- | ------------------- | -------------------- |
| New Card Gather Order | Descending Position | Ưu tiên thẻ mới nhất |
| New / Review Order    | Show Before Reviews | Học mới trước        |
| Review Sort Order     | Ascending Ease      | Học thẻ khó trước    |

> [!warning]
> Chỉ dùng ngắn hạn trước kỳ thi.
>
> Sau khi thi xong nên quay lại cấu hình mặc định.

