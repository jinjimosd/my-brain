---
tags: [home, index]
created: 2025-01-15
---

# 🧠 MyBrain

> Bộ não thứ hai của tôi — DevOps · Học tập · Cuộc sống · Blog

---

## ⚡ Quick Capture
_Ghi nhanh vào đây, phân loại sau:_
- [[00-Inbox/_Inbox|📥 Mở Inbox]]
- Hoặc nhấn `Cmd+N` → note tự vào Inbox

---

## 🗺️ Vault Map

| Khu vực       | Link                                      | Mục đích             |
| ------------- | ----------------------------------------- | -------------------- |
| 📥 Inbox      | [[00-Inbox/_Inbox\|Inbox]]                | Ghi nhanh chưa xử lý |
| 📅 Daily      | [[10-Daily/_Daily\|Daily Notes]]          | Nhật ký hàng ngày    |
| 💼 Work       | [[20-Work/_Work\|Work]]                   | Công việc, dự án     |
| 📚 Learning   | [[30-Learning/_Learning\|Learning]]       | Kiến thức kỹ thuật   |
| 🌱 Personal   | [[40-Personal/_Personal\|Personal]]       | Cá nhân, goals       |
| 📖 References | [[50-References/_References\|References]] | Cheatsheets, docs    |

---

## 📅 Daily Notes gần nhất
```dataview
LIST
FROM "10-Daily"
WHERE file.name != "_Daily"
SORT file.day DESC
LIMIT 7
```

---

## 🚀 Projects đang active
```dataview
TABLE started AS "Bắt đầu", deadline AS "Deadline"
FROM "20-Work/Projects"
WHERE status = "active"
SORT file.mtime DESC
```

---

## ✅ Tasks hôm nay
```tasks
not done
due today
sort by priority
```

### Tasks quá hạn
```tasks
not done
due before today
sort by due
limit 5
```

---

## ✍️ Blog Pipeline
```dataview
TABLE status AS "Status", date_created AS "Created"
FROM #blog/draft OR #blog/ready
SORT file.mtime DESC
```

---

## 📚 Learning Notes gần nhất
```dataview
LIST
FROM "30-Learning"
WHERE file.name != "_Learning"
SORT file.mtime DESC
LIMIT 5
```

---

## 🔗 Quick Links
- [[20-Work/Projects/_Projects|🚀 All Projects]]
- [[20-Work/Incidents/_Incidents|🚨 Incidents]]
- [[20-Work/Meetings/_Meetings|🤝 Meetings]]
- [[Templates/_Templates|📄 Templates]]

---

## 🏷️ Tags hay dùng
- #journal · #learning · #project · #incident
- #tech/kubernetes · #tech/terraform · #tech/docker
- #blog/draft · #blog/ready · #blog/published
- #status/active · #status/done · #todo