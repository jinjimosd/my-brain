---
week: W<% tp.date.now("WW") %>
date: <% tp.date.now("YYYY-MM-DD") %>
tags:
  - weekly-review
---
  
# 📊 Weekly Review — W<% tp.date.now("WW") %>
  
## ✅ Hoàn thành tuần này
-

## 📚 Học được gì
-

## 🚨 Incidents tuần này
```dataview
LIST FROM "20-Work/Incidents"
WHERE file.ctime >= date(today) - dur(7 days)
```
  
## ✍️ Blog ideas nảy ra
-
  
## 🎯 Focus tuần tới
- [ ]