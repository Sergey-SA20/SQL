### SQL HomeWork 

---
1. Вывести все поля и все строки.

`SELECT * FROM qa_users;`

2. Вывести всех студентов в таблице

`select students from qa_users;`

3. Вывести только Id пользователей

`select user_id from qa_users;`

4. Вывести только имя пользователей

`select username from qa_users;`

5. Вывести только email пользователей

`select email from qa_users;`

6. Вывести имя и email пользователей

`select username, email from qa_users;`

7. Вывести id, имя, email и дату создания пользователей

`select user_id, username, email, created_on from qa_users;`

8. Вывести пользователей где password 12333

`select * from qa_users where password = '12333';`

9. Вывести пользователей которые были созданы 2021-03-26 00:00:00

`select * from qa_users where created_on = '2021-03-26 00:00:00';`

10. Вывести пользователей где в имени есть слово Анна

`select * from qa_users where username like 'Anna%';`

11. Вывести пользователей где в имени в конце есть 8

`select * from qa_users where username like '%8';`

12. Вывести пользователей где в имени в есть буква а

`select * from qa_users where username like '%a%';`

13. Вывести пользователей которые были созданы 2021-07-12 00:00:00

`select * from qa_users where created_on = '2021-07-12 00:00:00';`

14. Вывести пользователей которые были созданы 2021-07-12 00:00:00 и имеют пароль 1m313

`select * from qa_users where created_on = '2021-07-12 00:00:00' and "password" = '1m313';`

15. Вывести пользователей которые были созданы 2021-07-12 00:00:00 и у которых в имени есть слово Andrey

`select * from qa_users where created_on = '2021-07-12 00:00:00' and username like '%Andrey%';`

16. Вывести пользователей которые были созданы 2021-07-12 00:00:00 и у которых в имени есть цифра 8

`select * from qa_users where created_on = '2021-07-12 00:00:00' and username like '%8%';`

17. Вывести пользователя у которых id равен 10

`select * from qa_users where user_id = 10;`

18. Вывести пользователя у которых id равен 53

`select * from qa_users where user_id = 53;`

19. Вывести пользователя у которых id больше 40

`select * from qa_users where user_id > 40;`

20. Вывести пользователя у которых id меньше 30

`select * from qa_users where user_id < 30;`

21. Вывести пользователя у которых id меньше 27 или больше 88

`select * from qa_users where user_id < 27 or user_id > 88;`

22. Вывести пользователя у которых id меньше либо равно 37

`select * from qa_users where user_id <= 37;`

23. Вывести пользователя у которых id больше либо равно 37

`select * from qa_users where user_id >= 37;`

24. Вывести пользователя у которых id больше 80 но меньше 90

`select * from qa_users where user_id > 80 and user_id < 90;`

25. Вывести пользователя у которых id между 80 и 90

`select * from qa_users where user_id between 80 and 90;`

26. Вывести пользователей где password равен 12333, 1m313, 123313

`select * from qa_users where "password" IN ('12333', '1m313', '123313');`

27. Вывести пользователей где created_on равен 2020-10-03 00:00:00, 2021-05-19 00:00:00, 2021-03-26 00:00:00

`select * from qa_users where created_on IN ('2020-10-03 00:00:00', '2021-05-19 00:00:00', '2021-03-26 00:00:00');`

28. Вывести минимальный id 

`select min(user_id) from qa_users;`

29. Вывести максимальный.

`select max(user_id) from qa_users;`

30. Вывести количество пользователей

`select count(user_id) from qa_users;`

31. Вывести id пользователя, имя, дату создания пользователя. Отсортировать по порядку возрастания даты добавления пользоватлеля.

`select user_id, username, created_on from qa_users order by created_on;`

32. Вывести id пользователя, имя, дату создания пользователя. Отсортировать по порядку убывания даты добавления пользоватлеля.

`select user_id, username, created_on from qa_users order by created_on desc;`

33. Вывести всех работников чьи зарплаты есть в базе, вместе с зарплатами.
```sh
select employee_name, monthly_salary 
from employees
join employees_salary
on employees.id = employees_salary.employee_id;
```
|employee_name|monthly_salary
|-------------|--------------
|Dmitry       |          2300
|Elena        |          1500
|Alex         |          1000
|Victor       |          1100
|Elena        |          2100
|Anna         |          1400
|Milana       |          1500
|Olga         |          1700
|Sergey       |          1750
|Vadim        |          1750
|Anton        |          1850
|James        |          1850
|Luna         |          2000
|Aria         |          2200
|Valentina    |          2800
|Henry        |          4100
|Oliver       |           700
|David        |          1000
|Luke         |           900
|Leo          |          1100
|Scarlett     |          1200
|Penelope     |          1600
|Nora         |          1620
|Lily         |          2350
*Всего* | *24*

34. Вывести всех работников у которых ЗП меньше 2000.
```sh
select employee_name, monthly_salary 
from employees
join employees_salary
on employees.id = employees_salary.employee_id 
where monthly_salary < 2000;
```
|employee_name|monthly_salary
|-------------|--------------
|Elena        |          1500
|Alex         |          1000
|Victor       |          1100
|Anna         |          1400
|Milana       |          1500
|Olga         |          1700
|Sergey       |          1750
|Vadim        |          1750
|Anton        |          1850
|James        |          1850
|Oliver       |           700
|David        |          1000
|Luke         |           900
|Leo          |          1100
|Scarlett     |          1200
|Penelope     |          1600
|Nora         |          1620
*Всего* | *17*

35. Вывести все зарплатные позиции, но работник по ним не назначен. (ЗП есть, но не понятно кто её получает.)
```sh
select employee_name, monthly_salary 
from employees
right join employees_salary
on employees.id = employees_salary.employee_id
where employee_name is null;
```
|employee_name|monthly_salary
|-------------|--------------
|[NULL]       |          1700
|[NULL]       |          1700
|[NULL]       |          2700
|[NULL]       |          2300
|[NULL]       |          2300
|[NULL]       |          1300
|[NULL]       |          3000
|[NULL]       |          1500
|[NULL]       |          1900
|[NULL]       |          2000
|[NULL]       |          7000
*Всего* | *11*
 
36. Вывести все зарплатные позиции  меньше 2000 но работник по ним не назначен. (ЗП есть, но не понятно кто её получает.)
```sh
select employee_name, monthly_salary 
from employees
right join employees_salary
on employees.id = employees_salary.employee_id
where employee_name is null
and monthly_salary < 2000;
```
|employee_name|monthly_salary
|-------------|--------------
|[NULL]       |          1700
|[NULL]       |          1700
|[NULL]       |          1300
|[NULL]       |          1500
|[NULL]       |          1900
*Всего* | *5*
