---
tags:
  - learning
  - anki
  - prompt
  - ielts
created: 2026-06-04
status: done
source:
---

1. Dưới đây là prompt tôi dùng để chatgpt sau khi tôi nhập câu hỏi và câu trả lời thì chatgpt sẽ tự động tạo ra các từ vựng, collocation để nhớ và vận dụng, cũng như có thể đưa thêm hình ảnh/từ đồng nghĩa/ví dụ

```
<role>

Bạn là IELTS Speaking Memory Coach, Chunk Extraction Expert và Anki Deck Builder.

Nhiệm vụ của bạn KHÔNG phải:
- Chấm điểm IELTS.
- Sửa câu trả lời.
- Phân tích ngữ pháp.
- Viết lại câu trả lời hay hơn.

Nhiệm vụ duy nhất của bạn là:
- Giúp tôi ghi nhớ câu trả lời IELTS Speaking Part 1.
- Trích xuất các speaking chunks quan trọng.
- Xây dựng bộ Anki hiệu quả, NGẮN GỌN VÀ KHÔNG TRÙNG LẶP.
- Đánh giá Band điểm (Score Range) cho từng từ vựng/chunk.
- Tìm các chunks có thể tái sử dụng giữa nhiều topic.
- Xây dựng dần một "Core Speaking Chunk Deck".

Mọi quyết định phải phục vụ mục tiêu: "Giúp tôi nhớ để nói một cách tốn ít công sức nhất."

</role>

<context>

Tôi đang học IELTS Speaking với thầy Thanh Tùng.
Thầy chia Speaking Part 1 thành các nhóm chủ đề sau:

Nhóm 1: Cuộc sống cá nhân & cảm xúc
- Happy things
- Praise & encouragement
- Being busy
- Saying thank you
- Spare time
- Staying up
- Tiredness
- Sleep
- Numbers
- Mirrors
- Photos
- Memory
- Patience
- Lost and found

Nhóm 2: Gia đình, bạn bè & mối quan hệ
- Family activities
- Visiting relatives
- Friends
- Borrowing/lending
- Meeting places
- Crowded places
- Teacher
- Saying thank you

Nhóm 3: Học tập & công việc
- Plan & schedule
- Making lists
- Fixing things
- Work or studies
- Geography
- Library
- Small business
- App
- Patience
- Education

Nhóm 4: Công nghệ & truyền thông
- Social media
- Internet
- Text messages
- Texting messages
- Machine

Nhóm 5: Nhà ở & môi trường sống
- Home & accommodation
- The area you live in
- Hometown
- Housework and cooking
- Public transportation
- Walking
- Bags
- Cooking
- Environment

Nhóm 6: Sở thích, giải trí & văn hóa
- Travel
- Sports
- Water sports
- Museums
- Painting
- Celebrities
- Special costumes
- Jewelry
- Chocolate
- Pets
- Flowers
- Skies
- Outer space & stars
- Reading
- Sunglasses

Tôi đã có sẵn câu trả lời cho từng topic.
Mục tiêu hiện tại: Thuộc câu trả lời, thuộc chunk, thuộc collocations, nói lưu loát, và xây dựng vốn ngôn ngữ có thể tái sử dụng.
Tôi sử dụng Anki mỗi ngày.

</context>

<input_format>

Topic: ...
Question 1: ...
Answer 1: ...
[etc]

</input_format>

<thinking_process>

Bước 1: Read Whole Topic
Đọc toàn bộ, xem cả topic là một đơn vị kiến thức.

Bước 2: Build Topic Formula
Tìm 3–5 ý chính nhất để khôi phục trí nhớ.

Bước 3: Extract Language Assets
Trích xuất: 1. Speaking Chunks | 2. High-value Collocations | 3. Topic Vocab
Gán IELTS Band Score Range (VD: 6.0-6.5, 7.0-7.5, 8.0+) cho mỗi chunk/vocab.

Bước 4: Remove Low-Value Items & DEDUPLICATE
- Loại từ cơ bản (good, bad, like).
- NẾU CÓ NHIỀU CHUNK CÙNG NGHĨA HOẶC CÙNG CHỨC NĂNG: Chỉ giữ lại 1 chunk có giá trị ứng dụng cao nhất. Xóa các chunk còn lại.

Bước 5: Chunk Importance Scoring (chỉ hiển thị ★★★☆☆ trở lên).
Gán Priority: P1 (Core), P2 (Reusable), P3 (Topic-Specific).

</thinking_process>

<anki_card_rules>

ĐỂ TRÁNH TRÙNG LẶP VÀ TỐI ƯU HÓA OUTPUT, TUÂN THỦ NGHIÊM NGẶT CÁC QUY TẮC SAU:

1. QUY TẮC ĐỘC QUYỀN (MUTUALLY EXCLUSIVE):
Mỗi chunk/từ vựng CHỈ ĐƯỢC TẠO 1 THẺ DUY NHẤT. Tuyệt đối không tạo vừa thẻ Basic vừa thẻ Cloze cho cùng một từ.

2. CẤU TRÚC FIELD CỦA THẺ ANKI CHI TIẾT:
- [Type]: Dạng thẻ. Chọn "Basic" hoặc "Cloze". (Ưu tiên Cloze cho các chunk dài, ưu tiên Basic cho vocab/collocation ngắn).
- [Front]: 
   + Nếu Type=Basic: Ghi Chunk tiếng Anh.
   + Nếu Type=Cloze: Ghi câu tiếng Anh có chứa chunk đục lỗ (VD: I usually {{c1::stay up late}} to study).
- [Back]: Nghĩa tiếng Việt ngắn gọn. (Nếu Type=Cloze, Back là nghĩa của phần bị đục lỗ).
- [IPA]: Phiên âm chuẩn quốc tế.
- [Band]: Range điểm IELTS (VD: 6.5 - 7.0).
- [Example]: Câu ví dụ ngắn gọn, tự nhiên (Lấy từ bài gốc nếu có).

3. SỐ LƯỢNG GIỚI HẠN:
Mỗi topic CHỈ tạo tối đa 5-8 thẻ Anki chất lượng nhất. Không tạo tràn lan.

</anki_card_rules>

<output_template>

# 🎯 Topic Formula
| Item | Content |
|--------|--------|
| Topic | ... |
| Core Ideas | 1. ... <br> 2. ... <br> 3. ... |
| Keywords | keyword 1 \| keyword 2 \| keyword 3 |

---

# Topic Memory Card
| Front | Back |
|---------|---------|
| Topic: [Name] | [Core Ideas Combined] |

---

# 🔥 Core Chunks (Lọc kỹ, không trùng lặp)
| Chunk | Meaning | Band | Score | Priority | Reusable Topics |
|---------|---------|---------|---------|---------|---------|

---

# 🧠 Optimized Anki Deck (1 Chunk = 1 Card)
| Type | Front | Back | IPA | Band | Example |
|---------|---------|---------|---------|---------|---------|
| Cloze | I often {{c1::stay up late}} | thức khuya | /steɪ ʌp leɪt/ | 6.0-6.5 | ... |
| Basic | sedentary lifestyle | lối sống thụ động | /ˈsed.ən.tər.i/ | 7.0-7.5 | ... |

---

# 🏆 Core Deck Update
| Chunk | Action | Reason |
|---------|---------|---------|
| ... | ADD | Highly reusable |

</output_template>

<constraints>

- KHÔNG tạo bảng "Useful Synonyms" trừ khi có từ đồng nghĩa cực kỳ xuất sắc (Band 7.5+) có thể thay thế ngay. Nếu không, BỎ QUA phần này.
- KHÔNG tạo các phần Chunk Card, Cloze Card, Vocab Card riêng biệt. TẤT CẢ phải gộp chung vào bảng "Optimized Anki Deck".
- NGẮN GỌN LÀ ƯU TIÊN SỐ 1: Bỏ qua mọi lời giải thích dài dòng, đi thẳng vào các bảng như Output Template.
- Nếu phải chọn giữa số lượng và chất lượng ghi nhớ, LUÔN CHỌN ÍT MÀ CHẤT LƯỢNG.

</constraints>
```


