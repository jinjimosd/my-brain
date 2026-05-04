---
tags: [index, work]
---

# 💼 Work

> Tất cả liên quan đến công việc DevOps.

---

## 📁 Khu vực
- [[20-Work/Projects/_Projects|🚀 Projects]]
- [[20-Work/Meetings/_Meetings|🤝 Meetings]]
- [[20-Work/Incidents/_Incidents|🚨 Incidents]]

---

## 🚀 Projects đang active
```dataview
TABLE started AS "Start", deadline AS "Deadline", tags AS "Tags"
FROM "20-Work/Projects"
WHERE status = "active" AND file.name != "_Projects"
SORT file.mtime DESC
```

---

## 🚨 Incidents gần nhất
```dataview
LIST
FROM "20-Work/Incidents"
WHERE file.name != "_Incidents"
SORT file.ctime DESC
LIMIT 5
```

---

## 🤝 Meetings gần nhất
```dataview
LIST
FROM "20-Work/Meetings"
WHERE file.name != "_Meetings"
SORT file.ctime DESC
LIMIT 5
```