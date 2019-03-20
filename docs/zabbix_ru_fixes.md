# Zabbix - проблема с кодировкой

## Если возникает проблема с кодировкой - видны символы ??? вместо русского или другого языка (кроме англйиского)

Заходим на сервер, где установлен mysql, и подключаемся к базе:

```
root@zabbix:/home/user1# mysql -u root -p
Enter password:
```

Подключаемся к базе zabbix и посмотрим таблицы, которые имеют кодировку, отличную от utf8:
```
use zabbix
select `TABLE_NAME`,t.`TABLE_COLLATION` from `information_schema`.`TABLES` t where t.`TABLE_SCHEMA` = 'zabbix' and t.`TABLE_COLLATION` != 'utf8_general_ci';
```

Результат будет примерно следующим:
```
+----------------------------+-------------------+
| TABLE_NAME                 | TABLE_COLLATION   |
+----------------------------+-------------------+
| application_discovery      | latin1_swedish_ci |
| application_prototype      | latin1_swedish_ci |
...
| widget_field               | latin1_swedish_ci |
+----------------------------+-------------------+
42 rows in set (0.00 sec)
```

Берем все таблицы, которые мы получили выше, и выполняем изменение кодировки:
```
ALTER TABLE application_discovery CONVERT TO CHARACTER SET utf8;
ALTER TABLE application_prototype CONVERT TO CHARACTER SET utf8;

...
ALTER TABLE widget_field CONVERT TO CHARACTER SET utf8;
```

Не забываем изменить кодировку самой базы:
```
ALTER DATABASE zabbix DEFAULT CHARACTER SET utf8;
```

Все!