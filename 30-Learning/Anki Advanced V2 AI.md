---
title: Anki Advanced v2
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
# 🌟 BỘ TÀI LIỆU TẠO ANKI TEMPLATE: IELTS AURORA MINIMALIST (TÍCH HỢP VS CODE)

**Mục tiêu:** Tạo ra một hệ thống thẻ Anki chuyên dụng cho IELTS Speaking, hỗ trợ 2 loại thẻ (Basic gõ chữ và Cloze đục lỗ), giao diện Kính mờ (Glassmorphism) trên nền Cực quang (Aurora), tối ưu hóa để nhập liệu siêu tốc qua VS Code.

---

## PHẦN 1: CẤU HÌNH TRƯỜNG DỮ LIỆU (FIELDS)

Tạo 2 Note Types trên Anki:
1. **Ielts Minimalist** (Clone từ Basic)
2. **Ielts Cloze Minimalist** (Clone từ Cloze)

Cả 2 Note Types này **BẮT BUỘC** phải có chung cấu trúc gồm **9 Fields** theo đúng thứ tự sau:
1. ID (Cài đặt: Sort by this field in the browser)
2. Front
3. Back
4. IPA
5. Band
6. Example
7. Audio
8. Note
9. Tag

---

## PHẦN 2: CODE CHO THẺ BASIC (IELTS MINIMALIST)

Cơ chế: Mặt trước hiện Nghĩa Tiếng Việt -> Người học gõ cụm từ Tiếng Anh vào ô trống -> Mặt sau chấm điểm đúng/sai từng chữ.
**📍 Front Template:**
codeHtml

```
<div class="card-container">
    {{#Band}}
        <div class="band-badge">🎯 {{Band}}</div>
    {{/Band}}

    <div class="meaning-section">
        <div class="label" style="color: #94a3b8; margin-bottom: 10px;">✍️ Gõ cụm từ Tiếng Anh:</div>
        <div class="meaning" style="font-size: 1.8rem;">{{Back}}</div>
    </div>

    <div class="typing-area">
        {{type:Front}}
    </div>

    <div class="footer-section">
        {{#Tag}}
            <div class="tag-pill">🏷️ {{Tag}}</div>
        {{/Tag}}
        {{#ID}}
            <div class="card-id">ID: {{ID}}</div>
        {{/ID}}
    </div>
</div>
```

**📍 Back Template:**

codeHtml

```
<div class="card-container">
    {{#Band}}
        <div class="band-badge">🎯 {{Band}}</div>
    {{/Band}}

    <div class="typing-result">
        {{type:Front}}
    </div>

    <hr class="divider">

    <div class="word-section">
        {{#IPA}}
            <div class="ipa">{{IPA}}</div>
        {{/IPA}}
        {{#Audio}}
            <div class="audio">{{Audio}}</div>
        {{/Audio}}
    </div>

    {{#Example}}
        <div class="info-box example-box">
            <div class="label">✨ Example</div>
            <div class="content">{{Example}}</div>
        </div>
    {{/Example}}

    {{#Note}}
        <div class="info-box note-box">
            <div class="label">💡 Note</div>
            <div class="content">{{Note}}</div>
        </div>
    {{/Note}}

    <div class="footer-section">
        {{#Tag}}
            <div class="tag-pill">🏷️ {{Tag}}</div>
        {{/Tag}}
        {{#ID}}
            <div class="card-id">ID: {{ID}}</div>
        {{/ID}}
    </div>
</div>
```

---

## PHẦN 3: CODE CHO THẺ CLOZE (IELTS CLOZE MINIMALIST)

Cơ chế: Mặt trước hiện câu Tiếng Anh bị đục lỗ kèm gợi ý Tiếng Việt -> Người học tự nhẩm đáp án -> Mặt sau hiện câu hoàn chỉnh.

**📍 Front Template:**

codeHtml

```
<div class="card-container">
    {{#Band}}
        <div class="band-badge">🎯 {{Band}}</div>
    {{/Band}}

    <div class="cloze-section">
        <div class="text">{{cloze:Front}}</div>
    </div>

    {{#Back}}
        <div class="hint-box">
            <div class="label">🇻🇳 Gợi ý:</div>
            <div class="meaning-hint">{{Back}}</div>
        </div>
    {{/Back}}

    <div class="footer-section">
        {{#Tag}}
            <div class="tag-pill">🏷️ {{Tag}}</div>
        {{/Tag}}
        {{#ID}}
            <div class="card-id">ID: {{ID}}</div>
        {{/ID}}
    </div>
</div>
```

