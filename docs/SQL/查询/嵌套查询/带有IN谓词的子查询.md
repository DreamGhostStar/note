```sql
SELECT Sno, Sname, Sdept
FROM Student
WHERE Sdept IN
	(SELECT Sdept
    FROM Student
    WHERE Sname = '刘晨')
```

查找刘晨所在系的同学