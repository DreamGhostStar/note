集合操作的种类

+ 并操作 `UNION`
+ 交操作 `INTERSECT`
+ 差操作 `EXCEPT`

### `UNION`

```sql
SELECT *
FROM Student
WHERE Sdept = 'CS'
UNION
SELECT *
FROM Student
WHERE Sage <=19;
```

查询计算机科学系的学生或年龄不大于19岁的学生

+ `UNION`：将多个查询结果合并起来时，系统自动去掉重复元组
+ `UNION ALL` ：将多个查询结果合并起来时，保留重复元组

### `INTERSECT`

```sql
SELECT *
FROM Student
WHERE Sdept = 'CS'
INTERSECT
SELECT *
FROM Student
WHERE Sage <=19;
```

查询计算机科学系的学生并且年龄不大于19岁的学生

### `EXCEPT`

```sql
SELECT *
FROM Student
WHERE Sdept = 'CS'
EXCEPT
SELECT *
FROM Student
WHERE Sage <=19;
```

实际上是查询计算机科学系的学生并且年龄大于19岁的学生