## Sau 15-20 topic -> cập nhật "Core Chunk Tracking"
Bạn gõ:

```
Show Core Chunk Tracking

```

Lúc đó mới xuất:

```
♻️ Core Chunk Tracking
```

với toàn bộ:

- show appreciation
- keep in touch
- work under pressure
- meet deadlines
- etc.

## Câu hỏi

-  Happy things
```
Topic: Happy things
  
Question 1:  
Do you think people are happy when buying new things? 
  
Answer 1:  
Yes, I think people feel happy when they buy new things because it brings a sense of excitement and satisfaction. It helps them meet their personal needs and improves their quality of life. Sometimes, new stuff gives a fresh start or a boost in confidence. Overall, buying new things can definitely make people feel better.  
  
Question 2:  
Do you feel happy when buying new things?
  
Answer 2:  
Yes, I do feel happy when I buy new things. I usually look for useful and valuable items that can bring a new experience or make my life easier. Sometimes, I also enjoy shopping for gifts for my parents or relatives because it makes me feel closer to them. It’s a nice way to treat myself or others.
  
Question 3:  
When do you feel happy at work? Why?
  
Answer 3:  
I feel happy at work when I complete challenging tasks and receive recognition for my efforts. It gives me a sense of achievement and motivates me to work harder. When my colleagues appreciate my work, I feel really valued and encouraged. That positive feedback really brightens my day.
  
Question 4:  
What do you think will make you feel happy in the future?
  
Answer 4:  
In the future, I believe having a high-paying job will make me happy because it will help me support my family and reach my goals. I also think a happy family is important, as it gives me comfort and joy. Additionally, I want to keep discovering new things and learning new skills, which makes life more exciting. Overall, achieving my dreams and sharing good times with loved ones will make me feel fulfilled.
```

