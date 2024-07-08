# Установка и обновление

Primo RPA Orchestrator (далее в тексте - Orchestrator, Оркестратор) может быть установлен на операционных системах семейств Windows (Windows 2019 Server) и Linux (Astra Linux, Cent OS, РЕДОС).


## Установка на Linux

Подробно процедура установки Оркестратора на операционной системе Linux (на примере Ubuntu Server 22.04) описана в статье [**Руководство по установке Primo RPA Orchestrator на Ubuntu Server 22.04**] (ССЫЫЫЛКА !!!).

Для развертывания Оркестратора выполните следующие шаги в указанном порядке:

1. Установка **PostgreSQL** - Скачайте и установите соответствующую вашей операционной системе версию, используя [инструкцию](https://www.postgresql.org/download/). Затем выполните шаги по подключению по сети и созданию пользователей согласно статье [**Руководство по установке Primo RPA Orchestrator на Ubuntu Server 22.04**] (ССЫЫЫЛКА !!!).

2. Установка **RabbitMQ** - Скачайте и установите нужную версию, используя инструкции для [Debian, Ubuntu и основанных на них дистрибутивах](https://www.rabbitmq.com/docs/install-debian), либо инструкции для [RPM дистрибутивов](https://www.rabbitmq.com/docs/install-rpm).  
Далее следуйте инструкции, описанной в статье [**Руководство по установке Primo RPA Orchestrator на Ubuntu Server 22.04**] (ССЫЫЫЛКА !!!).

4. Установка **nginx** - установите nginx из репозиториев. После установки скопируйте конфигурационный файл и файлы сертификатов, находящиеся в комплекте поставки:
```
cp cert1.rsa /etc/nginx/cert1.rsa
cp cert1.crt /etc/nginx/cert1.crt
cp nginx.conf /etc/nginx/nginx.conf
```
Также данные файлы можно [скачать] (ССЫЫЫЫЛКА НА СКАЧИВАНИЕ???)

🔸 **Указанные файлы строго необходимы для работы Оркестратора.**

Более подробно установка nginx описана в документе [**Руководство по установке Primo RPA Orchestrator на Ubuntu Server 22.04**] (ССЫЫЫЛКА !!!).

4. Установка **UI** - 


## Установка на Windows



### Пошаговая установка Оркестратора
Видео по установке Оркестратора на Windows Server 2019 с WebApi (IIS) можно просмотреть [здесь](https://www.youtube.com/watch?v=IAIRmChw65k&ab_channel=PrimoRPA).

<a href="https://www.youtube.com/watch?v=IAIRmChw65k"><img src="https://raw.githubusercontent.com/PrimoRPA/Docs.Rus/main/.gitbook/assets/video_preview/test_gif.gif" width="850" title="hover text"></a>
