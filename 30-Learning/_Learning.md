---
tags: [index, learning]
---

# 📚 Learning

> Kho kiến thức kỹ thuật — nguồn để viết blog.
> Mỗi concept một note. Link nhiều notes lại = hiểu sâu hơn.

---

## Tất cả learning notes
```dataview
TABLE tags AS "Tags"
FROM "30-Learning"
WHERE file.name != "_Learning"
SORT file.mtime DESC
```

---

## Theo tech stack

### ☸️ Kubernetes
```dataview
LIST FROM "30-Learning" WHERE contains(tags, "tech/kubernetes")
```

### 🏗️ Terraform
```dataview
LIST FROM "30-Learning" WHERE contains(tags, "tech/terraform")
```

### 🐳 Docker
```dataview
LIST FROM "30-Learning" WHERE contains(tags, "tech/docker")
```

### ☁️ AWS
```dataview
LIST FROM "30-Learning" WHERE contains(tags, "tech/aws")
```