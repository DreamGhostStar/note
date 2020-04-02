### 增加列

```sql
alter table tableName add columnName varchar(30); 
```

### 修改列类型

```sql
alter table tableName alter column columnName varchar(4000) 
```

### 修改列的名称

```sql
EXEC  sp_rename   'tableName.column1' , 'column2'  (把表名为tableName的column1列名修改为column2)  
```

### 删除列

```sql
alter table tableName drop column columnName;
```

