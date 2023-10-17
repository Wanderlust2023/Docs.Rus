# Создание элемента очереди

Чтобы добавить элемент через интерфейс Оркестратора:
1. Выделите нужную очередь и нажмите на количество элементов в ней.
2. Откроется раздел со списком элементов.
3. Вверху страницы нажмите кнопку **Добавить элемент** и укажите его параметры.

**Таблица 2 - Параметры элемента очереди**.

| Параметр                                                          | Описание                                                                                    |
| ----------------------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| Натуральный ключ | Содержательный идентификатор элемента очереди. Может быть глобальным в пределах очереди, в пределах всех очередей или уникальность может отсутствовать |
| Метаданные       | Словарь **Ключ-значение** с произвольными строковыми данными |
| Дата, до которой элемент считается недоступным     | Время, до которого откладывается обработка элемента роботом |
| Дата, после которой элемент считается недоступным  | Время, после которого элемент будет удален из очереди       |
| Статус элемента очереди     | Текущий статус элемента в истории его статусов: «Успешно», «Ошибка общего вида», «Бизнес-ошибка». В UI статусы отображаются сл. образом: <p>•	«New» – элемент добавлен в очередь, еще не прочитан. Отсутствует в истории статусов, вычисляется по косвенным признакам элемента. </p><p>•	«InProgress» – элемент прочитан (псевдостатус).</p><p>•	«Success» – «Успешно».</p><p>•	«Error» – «Ошибка общего вида».</p><p>•	«Business Error» – «Бизнес-ошибка»</p> |
| Теги    | Произвольные строки, по которым может осуществляться поиск элементов |

# Управление элементами

Элементы очереди можно удалять, клонировать и повторять. 

При клонировании и повторении элементы снова ставятся в очередь. Клонирование отличается от повторения тем, что клонированный элемент сбрасывает счетчик «Количество повторных помещений элемента в очередь...», таким образом, он становится полностью новым элементом. 

По событиям, связанным с работой роботов с очередью, вычисляется статистика по очереди – количество элементов очереди в разных статусах и график среднего времени (по окну) обработки элемента очереди роботом (разница времени прочтения элемента и проставления ему финального статуса).   