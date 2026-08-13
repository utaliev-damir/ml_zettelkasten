---
тип: раздел
---

# Машинное обучение

## Концепции

```dataview
TABLE подраздел
WHERE contains(раздел, this.file.link) AND тип = "концепция ml"
SORT подраздел, file.name
```

## Модели

```dataview
TABLE подраздел
WHERE contains(раздел, this.file.link) AND тип = "модель ml"
SORT подраздел, file.name
```

## Методы ML

```dataview
TABLE подраздел
WHERE contains(раздел, this.file.link) AND тип = "метод ml"
SORT подраздел, file.name
```

## Оценивание

```dataview
TABLE подраздел
WHERE contains(раздел, this.file.link) AND тип = "оценивание ml"
SORT подраздел, file.name
```

## Определения

```dataview
TABLE подраздел
WHERE contains(раздел, this.file.link) AND тип = "определение"
SORT подраздел, file.name
```

## Теоремы

```dataview
TABLE подраздел
WHERE contains(раздел, this.file.link) AND тип = "теорема"
SORT подраздел, file.name
```

## Задачи

```dataview
TABLE подраздел, формат, сложность, для_повтора
WHERE contains(раздел, this.file.link) AND тип = "задача"
SORT подраздел, сложность
```

## Сигналы

```dataview
LIST
WHERE contains(раздел, this.file.link) AND тип = "сигнал"
SORT file.name
```
