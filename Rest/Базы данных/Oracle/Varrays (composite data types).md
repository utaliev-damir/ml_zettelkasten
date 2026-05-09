#oracle #datatype

[[Composite data types]]

Список - это тип данных, который представляет собой коллекцию элементов одинакового типа. Ограничен в размерах, требует инициализации. Нужно указать какой тип данных будет содержаться в нем и максимальное кол-во элементов. Есть методы - 
* array.count() - возвращает кол-во элементов
* array.limit - максимальное кол-во элементов

***Инициализация в блоке begin***
```sql

declare 
type emp_type is varray(10) of varchar2(100);
empl_array emp_type;
begin 

empl_array := emp_type('Damir', 'Sergey'); -- инициализация в блоке SQL

for i in 1..empl_array.count() loop
    dbms_output.put_line(empl_array(i));
    end loop;

end;
```

***Инициализация в declare***

```sql
declare 
type emp_type is varray(10) of varchar2(100);
empl_array emp_type := emp_type();
begin 
for i in 1..2 loop
    empl_array.extend; 
    select first_name into empl_array(i) 
    from employees where employee_id = 101+i;
    end loop; 
for i in 1..empl_array.count() loop
     dbms_output.put_line(empl_array(i));
    end loop;
end;
```

***Инициализация во внешнем контуре***

```sql
create type emp_arr is varray(10) of varchar2(100);
declare 
empl_array emp_arr := emp_arr();
begin 
for i in 1..2 loop
    empl_array.extend;
    select first_name into empl_array(i) 
    from employees where employee_id = 101+i;
    end loop;
for i in 1..empl_array.count() loop
     dbms_output.put_line(empl_array(i));
    end loop;
end;
```