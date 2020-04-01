+ 引入`EXISTS`谓词，其对象也是某个查询结果，但表示这个查询结果是否为空，返回真值

+ 带 有 `EXISTS` 谓词的子查询不反悔任何数据，只产生逻辑真值 `true` 或 `false`

```sql
SELECT Sname, Teacher_id
FROM Student
WHERE EXISTS
		(SELECT *
		FROM Teacher
		WHERE Student.Teacher_id = Teacher.Sno);
```

选择学生的所教教师id与Teacher中的教师id相同的数据，类似于外连接的

