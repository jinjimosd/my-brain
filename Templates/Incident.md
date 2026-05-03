---
incident_id: INC-<% tp.date.now("YYYYMMDD-HHmm") %>
title: "<% tp.file.title %>"
date: <% tp.date.now("YYYY-MM-DD") %>
time_detected: <% tp.date.now("HH:mm") %>
severity: P2
status: investigating
service: 
tags: [incident, status/investigating]
---

# 🚨 <% tp.file.title %>

> **ID:** INC-<% tp.date.now("YYYYMMDD-HHmm") %> | **Severity:** P2 | **Status:** Investigating

---

## ⏱️ Timeline
| Time | Event |
|---|---|
| <% tp.date.now("HH:mm") %> | Incident detected |
| | |
| | Incident resolved |

**Total downtime:** 

---

## 🔍 Triệu chứng (Symptoms)
> Mô tả những gì đang xảy ra từ góc nhìn người dùng / monitoring

- 
- 

**Error logs:**
```
paste logs ở đây
```

---

## 🎯 Impact
- **Service bị ảnh hưởng:** 
- **Users bị ảnh hưởng:** 
- **Doanh thu / SLA:** 

---

## 🔬 Root Cause Analysis
**Nguyên nhân trực tiếp:**


**Nguyên nhân gốc rễ (5 Whys):**
1. Why? → 
2. Why? → 
3. Why? → 
4. Why? → 
5. Why? → 

---

## 🔧 Cách fix (Resolution)
**Short-term fix:**
```bash
# commands đã chạy
```

**Verify fix:**
```bash
# commands kiểm tra
```

---

## 🛡️ Action Items (Prevent recurrence)
- [ ] 
- [ ] 
- [ ] 

---

## 📎 References
- Monitoring dashboard: 
- Related PR/commit: 
- Related notes: [[]]