# 1. Lý do nên chọn **Anki** để học hiệu quả hơn
### 1. Thuật toán SRS thực thụ và có thể tùy chỉnh
- Anki được xây dựng dựa trên một **thuật toán SRS (Spaced Repetition System)** thực sự, đã được chứng minh hiệu quả khoa học. 
- Điểm đặc biệt là người dùng có thể **tùy chỉnh hàng chục thông số** để phù hợp với loại nội dung và khả năng ghi nhớ cá nhân.
### 2. Hỗ trợ các loại thẻ học nâng cao
- **Cloze Deletion (Điền vào chỗ trống):** cho phép bạn tạo các thẻ như ”… là thủ đô của Pháp.” thay vì “Thủ đô của Pháp là gì?”. Phương pháp này giúp _ghi nhớ thông tin trong ngữ cảnh_.
- **Image Occlusion (Che lấp hình ảnh):** thông qua add-on nổi tiếng, bạn có thể che nhãn trên sơ đồ giải phẫu hoặc biểu đồ kỹ thuật để tự kiểm tra. Đây là công cụ không thể thiếu cho những người học các ngành có tính trực quan cao.
### 3. Hệ sinh thái add-on khổng lồ, tùy biến mạnh mẽ
### 4. Mã nguồn mở và hoàn toàn miễn phí
- Anki là **phần mềm mã nguồn mở và miễn phí** cho Windows, macOS, Linux và Android. 
- Phiên bản iOS chỉ thu phí một lần để hỗ trợ nhà phát triển — không có chi phí hàng tháng.

# 2. So sánh Anki, Quizlet và Memrise
- **Key takeaways:**
	- Anki = công cụ chuyên nghiệp, tối ưu học lâu dài.
	- Quizlet = trải nghiệm thân thiện, học ngắn hạn/ôn kiểm tra.
	- Memrise = hợp người mới bắt đầu học ngôn ngữ với khóa dựng sẵn.

- Hãy hình dung Microsoft Paint (dễ dùng, giới hạn) so với Adobe Photoshop (khó lúc đầu nhưng mạnh mẽ khi nắm vững).

# 3. Thuật toán SM-2 trong Anki
- **SM-2** là thuật toán mặc định của Anki trước khi **FSRS** ra đời vào năm 1980 bởi Piotr Wozniak, tác giả phần mềm SuperMemo.
- Về nguyên lý, SM-2 hoạt động dựa trên công thức đơn giản:
> **Khoảng thời gian mới = Khoảng thời gian cũ × Hệ số dễ (Ease Factor)**

- 4 Hạn chế chính của SM-2
	- Gộp các khái niệm khác nhau: `Độ khó của thẻ` và `tốc độ quên của ký ức` vào cùng 1 biến duy nhất là Easy Factor.
	- Thiếu khả năng ghi nhớ dài hạn: thuật toán chỉ dựa vào kết quả lần ôn gần nhất, bỏ qua toàn bộ lịch sử học trước đó.
	- Mô hình tăng trưởng không thực tế.
	- Hiện tượng "Easy Hell": Khi người dùng trả lời sai nhiều lần, hệ số `easy` giảm mạnh khiến thẻ đó lặp lại thường xuyên hơn - tạo cảm giác mệt mỏi và phản tác dụng trong quá trình học.

# 4. FSRS Anki
- **FSRS (Free Spaced Repetition Scheduler)** là thuật toán học máy thế hệ mới trong Anki, thay thế [SM-2 - thuật toán mặc định](https://ankivn.com/guides/co-ban/11-sm-2-thuat-toan-mac-dinh-tot-nhung-chua-du). FSRS:
	- **Giảm 20-30% số review/ngày** mà vẫn cải thiện retention
	- **Tự học từ bạn** - phân tích cách bạn ghi nhớ và quên
	- **Dễ cấu hình hơn** - chỉ cần điều chỉnh Desired Retention
	- **Tích hợp sẵn** từ Anki 23.10+
- FSRS dựa trên mô hình DSR (Difficulty, Stability, Retrievability) thay vì ease factor cố định của SM-2. Đây là một cuộc cách mạng trong spaced repetition
- So sánh FSRS vs SM-2: Cuộc cách mạng thực sự

| Tiêu chí             | SM-2 (Cũ)                      | FSRS (Mới)                        |
| -------------------- | ------------------------------ | --------------------------------- |
| Mô hình trí nhớ      | Ease factor + interval cố định | Mô hình DSR (D, S, R) dựa trên ML |
| Độ chính xác         | ⭐⭐⭐                            | ⭐⭐⭐⭐⭐ (+15-25% log loss)          |
| Cá nhân hóa          | ❌ Rất hạn chế                  | ✅ Tự học từ bạn                   |
| Số review/ngày       | Baseline (100%)                | ↓ Giảm 20-30%                     |
| Điều khiển retention | Gián tiếp qua settings         | Trực tiếp: Desired Retention      |
| Độ phức tạp config   | Nhiều settings "bẫy"           | Đơn giản hơn rất nhiều            |

- Bật FSRS: 
	- Mở Desk Options (bánh răng cạnh desk) -> cuộn tìm FSRS -> Bật công tắc.
	- 