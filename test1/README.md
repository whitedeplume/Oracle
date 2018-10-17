# 实验一：分析SQL执行计划，执行SQL语句的优化指导

## 实验内容：
- 对Oracle12c中的HR人力资源管理系统中的表进行查询与分析
-  hr用户有一个员工表，有三个字段属性：员工号，姓名，员工的管理员号。普通用户不允许查询执行计划，必须要有plustrace角色才可以。
- 运行和分析教材中的样例
- ![image](https://github.com/whitedeplume/Oracle/blob/master/test1/%E6%9F%A5%E8%AF%A21-1.png)
-![image](https://github.com/whitedeplume/Oracle/blob/master/test1/%E6%9F%A5%E8%AF%A21-2.png)
-![image](https://github.com/whitedeplume/Oracle/blob/master/test1/%E6%9F%A5%E8%AF%A21-3.png)
- ![image](https://github.com/whitedeplume/Oracle/blob/master/test1/%E6%9F%A5%E8%AF%A22-1.png)
- ![image](https://github.com/whitedeplume/Oracle/blob/master/test1/%E6%9F%A5%E8%AF%A22-2.png)
- ![image](https://github.com/whitedeplume/Oracle/blob/master/test1/%E6%9F%A5%E8%AF%A22-3.png)
- 我认为第二种查询方式更优，用时更短
- 设计自己的查询语句
- 查询部门的总人数
```SQL
SELECT d.department_name，count(e.job_id)as "部门总人数"，
FROM hr.departments d，hr.employees e
WHERE d.department_id = e.department_id
GROUP BY department_name
HAVING d.department_name in ('Sales');
```
