# Домашнее задание к занятию «Базы данных» "Макарцев Александр Владимирович"

### Легенда

Заказчик передал вам [файл в формате Excel](https://github.com/netology-code/sdb-homeworks/blob/main/resources/hw-12-1.xlsx), в котором сформирован отчёт. 

На основе этого отчёта нужно выполнить следующие задания.

### Задание 1

Опишите не менее семи таблиц, из которых состоит база данных:

- какие данные хранятся в этих таблицах;
- какой тип данных у столбцов в этих таблицах, если данные хранятся в PostgreSQL.

Приведите решение к следующему виду:

Сотрудники (

- идентификатор, первичный ключ, serial,
- фамилия varchar(50),
- ...
- идентификатор структурного подразделения, внешний ключ, integer).

#### Решение

1. Сотрудники (
- идентификатор сотрудника, первичный ключ, serial,
- Ф.И.О. varchar(100),
- дата найма date,
- оклад decimal(10,2),
- идентификатор должности, внешний ключ, integer,
- идентификатор структурного подразделения, внешний ключ, integer)

2. Должности (
- идентификатор должности, первичный ключ, serial,
- должность varchar(50))

3. Типы подразделений (
- идентификатор типа подразделения, первичный ключ, serial,
- тип подразделения varchar(15))

4. Структурные подразделения (
- идентификатор структурного подразделения, первичный ключ, serial,
- структурное подразделение varchar(100),
- идентификатор типа подразделения, внешний ключ, integer
- идентификатор филиала, внешний ключ, integer)

5. Филиалы (
- идентификатор филиала, первичный ключ, serial,
- адрес филиала varchar(100))

6. Проекты (
- идентификатор проекта, первичный ключ, serial,
- название проекта varchar(50))

7. Назначения на проекты (
- идентификатор сотрудника, внешний ключ, integer,
- идентификатор проекта, внешний ключ, integer,)

## Дополнительные задания (со звёздочкой*)
Эти задания дополнительные, то есть не обязательные к выполнению, и никак не повлияют на получение вами зачёта по этому домашнему заданию. Вы можете их выполнить, если хотите глубже шире разобраться в материале.


### Задание 2*

Перечислите, какие, на ваш взгляд, в этой денормализованной таблице встречаются функциональные зависимости и какие правила вывода нужно применить, чтобы нормализовать данные.