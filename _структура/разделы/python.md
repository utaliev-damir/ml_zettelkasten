---
тип: раздел
---

# Python

## Подразделы

- [[python - язык]]
- [[python - numpy]]
- [[python - pandas]]
- [[python - sklearn]]
- [[python - визуализация]]

## Понятия

```dataview
TABLE подраздел
WHERE contains(раздел, this.file.link) AND тип = "понятие кода"
SORT подраздел, file.name
```

## Приёмы

```dataview
TABLE подраздел
WHERE contains(раздел, this.file.link) AND тип = "приём"
SORT подраздел, file.name
```

## Задачи

```dataview
TABLE подраздел, формат, сложность
WHERE contains(раздел, this.file.link) AND тип = "задача"
SORT подраздел
```
