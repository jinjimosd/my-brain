---
week: "<% tp.date.now("gggg-[W]ww") %>"
week_start: <% tp.date.now("YYYY-MM-DD", 0, "isoWeek") %>
week_end: <% tp.date.now("YYYY-MM-DD", 6, "isoWeek") %>
tags: [weekly, review]
mood: 
---

# 📅 Week <% tp.date.now("ww") %> · <% tp.date.now("YYYY") %>
> <% tp.date.now("DD/MM", 0, "isoWeek") %> – <% tp.date.now("DD/MM", 6, "isoWeek") %>

---

## ⚡ Focus tuần này
_Một câu mô tả tuần này tập trung vào gì:_


---

## 📋 Todo tuần này
### 💼 Work
- [ ] 
- [ ] 
- [ ] 

### 📚 Learning
- [ ] 
- [ ] 

### 🌱 Personal
- [ ] 

---

## 💼 Work log
### Thứ Hai · <% tp.date.now("DD/MM", 0, "isoWeek") %>
- 

### Thứ Ba · <% tp.date.now("DD/MM", 1, "isoWeek") %>
- 

### Thứ Tư · <% tp.date.now("DD/MM", 2, "isoWeek") %>
- 

### Thứ Năm · <% tp.date.now("DD/MM", 3, "isoWeek") %>
- 

### Thứ Sáu · <% tp.date.now("DD/MM", 4, "isoWeek") %>
- 

---

## 🚨 Incidents tuần này
```dataview
LIST
FROM "20-Work/Incidents"
WHERE file.ctime >= this.week_start AND file.ctime <= this.week_end
```

---

## 📚 Học được tuần này
- 
- 
- 

### Notes mới trong Learning
```dataview
LIST
FROM "30-Learning"
WHERE file.ctime >= this.week_start AND file.ctime <= this.week_end
```

---

## 💡 Ideas & Suy nghĩ
- 

---

## ✍️ Blog pipeline
```dataview
TABLE status AS "Status"
FROM #blog/draft OR #blog/ready
SORT file.mtime DESC
```

---

## 🌙 Wrap-up cuối tuần
### ✅ Hoàn thành
- 

### ⏩ Chuyển sang tuần tới
- [ ] 

### 📊 Mood & năng lượng
Work:     ⭐⭐⭐⭐⭐
Energy:   ⭐⭐⭐⭐⭐
Learning: ⭐⭐⭐⭐⭐

### 🙏 Grateful for
1. 
2. 
3. 

---

## 🔗 Links
- Tuần trước: [[<% tp.date.now("gggg-[W]ww", -7) %>]]
- [[Home]] · [[_Inbox]] · [[_Work]]