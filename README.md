# Домашнее задание к занятию "Работа с данными (DDL/DML)" - `Манчинский Алексей`


### Инструкция по выполнению домашнего задания

   1. Сделайте `fork` данного репозитория к себе в Github и переименуйте его по названию или номеру занятия, например, https://github.com/имя-вашего-репозитория/git-hw или  https://github.com/имя-вашего-репозитория/7-1-ansible-hw).
   2. Выполните клонирование данного репозитория к себе на ПК с помощью команды `git clone`.
   3. Выполните домашнее задание и заполните у себя локально этот файл README.md:
      - впишите вверху название занятия и вашу фамилию и имя
      - в каждом задании добавьте решение в требуемом виде (текст/код/скриншоты/ссылка)
      - для корректного добавления скриншотов воспользуйтесь [инструкцией "Как вставить скриншот в шаблон с решением](https://github.com/netology-code/sys-pattern-homework/blob/main/screen-instruction.md)
      - при оформлении используйте возможности языка разметки md (коротко об этом можно посмотреть в [инструкции  по MarkDown](https://github.com/netology-code/sys-pattern-homework/blob/main/md-instruction.md))
   4. После завершения работы над домашним заданием сделайте коммит (`git commit -m "comment"`) и отправьте его на Github (`git push origin`);
   5. Для проверки домашнего задания преподавателем в личном кабинете прикрепите и отправьте ссылку на решение в виде md-файла в вашем Github.
   6. Любые вопросы по выполнению заданий спрашивайте в чате учебной группы и/или в разделе “Вопросы по заданию” в личном кабинете.
   
Желаем успехов в выполнении домашнего задания!
   
### Дополнительные материалы, которые могут быть полезны для выполнения задания

1. [Руководство по оформлению Markdown файлов](https://gist.github.com/Jekins/2bf2d0638163f1294637#Code)

---

### Создайте учётную запись sys_temp.
CREATE USER 'sys_temp'@'localhost' IDENTIFIED BY 'sys_temp';

### Выполните запрос на получение списка пользователей в базе данных. (скриншот)
SELECT user FROM mysql.user;

![Скриншот](https://github.com/aleman7713/go_db/blob/main/img/select_users.png)

### Дайте все права для пользователя sys_temp.
GRANT ALL PRIVILEGES ON *.* TO 'sys_temp'@'localhost';

### Выполните запрос на получение списка прав для пользователя sys_temp. (скриншот)
SHOW GRANTS FOR 'sys_temp'@'localhost';

![Скриншот](https://github.com/aleman7713/go_db/blob/main/img/%D0%9F%D1%80%D0%B0%D0%B2%D0%B0_%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D0%B5%D0%BB%D1%8F.png)

### При работе в IDE сформируйте ER-диаграмму получившейся базы данных. При работе в командной строке используйте команду для получения всех таблиц базы данных. (скриншот)

![Скриншот](https://github.com/aleman7713/go_db/blob/main/img/%D0%94%D0%B8%D0%B0%D0%B3%D1%80%D0%B0%D0%BC%D0%BC%D0%B0_%D1%82%D0%B0%D0%B1%D0%BB%D0%B8%D1%86.png)

### Составьте таблицу, используя любой текстовый редактор или Excel, в которой должно быть два столбца: в первом должны быть названия таблиц восстановленной базы, во втором названия первичных ключей этих таблиц. Пример: (скриншот/текст)

![Скриншот](https://github.com/aleman7713/go_db/blob/main/img/tables_pk.png)


### Блок кода
```
CREATE USER 'sys_temp'@'localhost' IDENTIFIED BY 'sys_temp';

SELECT user FROM mysql.user;

GRANT ALL PRIVILEGES ON *.* TO 'sys_temp'@'localhost';

SHOW GRANTS FOR 'sys_temp'@'localhost';

select u.TABLE_NAME, u.COLUMN_NAME, u.ORDINAL_POSITION
from INFORMATION_SCHEMA.KEY_COLUMN_USAGE u
where
   u.TABLE_SCHEMA = 'sakila'  and
   u.CONSTRAINT_NAME = 'PRIMARY'
order by u.TABLE_NAME, u.ORDINAL_POSITION
```
