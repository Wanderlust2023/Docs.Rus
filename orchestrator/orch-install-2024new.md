# Установка и обновление

Primo RPA Orchestrator (далее в тексте - Orchestrator, Оркестратор) может быть установлен на операционных системах семейств Windows (Windows 2019 Server) и Linux (Astra Linux, Cent OS, РЕДОС).


## Установка на Linux

Для развертывания Оркестратора выполните следующие шаги в указанном порядке:

1. Установка **PostgreSQL** - Скачайте и установите соответствующую вашей операционной системе версию, используя [инструкцию](https://www.postgresql.org/download/).

2. Установка **RabbitMQ** - Скачайте и установите нужную версию, используя инструкции для [Debian, Ubuntu и основанных на них дистрибутивах](https://www.rabbitmq.com/docs/install-debian), либо инструкции для [RPM дистрибутивов](https://www.rabbitmq.com/docs/install-rpm).

3. Установка **nginx** - установите nginx из репозиториев. После установки скопируйте конфигурационный файл и файлы сертификатов, находящиеся в комплекте поставки:
```
cp cert1.rsa /etc/nginx/cert1.rsa
cp cert1.crt /etc/nginx/cert1.crt
cp nginx.conf /etc/nginx/nginx.conf
```
Более подробно установка nginx описана в документе [Руководство по установке Nginx под CentOS 8] (LIIIIIINK !!!) 

4. 


## Установка на Windows



### Пошаговая установка Оркестратора
Видео по установке Оркестратора на Windows Server 2019 с WebApi (IIS) можно просмотреть [здесь](https://www.youtube.com/watch?v=IAIRmChw65k&ab_channel=PrimoRPA).

<a href="https://www.youtube.com/watch?v=IAIRmChw65k"><img src="https://raw.githubusercontent.com/PrimoRPA/Docs.Rus/main/.gitbook/assets/video_preview/test_gif.gif" width="850" title="hover text"></a>
