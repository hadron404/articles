# MySQL 索引记录

## 创建索引

```sql
CREATE INDEX indexName ON mytable(username(length)); 
```

如果是CHAR，VARCHAR类型，length可以小于字段实际长度；如果是BLOB和TEXT类型，必须指定 length。

## 添加索引

### 添加主键索引（PRIMARY）

​	语法：ALTER TABLE     `tablename`   ADD PRIMARY KEY (  `columnname`  )

### 添加UNIQUE(唯一索引)

​	语法：ALTER TABLE    `tablename`   ADD UNIQUE ( `column`)

### 添加INDEX(普通索引)

​	语法：ALTER TABLE        `tablename`    ADD INDEX index_name ( `column` ) 

### 添加FULLTEXT(全文索引)

​	语法：ALTER TABLE     `tablename`   ADD FULLTEXT (column)

### 添加组合索引

语法：ALTER TABLE `tablename` ADD INDEX index_name (`column1,column2，column3`)

## 删除索引

```sql
DROP INDEX [indexName] ON mytable; 
```

## 普通索引、唯一索引、主键索引、全文索引、复合索引

### 普通索引（INDEX）

​	普通索引（由关键字KEY或INDEX 定义的索引）的唯一任务是加快对数据的访问速度。因此，应该只为那些最经常出现在查询条件（where clause）或排序条件（order by clause）中的数据列创建索引。只要由可能，就应该选择一个数据最整齐、最紧凑的数据列（如一个证书类型的数据列）来创建索引。

### 唯一索引(UNIQUE)

​	普通索引允许被索引的数据列包含重复的值。比如说，因为人有可能同名，所以同一个姓名在同一个“员工个人资料”数据表里可能出现两次或更多次。与普通索引类似，不同的就是，索引列的值必须唯一，但允许有空值。

　　如果能确定某个数据列将只包含彼此各不相同的值，在为这个数据列创建索引的时候就应该用关键字UNIQUE把它定义为一个唯一索引。这么做的好处：一是简化了MySQL对这个索引的管理工作，这个索引也因此而变得更有效率；二是MySQL会在有新记录插入数据表时，自动检查新记录的这个字段的值是否已经在某个记录的这个字段里出现过了；如果是，MySQL将拒绝插入那条新记录。也就是说，唯一索引可以保证数据记录的唯一性。事实上，在许多场合，人们创建唯一索引的目的往往不是为了提高访问速度，而只是为了避免数据出现重复。

### 主键索引(PRIMARY)

​	MySQL主键是一种唯一性索引。在前面已经反复多次强调过：必须为主键字段创建一个索引，这个索引就是所谓的“主索引”。主索引与唯一索引的区别是：前者在定义时使用的关键字是`PRIMARY`而不是`UNIQUE`，且不允许有空值。

### 外键索引

​	如果为某个外键字段定义了一个外键约束条件，MySQL就会定义一个内部索引来帮助自己以最有效率的方式去管理和使用外键约束条件。

### 复合索引

为了更多的提高mysql效率可建立复合索引，，遵循“最左前缀原则”。

### 全文索引（FULLTEXT）

用于在一篇文章中，检索文本信息的，适合在进行模糊查询的时候使用。