**📍 Back Template:**

codeHtml

```
<div class="card-container">
    {{#Band}}
        <div class="band-badge">🎯 {{Band}}</div>
    {{/Band}}

    <div class="cloze-section">
        <div class="text">{{cloze:Front}}</div>
        {{#Audio}}
            <div class="audio">{{Audio}}</div>
        {{/Audio}}
    </div>

    <hr class="divider">

    <div class="meaning-section">
        <div class="meaning">{{Back}}</div>
    </div>

    {{#IPA}}
        <div class="info-box ipa-box">
            <div class="label">🗣️ Pronunciation</div>
            <div class="content ipa-text">{{IPA}}</div>
        </div>
    {{/IPA}}

    {{#Example}}
        <div class="info-box example-box">
            <div class="label">✨ Context</div>
            <div class="content">{{Example}}</div>
        </div>
    {{/Example}}

    {{#Note}}
        <div class="info-box note-box">
            <div class="label">💡 Note</div>
            <div class="content">{{Note}}</div>
        </div>
    {{/Note}}

    <div class="footer-section">
        {{#Tag}}
            <div class="tag-pill">🏷️ {{Tag}}</div>
        {{/Tag}}
        {{#ID}}
            <div class="card-id">ID: {{ID}}</div>
        {{/ID}}
    </div>
</div>
```

---

## PHẦN 4: STYLING (CSS DÙNG CHUNG CHO CẢ 2 THẺ)

Copy toàn bộ CSS dưới đây dán vào phần Styling của cả 2 Note Types.

codeCSS

