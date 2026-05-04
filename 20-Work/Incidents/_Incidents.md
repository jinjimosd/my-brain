---
tags: [index, incident]
---

# 🚨 Incidents

> Ghi lại mọi sự cố: triệu chứng → root cause → fix → prevention.
> Đây là knowledge base quý nhất của DevOps.

---

## Tất cả incidents
```dataview
TABLE incident_id AS "ID", severity AS "Severity", status AS "Status", service AS "Service"
FROM "20-Work/Incidents"
WHERE file.name != "_Incidents"
SORT file.ctime DESC
```

---

## Đang investigate
```dataview
LIST
FROM "20-Work/Incidents"
WHERE status = "investigating" AND file.name != "_Incidents"
```