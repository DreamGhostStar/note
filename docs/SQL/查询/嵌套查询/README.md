## 嵌套查询

+ 一个`SELECT-FROM-WHERE` 语句称为一个查询块
+ 将一个查询块嵌套在另一个查询块的 `WHERE` 子句或 `HAVING` 短语的条件中的查询称为 `嵌套查询`

```sql
SELECT Sname
FROM Student
WHERE Sno IN
   (SELECT Sno
    FROM SC
    WHERE Cno = '2');
```

+ 上层的查询块称为 `外层查询` 或 `父查询`
+ 下层查询块称为 `内层查询` 或 `子查询`
+ SQL语言允许多层嵌套查询
+ 子查询的限制：不能使用 `ORDER BY` 子句