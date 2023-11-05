# SQL 强化


<!--more-->

## MySQL[^1][^2]

[^1]: SQL从入门到实战 @戴师兄 https://yrzu9y4st8.feishu.cn/mindnotes/bmncn7s9I4IyCLgrrQCskdP7dRf
[^2]: 数据库（SQL）面试题，基础知识（超全面） @weihubeats https://blog.csdn.net/qq_42651904/article/details/83146345

- 语法 select-from-where-group by-having-order by-limit
- 运行 from-where-group by-having-order by-limit-select

### 基础语句

1. select & from
- `select 字段（展示） from 表（数据来源）`
- `*` 所有列
- `as` 别名
- `distinct` 去重，必须置首
- 计算（必须包含被引用的字段，除非可以独立计算）
- `select gdp, distinct population, gdp/population as averGDP from world`

2. where
- 筛选行数据
- `where 字段名 运算符 值`
- 比较符 `=, >, <, >=, <=, <>, !=`
- 条件范围 `in (...), not in, between and（闭区间）, is null, is not null`
- 逻辑 `and, or, not`
- 模糊查询 `like 通配符 字符`，通配符 `%, _` 匹配单个或多个字符
- `where population >= 20, name in ('Germany', 'Norway')`

3. order by
- 规定结果集显示顺序
- `asc, desc` 默认升序
- 主字段
- 将某些排最后 `order by subject in ('chem','phys'), subject`

4. limit
- `limit [位置偏移量,] 行数`
- 返回排名第4-7的数据 `order by area desc limit 3,4`

5. group by
- `group by 字段名`
- 直接使用只取对应组的第一个
- 和聚合函数连用 `AVG(), COUNT(), MAX(), MIN(), SUM()`，计算组内结果
- 和where的区别：可以对各组进行单独求解
- 查询nobel表中2013-2015每年每科目获奖人数，按各年人数降序
```sql
select yr, subject, count(winner)
from nobel
where yr between 2013 and 2015
group by yr, subject
order by yr desc, count(winner) desc
```

6. having
- 对分组后数据进行筛选

### 主要函数

1. `round(x,y)`
- 四舍五入精确到小数点后y位，y负数仅保留
- `round(14.15,-1)=10`

2. `concat(s1,s2,...)`
- 连接字符串
- `concat('My',null,'SQL')=null`

3. `replace(s,s1,s2)`
- 用s2替换s中所有s1

4. `left(s,n), right(s,n), substring(s,n,len)`
- 返回左边或右边n个字符
- 返回第n个起（负数则从右起）长度为len的子字符串，无len取到底

5. `cast(x as type)`
- `char(n), date, time, datetime, decimal`

6. `year(date), month(date), day(date)`
- `month(2021-08-21)=8`

7. `date_add(date,interval expr type), date_sub(...)`
- type: `second, minute, hour, day, week, month, quarter, year`
- `date_sub('2021-08-03 23:59:59',interval 2 month)=2021-06-03 23:59:59`

8. `datediff(date1,date2)`
- 计算间隔天数

9. `date_format(date,format)`
- format 参见[此表](https://www.w3school.com.cn/sql/func_date_format.asp)

10. `if(expr,v1,v2)`
- `if(1<2,'Y','N')=Y`

11. `case expr when v1 then r1[when v2 then r2] ... [else rn] end`

### 高级语句

1. 窗口函数
- `over([partition by 字段][order by 字段 asc/desc])`
- 排序窗口 `rank()over(), dense_rank()over(), row_number()over()`
- 偏移分析 `lag(字段名,偏移量[,默认值])over(), lead(字段名,偏移量[,默认值])over()`

**例题**
- 对每年票数从高到低赋予名次 `rank()over(partition by yr order by votes desc) as posn`
- [**covid每天新增人数**](https://sglzoo.net/wiki/Window_LAG)


2. 表连接

3. 子查询



## Spark SQL[^3]

[^3]: Spark SQL从入门到精通 @浪尖 https://zhuanlan.zhihu.com/p/45729547

## PySpark[^4]

[^4]: 3万字长文 PySpark入门级学习教程，框架思维 @小晨说数据 https://zhuanlan.zhihu.com/p/395431025



## Hive SQL[^5]

[^5]: 一文学完所有的Hive Sql（两万字最全详解） @五分钟学大数据 https://blog.csdn.net/helloHbulie/article/details/115376657



### 常见问题[^6]
[^6]: SQL经典50题&答案 @胖熊酱 https://zhuanlan.zhihu.com/p/67645448
