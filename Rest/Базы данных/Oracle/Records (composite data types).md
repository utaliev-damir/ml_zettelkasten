#oracle #datatype

[[Composite data types]]

Представляет собой контейнер значений разных типов данных. Может быть только однострочным, в него можно помещать результат select запроса (1 строку). Позволяет хранить в одной переменной список значений. 

Задать тип данных для переменной 
```sql
delare 
-- если хотим взять всю строку, но захватим ненужную инфу
-- если не вся строка понадобится
rec_var employees % rowtype;
-- задаем тип самостоятельно
type rec_var_type is (first_name employees.first_name%type
				   salary number);
-- можем при создании типов использовать другие композитные типы
type rec_var_type is (dep employees.department%type
				   user rec_var_type);
-- и обязательно создадим переменную от нового типа
r_var_new_type rec_var_type;
begin
 --some code
end;
```

Передадим в record sql запрос

```sql
SET serveroutput ON;
DECLARE
    r_emp employees%ROWTYPE;
BEGIN
    SELECT e.*
    INTO   r_emp
    FROM   employees e
    WHERE  employee_id = 101;

    r_emp.salary := 12;

    dbms_output.Put_line(r_emp.first_name
                         || ' '
                         || r_emp.last_name
                         || ' '
                         || r_emp.salary);
END; 
```


Создадим свой record:
```sql
SET 
  SERVEROUTPUT ON;
declare type type_emp is record(
  first_name employees.first_name % type, 
  last_name employees.last_name % type, 
  salary employees.salary % type
);
t_emp type_emp;
begin 
select 
  e.* into t_emp 
from 
  (
    select 
      first_name, 
      last_name, 
      salary 
    from 
      employees 
    where 
      employee_id = 101
  ) e;

dbms_output.put_line(
  t_emp.first_name || ' ' || t_emp.last_name || t_emp.salary
);
end;

```


Создадим record type включающий другой record type
```sql
SET serveroutput ON;
DECLARE  
TYPE type_emp  
IS  
  RECORD  
  (  
    f_name employees.first_name % _TYPE_,  
  s_name employees.last_name % _TYPE_ );  
TYPE type_dep  
IS  
  RECORD  
  (  
    dep _VARCHAR2_(10000),  
    user_rec _TYPE_EMP_);  
  type_dep_rec _TYPE_DEP_;  
BEGIN  
  SELECT 'Damir',  
         'Utaliev'  
  INTO   type_dep_rec.user_rec.f_name,  
         type_dep_rec.user_rec.s_name  
  FROM   dual;  
    
  SELECT 'Senior Machine Learning Engineer and CEO of its own company'  
  INTO   type_dep_rec.dep  
  FROM   dual;  
    
  dbms_output.**Put_line** ( type_dep_rec.user_rec.f_name  
  || ' '  
  || type_dep_rec.user_rec.s_name  
  || ' '  
  || type_dep_rec.dep );  
END;
```