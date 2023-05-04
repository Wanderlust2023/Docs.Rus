# Чтение формулы из ячейки

![](<../../../.gitbook/assets/image (100) (1) (1) (1) (1) (1) (1) (10) (177).png>)

![](<../../../.gitbook/assets/excel-read-cell-formula.png>)

Элемент читает формулу из заданной ячейки Excel.

## Свойства
Описание общих свойств элемента см. в разделе [Свойства элемента](https://docs.primo-rpa.ru/primo-rpa/primo-studio/process/elements#svoistva-elementa).\
Символ `*` в названии свойства указывает на обязательность его заполнения.

| Свойство             | Тип                   | Описание                         |
| -------------------- | --------------------- | -------------------------------- |
| ***Excel***  | |  |
| Ячейка\*             | String   | Ячейка, из которой нужно извлечь формулу. Пример: `"A4"`  |
| Страница             | String   | Название страницы с указанной ячейкой |
| Индекс страницы      | Int32    | Порядковый номер страницы, отсчет с 0 |
| ***Вывод***  | |  |
| Формула\*            | String   | Переменная, в которой будет храниться формула, полученная из ячейки |