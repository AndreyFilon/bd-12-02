# Домашнее задание к занятию 2 "`«Работа с данными (DDL/DML)»`" - `Филон Андрей`

### Задание 1

1.1. Поднимите чистый инстанс MySQL версии 8.0+. Можно использовать локальный сервер или контейнер Docker.

1.2. Создайте учётную запись sys_temp.

1.3. Выполните запрос на получение списка пользователей в базе данных. (скриншот)
![SELECT User]()

1.4. Дайте все права для пользователя sys_temp.

1.5. Выполните запрос на получение списка прав для пользователя sys_temp. (скриншот)

1.6. Переподключитесь к базе данных от имени sys_temp.

Для смены типа аутентификации с sha2 используйте запрос:

ALTER USER 'sys_test'@'localhost' IDENTIFIED WITH mysql_native_password BY 'password';

1.6. По ссылке https://downloads.mysql.com/docs/sakila-db.zip скачайте дамп базы данных.

1.7. Восстановите дамп в базу данных.

1.8. При работе в IDE сформируйте ER-диаграмму получившейся базы данных. При работе в командной строке используйте команду для получения всех таблиц базы данных. (скриншот)

Результатом работы должны быть скриншоты обозначенных заданий, а также простыня со всеми запросами.



### Ответ

#### 1) Таблица Сотрудники  (исправлено)  

Идентификатор, PRIMARY KEY, INT, NOT NULL, AUTO_INCREMENT  
Фамилия, VARCHAR(30), NOT NULL  
Имя, VARCHAR(30), NOT NULL  
Отчество, VARCHAR(30), NOT NULL  
Адрес, VARCHAR(150), NOT NULL  
Идентификатор должности, FOREIGN KEY, INT, NOT NULL
Идентификатор проекта, FOREIGN KEY, INT, NOT NULL
Идентификатор структурного подразделения, FOREIGN KEY, INT, NOT NULL  

#### 2) Таблица Структурные подразделения   (исправлено)  

Идентификатор, PRIMARY KEY, INT, NOT NULL, AUTO_INCREMENT  
Наименование подразделения, VARCHAR(60), NOT NULL   
Идентификатор Тип подразделения, FOREIGN KEY, INT, NOT NULL  

#### 3) Таблица Должности   

Идентификатор, PRIMARY KEY, INT, NOT NULL, AUTO_INCREMENT  
Наименование, VARCHAR(60), NOT NULL  
Оклад, DECIMAL(10,2), NOT NULL   

#### 4) Таблица Тип подразделения  

Идентификатор, PRIMARY KEY, INT, NOT NULL, AUTO_INCREMENT  
Наименование, varchar(50), not null  

#### 5) Таблица Область  

Идентификатор, PRIMARY KEY, INT, NOT NULL, AUTO_INCREMENT  
Наименование, VARCHAR(50), NOT NULL 

#### 6) Таблица Город  

Идентификатор, PRIMARY KEY, INT, NOT NULL, AUTO_INCREMENT  
Наименование, VARCHAR(50), NOT NULL  

#### 7) Таблица Адрес  

Идентификатор, PRIMARY KEY, INT, NOT NULL, AUTO_INCREMENT  
Наименование, VARCHAR(200), NOT NULL   
 
#### 8) Таблица  Адрес филиала  

Идентификатор области, FOREIGN KEY, INT, NOT NULL  
Идентификатор города, FOREIGN KEY, INT, NOT NULL  
Идентификатор адреса, FOREIGN KEY, INT, NOT NULL  

#### 9) Таблица  Проекты

Идентификатор, PRIMARY KEY, INT, NOT NULL, AUTO_INCREMENT  
Наименование, VARCHAR(200), NOT NULL  

---
