---
тип: MOC
раздел: 
---

# Название

## Определения

```dataview
TABLE подраздел
FROM "Определения"
WHERE раздел = this.раздел
SORT подраздел, file.name
```

## Свойства

```dataview
TABLE подраздел
FROM "Свойства"
WHERE раздел = this.раздел
SORT подраздел, file.name
```

## Теоремы

```dataview
TABLE подраздел
FROM "Теоремы"
WHERE раздел = this.раздел
SORT подраздел, file.name
```

## Методы

```dataview
TABLE подраздел
FROM "Методы"
WHERE раздел = this.раздел
SORT подраздел, file.name
```

## Алгоритмы

```dataview
TABLE подраздел, временная_сложность
FROM "Алгоритмы"
WHERE раздел = this.раздел
SORT подраздел, file.name
```

## Структуры данных

```dataview
LIST
FROM "Структуры и типы данных"
WHERE раздел = this.раздел
SORT file.name
```

## Сигналы

```dataview
LIST
FROM "Сигналы"
WHERE contains(раздел, this.раздел)
SORT file.name
```

## Задачи

```dataview
TABLE подраздел, формат, сложность, для_повтора
FROM "Задачи"
WHERE раздел = this.раздел
SORT подраздел, сложность
```
