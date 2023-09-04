# Добавление RPA-проекта 

Для запуска RPA-проекта необходимо:

1. Добавить в Оркестратор RPA-проект или его версию (если проект был добавлен ранее).
2. Развернуть Робота на машине Робота (если не был развернут администратором).

Данный раздел посвящен загрузке проекта в Оркестратор и его последующему обновлению.

## Добавление

Чтобы загрузить архив с готовым проектом, перейдите в раздел **RPA-проекты ➝ Все RPA-проекты** и нажмите кнопку **Добавить RPA-проект**.

:small_blue_diamond: ***Примечание***. *Проект заранее формируется и [упаковывается](https://docs.primo-rpa.ru/primo-rpa/primo-studio/projects/publish) в Студии*.

![](../../.gitbook/assets/0)

Заполните необходимые поля в открывшейся форме.

Общие параметры:
1. **Архив (zip)**\* - нажмите на иконку, чтобы выбрать архив проекта для загрузки. После того, как архив выбран, отобразится поле с выпадающим списком процессов. Укажите стартовый процесс.
1. **Наименование**\* - название проекта, которое будет отображаться в Оркестраторе.
1. **Описание** - краткое описание проекта для отображения в Оркестраторе. 
1. **Разрядность**\* - разрядность Робота, который вправе выполнить этот проект.
1. **Приоритет** - определяет порядок выхода проекта из очереди проектов. Если используется очередь с гарантированным порядком (настраивается в конфигурационном файле Оркестратора администратором), то порядок гарантируется только при наличии у проектов разных приоритетов.
Определяет, как долго проект будет находиться в очереди проектов, когда туда попадет, и в каком порядке проекты будут выходить из очереди проектов при одновременном попадании в неё. Время (сек.) нахождения проекта в очереди проектов задается в конфигурационном файле Оркестратора
1. **Использовать загрушки** - по умолчанию отключено. 

Параметры конфигурации запуска:
1. **Стандартная** - по умолчанию отсутствует. Возможные значения:
   * Отладка - 
   * Релиз - .
1. **Специальная** - по умолчанию не задана.
1. **Версии дистрибутива робота** - только роботы указанных версий дистрибутива будут считаться подходящими для выполнения проекта (привязаны к нему).
1. **Запуск в ограниченном кол-ве экземпляров** - запуск проекта по заданию будет пропущен, если проект в данный момент уже запущен в нескольких (от 1 до N) экземплярах. Не распространяется на ручной запуск робота с проектом (не по заданию).
1. **Не повторять в очереди проектов** - если проект уже находится в очереди проектов, повторно в очередь он добавится.


Параметры работы RDP-сессии:
1. **Закрыть RDP-сессию** - при завершении проекта открытая ранее RDP-сессия, если она не нужна, будет закрыта.
1. **Освободить сессию принудительно** - если поднят этот флаг, робот, когда освобождает RDP-сессию, не смотрит на отсутствие признака освобождения RDP-сессии у других роботов. Должно использоваться, когда только один робот освобождает RDP-сессию за собой, чтобы не ломать работу остальных роботов в этой RDP-сессии
1. **Задержка освобождения RDP-сессии (мсек)** - RDP-сессия может очень быстро понадобиться другому Роботу, чтобы её не пересоздавать заново.

## Обновление 

Здесь же можно добавить новую версию уже существующего RPA-проекта (обновить его). Для этого выделите запись с нужным проектом и используйте кнопку **Добавить версию**. Все версии проекта сгруппированы в виде master–detail: 
* мастером всегда является активная версия проекта;
* неактивные версии, если они имеются, видны при открытии детализации по проекту. 

Активность версии означает, что при автоматическом выполнении проекта (т.е. по заданию) будет использоваться именно активная версия, хотя само задание могло быть создано в прошлом с другой версией проекта.
