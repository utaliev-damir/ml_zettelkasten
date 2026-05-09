#oracle #datatype

[[Composite data types]]

Тип данных аналогичный varrays, но в котором нет границ по кол-ву элементов.


```sql
declare 
 type t_type is table of varchar(50); -- объявляем тип данных
 nested_table t_type ;
 
begin
    
    nested_table := t_type('damir', 'anna');
    nested_table.extend; -- перед добавлением нужно расшрить
    nested_table(3) := 'alex';
    nested_table.delete(3); -- удаляет последний элемент
    
    for i in 1..nested_table.count()*2 loop 
    
        if not nested_table.exists(i) then -- проверка есть ли элемент
            nested_table.extend;
            nested_table(i) := 'alex';
        
        end if;
        dbms_output.put_line(nested_table(i));
        
    end loop;
    
end;

```