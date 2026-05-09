#oracle #datatype

При работе в PLSQL иногда требуется хранить не только скалярные данные, но такие в которых есть коллекция значений. Например список элементов. 

Для таких случаев с PLSQL есть:
* [[Records (composite data types)|records]] - запись (как однострочный результат SQL запроса)
* [[Nested tables (composite data types) |nested tables]] - неограниченный список с индексацией с 1
* [[Varrays (composite data types) |varrays]] -ограниченный список с индексацией с 1
* [[ Associative arrays (composite data types)|associated arrays]] - словарь

Эти типы данных можно миксовать и создавать например memory table . Когда в переменной будет хранится целая таблица, к данным которой мы сможем обращаться. 