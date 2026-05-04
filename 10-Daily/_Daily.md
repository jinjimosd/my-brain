---
tags: [index, daily]
---

# 📅 Daily Notes

> Nhật ký hàng ngày — mỗi ngày một file.
> Nhấn `Cmd+Shift+D` để mở daily note hôm nay.

---

## 7 ngày gần nhất
```dataview
LIST
FROM "10-Daily"
WHERE file.name != "_Daily"
SORT file.day DESC
LIMIT 7
```

---

## Tháng này
```dataview
LIST
FROM "10-Daily"
WHERE file.name != "_Daily"
AND date(file.name).month = date(today).month
SORT file.day DESC
```