DELETE：删除数据库表中的记录

```sql
DELETE FROM <表名> WHERE ...;
```

例如，我们想删除`students`表中`id=1`的记录，就需要这么写：

```sql
DELETE FROM students WHERE id=1;
```

注意到`DELETE`语句的`WHERE`条件也是用来筛选需要删除的行，因此和`UPDATE`类似，`DELETE`语句也可以一次删除多条记录：

```sql
DELETE FROM students WHERE id>=5 AND id<=7;
```

如果`WHERE`条件没有匹配到任何记录，`DELETE`语句不会报错，也不会有任何记录被删除。例如：

最后，要特别小心的是，和`UPDATE`类似，不带`WHERE`条件的`DELETE`语句会删除整个表的数据：

```sql
DELETE FROM students;
```

这时，整个表的所有记录都会被删除。所以，在执行`DELETE`语句时也要非常小心，最好先用`SELECT`语句来测试`WHERE`条件是否筛选出了期望的记录集，然后再用`DELETE`删除。

### 带子查询的删除语句

```sql
DELETE 
FROM SC
WHERE Sno IN
	(SELETE Sno
     FROM Student
     WHERE Sdept = 'CS');
```

