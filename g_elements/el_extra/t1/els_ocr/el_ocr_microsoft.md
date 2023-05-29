# Microsoft OCR

![](<../../../../.gitbook/assets/microsoft_ocr_scope.png>)

Элемент осуществляет подключение к ядру OCR Microsoft. Поддерживается только для Windows 10.

## Свойства
Описание общих свойств элемента см. в разделе [Свойства элемента](https://docs.primo-rpa.ru/primo-rpa/primo-studio/process/elements#svoistva-elementa).\
Символ `*` в названии свойства указывает на обязательность его заполнения.

| Свойство             | Тип                   | Описание                                      |
| -------------------- | --------------------- | --------------------------------------------- |
| ***OCR:*** | |  |
| Язык | String | Язык данных. По умолчанию `"en-US"` |
| Извлекать слова | Boolean | Извлекать положение каждого слова |
| Масштаб | Double | Масштаб изображения |
| Профиль | - | Профиль предварительной обработки изображения, используется для улучшения распознавания текста. По умолчанию **None** - не выбран. <p>Доступные значения: 1) **Screen** - для приложений удаленного рабочего стола; 2) **Scan** - для сканируемых файлов; 3) **Legasy** - настройки движка по умолчанию</p>  |
| ***Вывод:***  |  |  |
| Переменная | Primo.T1.OCR.OCRInst | Приложение OCR |