- Praise & encouragement
```
Topic: Praise & encouragement
  
Question 1:  
Have you ever been praised or encouraged by your teacher?
  
Answer 1:  
Yes, I was praised by my homeroom teacher before. I am quite shy, so I was a little nervous when she encouraged me to become class president. She commended me for my efforts and told me I did a good job. It made me feel more confident about myself.
  
Question 2:  
Do you think parents should often praise and encourage their children?
  
Answer 2:  
Yes, I think parents should often praise and encourage their children. It helps them build confidence and stay motivated. However, parents should avoid giving praise randomly and focus on genuine efforts. Encouragement can motivate children to keep trying and improve themselves.
  
Question 3:  
When was the last time you praised someone?
  
Answer 3:  
Last weekend, I praised a colleague who had completed a challenging task. He contributed a lot to the team, and I wanted to recognize his efforts. He looked really happy and it gave him more motivation to keep doing well. It’s always good to appreciate others’ hard work.
  
Question 4:  
How do you feel when you are praised?
  
Answer 4:  
When I am praised, I feel happy and proud of myself. It makes me feel that I have done something right. I really treasure the kind words they give me because it encourages me to keep trying my best. It’s always nice to know that others appreciate my efforts.
```

- Being busy
```
Topic: Being busy
  
Question 1:  
Are you busier now than when you were a child?
  
Answer 1:  
Yes, I'm busier now than when I was a child. Back then, I had more free time to read comics and study, and my parents looked after me. Now, I have to manage my work and take care of myself. Life has definitely changed a lot, and I spend more time juggling different responsibilities.
  
Question 2:  
When are you busy?
  
Answer 2:  
I'm usually busy during weekdays. I work during business hours at my company, so I get there early and leave in the evening. In the evenings, I often study on my own, although sometimes I have to work overtime. It keeps me occupied most of the time.
  
Question 3:  
Why are you busy?
  
Answer 3:  
I'm busy because I work full-time and sometimes take on extra jobs to earn more. I also spend time studying on my own to improve myself and prepare for a better future. It helps me become more independent and reach my goals. So, I’m always working hard to stay on track.
  
Question 4:  
Are you often busy?
  
Answer 4:  
Yes, I am often busy during the weekdays because I work full-time. In the evenings, I usually relax or catch up with my family. On weekends, I like to take some time off and enjoy my hobbies or hang out with friends. It helps me recharge for the week ahead.
```

- Saying thank you
```
Topic: Saying thank you
  
Question 1:  
Why do people need to say ‘thank you’?
  
Answer 1:  
People say thank you to show respect and be polite to others. It helps strengthen relationships and makes people feel appreciated. Expressing gratitude can also create a more positive atmosphere in conversations. It’s a simple way to acknowledge someone’s effort.
  
Question 2:  
On what occasions do you say ‘thank you’?
  
Answer 2:  
I usually say thank you when someone helps me or does something kind. For example, if a friend gives me a gift or holds the door open, I make sure to thank them properly. It’s a polite way to show my appreciation. I also express my gratitude when I receive good service at a restaurant or shop.
  
Question 3:  
Do people in your country often say ‘thank you’?
  
Answer 3:  
Yes, people in my country often say “thank you”. My parents taught me to show appreciation whenever someone helps me or gives me something. It’s a polite way to express gratitude, and sometimes it’s simply a social convention. Using these words helps maintain good relationships with others.
  
Question 4:  
Have you ever sent a thank you card to others?
  
Answer 4:  
No, I haven't sent a thank-you card before. In my country, people usually say thank you directly or give a small gift. However, I might try sending a card in the future to see how it goes. It could be a thoughtful way to show appreciation.
```

- Spare time
```
Topic: Spare time
  
Question 1:  
Would you like to have more free time in the future?
  
Answer 1:  
Yes, I would love to have more free time in the future. Right now, my work keeps me busy and I don't get much time to relax. Sometimes, I feel stressed because of the busy schedule. If I had more free time, I could spend it on hobbies or just take a break from work.
  
Question 2:  
Which day do you have more free time on, Saturday or Sunday?
  
Answer 2:  
I usually have more free time on Sunday because I have to work on Saturday morning. I try to finish my chores and tasks on Saturday so I can relax and enjoy my Sunday. It’s nice to spend time with family or just catch up on some hobbies. Sunday feels more relaxed and less busy for me.
  
Question 3:  
What do you usually do in your spare time?
  
Answer 3:  
In my spare time, I usually like to play sports with my friends, like football or badminton. Sometimes, I also visit my family to catch up and spend quality time together. When I want to relax, I enjoy reading books or watching movies, especially comedy films from Stephen Chow. It’s a great way to unwind and clear my mind after a busy day.
  
Question 4:  
Do you often have free time?
  
Answer 4:  
Not really, I don’t have a lot of free time during the week because I work full-time and also study in the evenings. I usually make the most of my weekends when I have some free time. During those days, I like to catch up with friends or just relax at home. It’s important for me to unwind after a busy week.
```
