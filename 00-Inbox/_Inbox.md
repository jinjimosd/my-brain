---
tags: [index, inbox]
---

# 📥 Inbox

> Ghi nhanh vào đây — đừng nghĩ nhiều, xử lý sau.
> **Rule:** Clear inbox mỗi tối trước khi ngủ.

---

## Notes chưa xử lý
```dataview
LIST
FROM "00-Inbox"
WHERE file.name != "_Inbox"
SORT file.ctime DESC
```

---

## Cách xử lý Inbox
- **Xoá** → nếu không cần thiết
- **Move** → chuyển sang đúng thư mục (20-Work, 30-Learning...)
- **Convert** → biến thành Project/Incident/Blog note với template
- **Keep** → nếu chưa biết để đâu, thêm tag `#todo`