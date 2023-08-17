# Чтение колонки

![](<../../../.gitbook/assets/image (100) (1) (1) (1) (1) (1) (1) (10) (177).png>)

![](<../../../.gitbook/assets/excel-read-column.png>)

Элемент считывает данные из колонки Excel. Путь до файла, тип драйвера и прочие параметры предварительно настраиваются в контейнере [Приложение Excel](https://docs.primo-rpa.ru/primo-rpa/g_elements/el_basic/els_excel/el_excel_app). **Чтение колонки** размещается внутри этого контейнера.

## Свойства
Описание общих свойств элемента см. в разделе [Свойства элемента](https://docs.primo-rpa.ru/primo-rpa/primo-studio/process/elements#svoistva-elementa).\
Символ `*` в названии свойства указывает на обязательность его заполнения.

| Свойство             | Тип                   | Описание                         |
| -------------------- | --------------------- | -------------------------------- |
| ***Excel:***  | |  |
| Ячейка\*             | String   | Идентификатор начальной ячейки. Пример: `"A4"`  |
| Страница             | String   | Название страницы, на которой находится колонка с данными |
| Индекс страницы      | Int32    | Порядковый номер страницы, отсчет с 0. Пример: `0` |
| ***Вывод:***  | |  |
| Данные\*             | List\<Object\> | Переменная, в которой будут храниться данные, полученные из колонки |

**Пример заполнения свойств**:

![](<../../../.gitbook/assets/excel-read-column2.png>)

## Обучающий пример 
Проект, в котором считываются данные из колонки, можно найти [здесь](https://github.com/PrimoRPA/Learning/tree/master/WorkWithExcelExample). Проект имеет название WorkWithExcelExample, в качестве типа процесса выбрана **Последовательность**. Чтобы просмотреть процессы проекта, загрузите его в Студию.
