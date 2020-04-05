##SQL执行流程
1. FROM ON WHERE GROUP BY HAVING SELECT DISTINCT ORDER BY LIMIT
##存储引擎
1. **innodb**
	1. 支持行锁和事务和外键
	2. 操作只锁某一行，适合高并发、
	3. 缓存索引和数据
2. **MyISAM**
	1. 支持全文搜索
	2. 不支持事务和行级锁，外键
	3. 即时只操作一条记录也锁住整个表
	4. 只缓存索引，不缓存数据
	5. 消耗少
3. Archive引擎
	1. 只支持INSERT和SELECT
	2. 适合日志应用
3. memory引擎
	1. 类似redis，出来太晚了
2. CSV殷勤
	1. 存储的数据直接可以用excel打开
##join
1. 性能选UnionAll(如果两个都不重复，这样不查重）union要查重
##索引
1. 优点：提高检索效率，降低io成本
2. 缺点：降低更新表的速度，因为不仅要跟新数据还要更新或者添加索引字段
##聚簇索引
1. 逻辑顺序和物理顺序一致，只存在于innodb