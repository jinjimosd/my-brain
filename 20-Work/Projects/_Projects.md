---
tags: [index, project]
---

# 🚀 Projects

---

## 🟢 Active
```dataview
TABLE started AS "Bắt đầu", deadline AS "Deadline"
FROM "20-Work/Projects"
WHERE status = "active" AND file.name != "_Projects"
SORT deadline ASC
```

---

## ✅ Done
```dataview
TABLE started AS "Bắt đầu"
FROM "20-Work/Projects"
WHERE status = "done" AND file.name != "_Projects"
SORT file.mtime DESC
LIMIT 10
```

---

## 💤 Backlog / On hold
```dataview
LIST
FROM "20-Work/Projects"
WHERE status = "backlog" AND file.name != "_Projects"
```