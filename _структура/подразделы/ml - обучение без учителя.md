---
тип: подраздел
раздел: ["[[ml]]"]
---

# Обучение без учителя

Раздел: [[ml]]

## Все заметки

```dataview
TABLE тип
WHERE contains(подраздел, this.file.link)
SORT тип, file.name
```

## Задачи

```dataview
TABLE формат, сложность, для_повтора, дата_решения
WHERE contains(подраздел, this.file.link) AND тип = "задача"
SORT сложность
```
