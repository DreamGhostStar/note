UPDATE：更新数据库表中的记录，必须使用 `UPDATE` 语句

### 基本语法

```sql
UPDATE <表名> SET 字段1=值1, 字段2=值2, ... WHERE ...;
```

例如，我们想更新`students`表`id=1`的记录的`name`和`score`这两个字段，先写出`UPDATE students SET name='大牛', score=66`，然后在`WHERE`子句中写出需要更新的行的筛选条件`id=1`：

```sql
UPDATE students SET name='大牛', score=56 WHERE id=2;
```

注意到`UPDATE`语句的`WHERE`条件和`SELECT`语句的`WHERE`条件其实是一样的，因此完全可以一次更新多条记录：

```sql
UPDATE students SET name='小牛', score=77 WHERE id>=5 AND id<=7;
```

在`UPDATE`语句中，更新字段时可以使用表达式。例如，把所有80分以下的同学的成绩加10分：

```sql
UPDATE students SET score=score+10 WHERE score<80;
```

如果`WHERE`条件没有匹配到任何记录，`UPDATE`语句不会报错，也不会有任何记录被更新

最后，要特别小心的是，`UPDATE`语句可以没有`WHERE`条件，例如：

```sql
UPDATE students SET score=60;
```

这时，整个表的所有记录都会被更新。所以，在执行`UPDATE`语句时要非常小心，最好先用`SELECT`语句来测试`WHERE`条件是否筛选出了期望的记录集，然后再用`UPDATE`更新。

### 修改多个元组的值

```sql
UPDATE Student SET Sage = Sage + 1;
```

会将 `Student` 表中的 `Sage` 字段值全部加一

### 带子查询的修改语句

```sql
UPDATE SC
SET Grade = 0
WHERE Sno IN
	(SELETE Sno
     FROM Student
     WHERE Sdept = 'CS');
```

