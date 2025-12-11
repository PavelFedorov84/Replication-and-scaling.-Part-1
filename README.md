# Домашнее задание по лекции "`Работа с данными (DDL/DML)`" - `Попов Всеволод`

### Задание 1

1.1. Поднимите чистый инстанс MySQL версии 8.0+. Можно использовать локальный сервер или контейнер Docker.

`Поднято через графический интерфейс Docker`

1.2. Создайте учётную запись sys_temp.

`CREATE USER 'sys_temp'@'localhost' IDENTIFIED BY ‘1234’;`

1.3. Выполните запрос на получение списка пользователей в базе данных. (скриншот)

`SELECT User, Host FROM mysql.user;`

![Скриншот-1](https://github.com/MeSeurus/sys-pattern-homework/blob/main/img/screen_1.png)

1.4. Дайте все права для пользователя sys_temp.

`3) GRANT ALL PRIVILEGES ON *.* TO 'sys_temp'@'localhost' WITH GRANT OPTION;`

1.5. Выполните запрос на получение списка прав для пользователя sys_temp. (скриншот)

`4) SHOW GRANTS FOR ‘sys_temp'@'localhost';`

![Скриншот-2](https://github.com/MeSeurus/sys-pattern-homework/blob/main/img/screen_2.png)

1.6. Переподключитесь к базе данных от имени sys_temp.

`exit`
`mysql -h localhost -P 3306 -u sys_temp -p`

Для смены типа аутентификации с sha2 используйте запрос:

`ALTER USER 'sys_temp'@'localhost' IDENTIFIED WITH mysql_native_password BY ‘1234';`

1.6. По ссылке https://downloads.mysql.com/docs/sakila-db.zip скачайте дамп базы данных.

`Выполнено`

1.7. Восстановите дамп в базу данных.

`docker cp /Users/seurus/Downloads/sakila-db/sakila-schema.sql 0f09a34a9255d395825d144b131446a09f650357722b69324466c16ddd07da3b:/tmp/backup_1.sql`
`Внутри контейнера:`
`mysql -u sys_temp -p < /tmp/backup_1.sql`
`docker cp /Users/seurus/Downloads/sakila-db/sakila-data.sql 0f09a34a9255d395825d144b131446a09f650357722b69324466c16ddd07da3b:/tmp/backup_2.sql`
`Внутри контейнера:`
`mysql -u sys_temp -p < /tmp/backup_2.sql`

1.8. При работе в IDE сформируйте ER-диаграмму получившейся базы данных. При работе в командной строке используйте команду для получения всех таблиц базы данных. (скриншот)

`SELECT TABLES FROM sakila;`
![Скриншот-3](https://github.com/MeSeurus/sys-pattern-homework/blob/main/img/screen_3.png)

Результатом работы должны быть скриншоты обозначенных заданий, а также простыня со всеми запросами.

### Задание 2

Составьте таблицу, используя любой текстовый редактор или Excel, в которой должно быть два столбца: в первом должны быть названия таблиц восстановленной базы, во втором названия первичных ключей этих таблиц. Пример: (скриншот/текст)

*table_name*	              *primary_key*
1. `actor                        actor_id`
2. `actor_info                	Null`
3. `address                   	address_id`
4. `category                 	   category_id`
5. `city                      	city_id`
6. `country                   	country_id`
7. `customer                   	customer_id`
8. `customer_list              	Null`
9. `film                       	film_id`
10. `film_actor                 	actor_id, film_id`
11. `film_category             	film_id, category_id`
12. `film_list                 	Null`
13. `film_text                 	film_id`
14. `inventory                	   inventory_id`
15. `language                 	   language_id`
16. `nicer_but_slower_film_list	Null`
17. `payment                   	payment_id`
18. `rental                    	rental_id`
19. `sales_by_film_category    	Null`
20. `sales_by_store            	Null`
21. `staff                     	staff_id`
22. `staff_list                	Null`
23. `store         	            store_id`
