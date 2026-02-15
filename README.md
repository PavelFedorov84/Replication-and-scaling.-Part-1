# Домашнее задание к занятию "`Репликация и масштабирование. Часть 1`" - `Федоров Павел`



### Задание 1 
На лекции рассматривались режимы репликации master-slave, master-master, опишите их различия.

1. `master-slave

Master-сервер обрабатывает все операции записи (INSERT, UPDATE, DELETE)

Slave-серверы получают обновления от Master и обрабатывают запросы на чтение (SELECT)

Клиенты могут читать данные как с Master, так и с Slaves`

2. `master-master

Все серверы равноправны и могут выполнять операции чтения и записи

Двунаправленная синхронизация данных между всеми серверами

Автоматическая обработка запросов на любом сервере`



### Задание 2

Выполните конфигурацию master-slave репликации, примером можно пользоваться из лекции.

Приложите скриншоты конфигурации, выполнения работы: состояния и режимы работы серверов.
![Название скриншота](https://github.com/PavelFedorov84/Replication-and-scaling.-Part-1/blob/main/img/S2.jpg)


### Задание 3

Выполните конфигурацию master-master репликации. Произведите проверку.

Приложите скриншоты конфигурации, выполнения работы: состояния и режимы работы серверов.

![Название скриншота](https://github.com/PavelFedorov84/Replication-and-scaling.-Part-1/blob/main/img/S3.jpg)
![Название скриншота](https://github.com/PavelFedorov84/Replication-and-scaling.-Part-1/blob/main/img/S3.1.jpg)
![Название скриншота](https://github.com/PavelFedorov84/Replication-and-scaling.-Part-1/blob/main/img/S3.2.jpg)
![Название скриншота](https://github.com/PavelFedorov84/Replication-and-scaling.-Part-1/blob/main/img/S3.3.jpg)
![Название скриншота](https://github.com/PavelFedorov84/Replication-and-scaling.-Part-1/blob/main/img/S3.4.jpg)
![Название скриншота](https://github.com/PavelFedorov84/Replication-and-scaling.-Part-1/blob/main/img/S3.5.jpg)

