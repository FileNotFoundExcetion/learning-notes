1.事务（ACID)：

- 原子性：数据库事务不可分割的单位，要么都做，要么都不做
- 隔离性：事务之间是相互不可见的
- 一致性：事务操作不会改变数据库的状态，唯一性约束
- 持久性：事务提交，宕机也可以恢复

2.隔离级别

读已提交（read committed）：不可重复读：事务 A 多次读取同一数据，事务 B 在事务A多次读取的过程中，对数据作了更新并提交，导致事务A多次读取同一数据时，结果 不一致。

读未提交（read uncommitted）：会出现脏读

可重复读（repeatable read）:MySQL默认的隔离级别，会产生幻读，所谓幻读其实就是会新增数据

串行化（serializable）:锁表，粒度大

3.MySQL执行计划
       select_type 
       表示查询中每个select子句的类型（简单 OR复杂）
       SIMPLE：查询中不包含子查询或者UNION
       查询中若包含任何复杂的子部分，最外层查询则被标记为：PRIMARY
       在SELECT或WHERE列表中包含了子查询，该子查询被标记为：SUBQUERY
       在FROM列表中包含的子查询被标记为：DERIVED（衍生）
       若第二个SELECT出现在UNION之后，则被标记为UNION；若UNION包含在  FROM子句的子查询中，外层SELECT将被标记为：DERIVED
       从UNION表获取结果的SELECT被标记为：UNION RESULT
