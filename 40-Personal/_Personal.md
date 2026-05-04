---
tags: [index, personal]
---

# 🌱 Personal

> Nhật ký cá nhân, goals, sách đọc, suy nghĩ.

---

## 📌 Pinned
- [[40-Personal/Goals 2025|🎯 Goals 2025]]

---

## Gần nhất
```dataview
LIST
FROM "40-Personal"
WHERE file.name != "_Personal"
SORT file.mtime DESC
LIMIT 8
```

---

## 📖 Book notes
```dataview
LIST
FROM "40-Personal"
WHERE contains(tags, "book")
SORT file.ctime DESC
```