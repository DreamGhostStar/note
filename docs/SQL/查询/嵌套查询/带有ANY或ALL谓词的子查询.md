### 带有ANY（SOME）或ALL谓词的子查询

引入`ANY`和`ALL`谓词，其对象为某个查询结果，表示任意一个值或者全部值

#### 注

> 使用 `ANY` 或 `ALL` 谓词时必须同时使用比较运算

### 示例

```sql
SELECT Sname, Sage
FROM Student
WHERE Sage < ANY(SELECT Sage
              FROM Student
              WHERE Sdept='CS');
```

查询非计算机科学系中比计算机科学系任意一个学生年龄小的学生姓名和年龄

#### 用聚集函数实现

```sql
SELECT Sname, Sage
FROM Student
WHERE Sage <
			(SELECT MAX(Sage)
            FROM Student
            WHERE Sdept='CS');
```

`ALL` 类似