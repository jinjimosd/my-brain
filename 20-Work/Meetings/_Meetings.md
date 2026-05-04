---
tags: [index, meeting]
---

# 🤝 Meetings

---

## Gần nhất
```dataview
TABLE file.ctime AS "Ngày"
FROM "20-Work/Meetings"
WHERE file.name != "_Meetings"
SORT file.ctime DESC
LIMIT 10
```