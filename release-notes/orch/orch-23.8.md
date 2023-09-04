# Оркестратор 23.8

Примечания к выпуску Оркестратора 23.8 описывают изменения для версии приложения, выпущенной в августе 2023 года.

### Новые функции и улучшения

1. Для очередей обмена данными добавлена статистика по элементам. Она отображается в разделе **Роботы > Очереди обмена данными** в столбце **Кол-во элементов**. Статистика представлена в виде кольцевой диаграммы и позволяет быстро просмотреть, сколько в очереди новых элементов, какое число уже находится в работе и т. д. При нажатии на гиперссылку, размещенную в диаграмме, осуществится переход в конкретную очередь, где также появился график со временем обработки транзакции. Его можно увидеть над таблицей элементов. 
1. Добавлена возможность мультитенантной авторизации AD-пользователей. Теперь, если в конфигурационном файле включена [мультитенантность](https://docs.primo-rpa.ru/primo-rpa/orchestrator/deployment/tenants), то один AD-пользователь сможет авторизоваться в разных тенантах. Для этого в форме авторизации ему нужно установить чекбокс мультитенантной AD-авторизации и явно указать тенант при входе в Оркестратор. В результате AD-группа пользователя будет сопоставляться с ролью Оркестратора из указанного тенанта.
1. Оптимизирована работа Роботов с очередью обмена данными. Для Роботов, считывающих элементы, появилась возможность настраивать тип реакции на блокировку элемента (только для PostgreSQL). Блокировка может возникать при извлечении элемента из очереди по FIFO, если в нее обратилось сразу несколько Роботов-читателей. Тип реакции устанавливается либо в конфигурационном файле WebApi в секции ExchangeQueue - глобально для всех очередей, либо на уровне отдельной очереди в UI Оркестратора. Для этого в UI, в разделе создания/изменения очереди, добавлены параметры:
   * **Реакция на невозможность извлечения элемента по FIFO** - определяет, что следует возвращать Роботу при блокировке элемента: null или ошибку.
     * Значение **Вернуть ошибку** рекомендуется при обработке заранее подготовленной очереди, с которой работают только Роботы-читатели. Это позволяет отличить блокировку от случая, когда в очереди закончились элементы. Таким образом, null будет являться признаком завершения работы с очередью (очередь пустая).
     * Значение **Вернуть null** рекомендуется выбирать при обработке динамической очереди, когда с ней одновременно работают Роботы-писатели и читатели. Тогда null будет возвращаться и при ошибке блокировки, и при пустой очереди, а сигналом завершения работы с очередью будет являться внешний признак. Например, достижение максимального количества итераций. Этот более производительный режим работы и предпочтителен при большой нагрузке.
   * **Кол-во попыток при извлечении элемента по FIFO** - параметр настраивается, только если в качестве реакции на невозможность извлечения элемента выбрано **Вернуть ошибку**. В этом случае при получении ошибки, связанной с блокировкой элемента, Робот будет пытаться получить элемент повторно указанное количество раз. Настройка может привести к увеличению времени извлечения элемента.
1. В заданиях скрыт триггер **Запуск при изменении очереди обмена данными**. Теперь имеется только триггер **Запуск при наличии новых элементов в очереди обмена данными**, работающий асинхронно с добавлением элементов - время опроса очереди настраивается в параметрах. Улучшение призвано упростить использование триггеров, связанных с очередью обмена данными.
1. Значительно ускорена работа раздела **Мониторинг**. 
1. Улучшены виджеты **Использование лицензий Робота** и **Использование лицензий Студии** в разделе **Обзор**. В их описании стало отображаться количество используемых и свободных лицензий. Ранее, чтобы узнать количество, требовалось навести курсор на кольцевую диаграмму.
1. Изменилась проверка уникальности почтового адреса, указанного в учетной записи. Теперь email должен быть уникальным только в рамках тенанта, к которому принадлежит пользователь. Ранее проверка осуществлялась глобально, что не давало возможность указывать один и тот же почтовый адрес в разных тенантах.
1. В журнал событий Оркестратора добавлены столбцы **ID проекта** и **Проект**. Они позволяют быстрее идентифицировать проект, к которому относится событие. Улучшение призвано повысить удобство чтения журнала.
1. Максимальная длина имени Робота увеличена до 200 символов. Теперь названия могут быть более полными и ясными.
1. Максимальная длина названия расписания увеличена до 250-ти символов.
1. Улучшена форма добавления версии проекта:
   * название обновляемого проекта стало более заметным;
   * выпадающий список процессов стал открываться вверх, чтобы не заслонять название проекта.
1. В шаблоне развертывания Робота поле **Логи в консоль** переименовано в **Не выводить в консоль**. Параметр включен по умолчанию.
1. В форме добавления Робота, в расширенных параметрах, добавилась подсказка к полю **Интервал**. Она позволяет понять, как лучше сконфигурировать Робота.


### Исправленные ошибки
1. Исправлена ошибка, из-за которой невозможно было добавить новую версию проекта, если перед этим пользователь удалял неактивные версии. 
1. В журнал Робота попадало множество пустых логов. Ошибка исправлена.
1. Исправлена ошибка, возникавшая при множественном нажатии кнопки **Попросить остановиться** для Робота, выполняющего проект с элементом **Должен остановиться (Should stop)**. В результате этой ошибки Робот, после повторного запуска проекта, останавливался еще раз. Теперь этого не происходит.
1. Устранена ошибка с зависанием статуса Робота в разделе **Робот > Все Роботы**. Статус мог отображаться некорректно. 
1. Невозможно было удалить задание с ручным запуском, если в очереди проектов была запись, ссылающаяся на него. Причина ошибки устранена.
1. Исправлена ошибочная запись логов Робота в консоль при выключенном чекбоксе **Логи в консоль** в шаблоне развертывания.   
1. Оптимизирована работа фильтров в Оркестраторе. Они стали выдавать более корректный результат поиска. 
1. Исправлена ошибка с присутствием проекта в очищенной очереди выполнения. В разделе **RPA-проекты**, при очистке очереди, в ней не пропадал значок присутствия проекта до тех пор, пока страница не обновлялась вручную.


### Где скачать

Скачать комплект поставки Оркестратора 23.8 можно по [этой ссылке](https://disk.primo-rpa.ru/index.php/s/primo?path=%2FRelease%2FOrchestrator). Он содержит 2 архива:
* **Primo RPA Orchestrator 23.8.0 FULL.zip** - полный комплект поставки, в который входят дистрибутивы Оркестратора и внешних компонентов: например, базы данных PostgreSQL Server, брокера сообщений RabbitMQ и др. Вес дистрибутива ~ 3,5 Гб.
* **Primo RPA Orchestrator 23.8.0.zip** - облегченный вариант поставки, который весит около ~ 1,1 Гб.

Робот Enterprise, дистрибутив которого загружается в Оркестратор, скачивается отдельно от комплекта поставки. Архив имеет название **Primo RPA Robot Orchestrator <архитектура> 23.8.0.zip** и находится [здесь](https://disk.primo-rpa.ru/index.php/s/primo?path=%2FRelease%2FRobot).