```
/* --- GLOBAL & BACKGROUND --- */
.card {
    font-family: 'Inter', 'Segoe UI', sans-serif;
    font-size: 16px; text-align: center; color: #ffffff;
    background: linear-gradient(135deg, #0f172a 0%, #1e1b4b 50%, #064e3b 100%);
    background-attachment: fixed; margin: 0; padding: 20px;
    display: flex; justify-content: center; align-items: center; min-height: 90vh;
}

/* --- CONTAINER --- */
.card-container {
    background: rgba(255, 255, 255, 0.05);
    backdrop-filter: blur(16px); -webkit-backdrop-filter: blur(16px);
    border: 1px solid rgba(255, 255, 255, 0.1); border-radius: 24px;
    padding: 45px 30px 25px 30px; max-width: 480px; width: 100%;
    box-shadow: 0 8px 32px rgba(0, 0, 0, 0.3); margin: auto; position: relative;
}

/* --- BADGE --- */
.band-badge {
    position: absolute; top: 15px; right: 20px;
    background: rgba(16, 185, 129, 0.15); border: 1px solid rgba(16, 185, 129, 0.4);
    color: #34d399; padding: 4px 12px; border-radius: 20px;
    font-size: 0.85rem; font-weight: 700; box-shadow: 0 0 10px rgba(16, 185, 129, 0.2);
}

/* --- TYPING (BASIC) --- */
input#typeans {
    width: 100%; box-sizing: border-box; padding: 15px 20px;
    font-size: 1.4rem; font-family: 'Inter', sans-serif; text-align: center;
    background: rgba(0, 0, 0, 0.3); border: 2px solid rgba(255, 255, 255, 0.2);
    border-radius: 16px; color: #ffffff; outline: none; transition: all 0.3s ease; margin-top: 15px;
}
input#typeans:focus { border-color: #00f2fe; box-shadow: 0 0 15px rgba(0, 242, 254, 0.3); background: rgba(0, 0, 0, 0.5); }
.typing-result { font-size: 1.5rem; font-weight: 700; margin-bottom: 10px; background: rgba(0, 0, 0, 0.3); padding: 15px; border-radius: 16px; line-height: 1.5; }
.typeGood { color: #10b981; }
.typeBad { color: #ef4444; text-decoration: line-through; opacity: 0.8; }
.typeMissed { color: #fbbf24; }

/* --- CLOZE --- */
.cloze-section { margin-bottom: 20px; }
.text { font-size: 1.6rem; font-weight: 600; line-height: 1.5; color: #ffffff; }
.cloze {
    font-weight: 800; background: linear-gradient(to right, #4facfe 0%, #00f2fe 100%);
    -webkit-background-clip: text; -webkit-text-fill-color: transparent;
    border-bottom: 2px dashed #00f2fe; padding: 0 5px;
}
.hint-box { margin-top: 20px; padding-top: 15px; border-top: 1px dashed rgba(255, 255, 255, 0.2); text-align: center; }
.hint-box .label { font-size: 0.8rem; color: #94a3b8; margin-bottom: 5px; }
.meaning-hint { font-size: 1.1rem; color: #cbd5e1; font-style: italic; }

/* --- COMMON ELEMENTS --- */
.word-section { margin-bottom: 20px; }
.ipa { font-size: 1.1rem; color: #a7f3d0; margin-bottom: 15px; opacity: 0.9; }
.audio { margin-top: 15px; }
.replay-button svg { width: 32px; height: 32px; fill: #4facfe; transition: transform 0.2s ease; }
.replay-button svg:hover { transform: scale(1.1); fill: #00f2fe; }
.divider { border: 0; height: 1px; background: linear-gradient(to right, transparent, rgba(255,255,255,0.2), transparent); margin: 25px 0; }
.meaning-section { margin-bottom: 25px; }
.meaning { font-size: 1.3rem; font-weight: 600; color: #e2e8f0; line-height: 1.4; }

/* --- INFO BOXES --- */
.info-box { background: rgba(0, 0, 0, 0.2); border-radius: 16px; padding: 15px 20px; margin-bottom: 15px; text-align: left; border-left: 4px solid transparent; }
.example-box { border-left-color: #a78bfa; }
.note-box { border-left-color: #fbbf24; }
.ipa-box { border-left-color: #34d399; padding: 10px 20px; }
.label { font-size: 0.85rem; font-weight: 700; text-transform: uppercase; letter-spacing: 1px; margin-bottom: 8px; opacity: 0.8; }
.example-box .label { color: #a78bfa; }
.note-box .label { color: #fbbf24; }
.ipa-box .label { color: #34d399; margin-bottom: 4px; }
.content { font-size: 1.05rem; line-height: 1.5; color: #cbd5e1; }
.example-box .content { font-style: italic; }
.ipa-text { font-family: 'Lucida Sans Unicode', sans-serif; color: #a7f3d0; }

/* --- FOOTER (TAG & ID) --- */
.footer-section { display: flex; justify-content: space-between; align-items: center; margin-top: 30px; padding-top: 15px; border-top: 1px solid rgba(255, 255, 255, 0.1); }
.tag-pill { background: rgba(255, 255, 255, 0.1); padding: 4px 12px; border-radius: 12px; font-size: 0.75rem; color: #94a3b8; letter-spacing: 0.5px; }
.card-id { font-size: 0.7rem; color: #64748b; font-family: monospace; }
```

---

## PHẦN 5: CÚ PHÁP NHẬP LIỆU BẰNG VS CODE (ANKI EDITOR)

Sử dụng định dạng Markdown dưới đây trên VS Code để đẩy thẻ thẳng vào Anki thông qua extension Anki-Connect.

codeMarkdown

```
## Tên_Deck_Của_Bạn

### ID-01
- model: Ielts Minimalist
- tags: topic:ten_topic
- ID: ID-01
- Front: make the most of something
- Back: tận dụng tối đa điều gì
- IPA: /meɪk ðə məʊst əv/
- Band: 7.0-7.5
- Example: I make the most of my weekends.
- Audio: 
- Note: Thường đi với thời gian hoặc cơ hội.
- Tag: topic:ten_topic

### ID-02
- model: Ielts Cloze Minimalist
- tags: topic:ten_topic
- ID: ID-02
- Front: On weekends, I often {{c1::catch up with friends}}.
- Back: gặp gỡ, cập nhật tình hình với bạn bè
- IPA: /kætʃ ʌp wɪð frendz/
- Band: 6.5-7.0
- Example: We talk about work and life.
- Audio: 
- Note: Fixed expression
- Tag: topic:ten_topic
```

(Lưu ý: Sau khi đẩy thẻ vào Anki, sử dụng Add-on **HyperTTS** để tạo Audio hàng loạt cho trường Audio).

---

Tài liệu này được thiết kế để tối ưu hóa quy trình học IELTS Speaking: Học sâu (Typing), Học ngữ cảnh (Cloze), và Quản lý dữ liệu tự động hóa hoàn toàn.
