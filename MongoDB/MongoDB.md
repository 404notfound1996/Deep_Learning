## MongoDB

1、什么是MongoDB？
MongoDB是一个文档数据库，提供好的性能，领先的非关系型数据库。采用BSON存储文档数据。
BSON（）是一种类json的一种二进制形式的存储格式，简称Binary JSON.
相对于json多了date类型和二进制数组

2、MySQL与MongoDB之间最基本的差别是什么?
MySQL和MongoDB两者都是免费开源的数据库。MySQL和MongoDB有许多基本差别包括数据的表示(data representation)，查询，关系，事务，schema的设计和定义，标准化(normalization)，速度和性能。

通过比较MySQL和MongoDB，实际上我们是在比较关系型和非关系型数据库，即数据存储结构不同

3、MongoDB成为最好NoSQL数据库的原因是什么?
以下特点使得MongoDB成为最好的NoSQL数据库：

面向文件的
高性能
高可用性
易扩展性
丰富的查询语言
4、为什么用MOngoDB？
架构简单
没有复杂的连接
深度查询能力,MongoDB支持动态查询。
容易调试
容易扩展
不需要转化/映射应用对象到数据库对象
使用内部内存作为存储工作区,以便更快的存取数据
5、在哪些场景使用MongoDB？
大数据
内容管理系统
移动端Apps
数据管理
6、monogodb 中的分片什么意思
分片是将数据水平切分到不同的物理节点。当应用数据越来越大的时候，数据量也会越来越大。当数据量增长
时，单台机器有可能无法存储数据或可接受的读取写入吞吐量。利用分片技术可以添加更多的机器来应对数据量增加
以及读写操作的要求

7、MongoDB支持主键外键关系吗
默认MongoDB不支持主键和外键关系。用Mongodb本身的API需要硬编码才能实现外键关联，不够直观且难度
较大

8、MongoDB支持哪些数据类型
String
Integer
Double
Boolean
Object
Object ID
Arrays
Min/Max Keys
Datetime
Code
Regular Expression等
9、在MongoDb中什么是索引
索引用于高效的执行查询,没有索引的MongoDB将扫描整个集合中的所有文档,这种扫描效率很低,需要处理大量
的数据.
索引是一种特殊的数据结构,将一小块数据集合保存为容易遍历的形式.索引能够存储某种特殊字段或字段集的
值,并按照索引指定的方式将字段值进行排序

10、如何添加索引
使用db.collection.createIndex()在集合中创建一个索引
1.
11、如何查询集合中的文档
db.collectionName.find({key:value})
1.
12、用什么方法可以格式化输出结果
db.collectionName.find().pretty()
1.
13、更新数据
db.collectionName.update({key:value},{$set:{newkey:newValue}})
1.
14、如何删除文档
db.collectionName.remove({key:value})
1.
15、在MongoDB中如何排序
并使用 1 和 -1 来指定排序方式，其中 1 表示升序，而 -1 表示降序。

db.connectionName.find({key:value}).sort({columnName:1})
1.
2.
3.
16、什么是聚合
聚合操作能够处理数据记录并返回计算结果。聚合操作能将多个文档中的值组合起来，对成组数据执行各种操作，返回单一的结果。它相当于 SQL 中的 count(*) 组合 group by。对于 MongoDB 中的聚合操作，应该使用aggregate()方法。

db.COLLECTION_NAME.aggregate(AGGREGATE_OPERATION)
1.
17、在MongoDB中什么是副本集（避免单点故障）
在MongoDB中副本集由一组MongoDB实例组成，包括一个主节点多个次节点，MongoDB客户端的所有数据都
写入主节点(Primary),副节点从主节点同步写入数据，以保持所有复制集内存储相同的数据，提高数据可用性

18、如何理解MongoDB中的GridFS机制，MongoDB为何使用GridFS来存储文件？
GridFS是一种将大型文件存储在MongoDB中的文件规范。使用GridFS可以将大文件分隔成多个小文档存放，这样我们能够有效的保存大文档，而且解决了BSON对象有限制的问题

19、索引类型有哪些？
单字段索引(Single Field Indexes)
复合索引(Compound Indexes)
多键索引(Multikey Indexes)
全文索引(text Indexes)
Hash 索引(Hash Indexes)
通配符索引(Wildcard Index)
2dsphere索引(2dsphere Indexes)
20、什么是master或primary？
副本集只能有一个主节点能够确认写入操作来接收所有写操作，并记录其操作日志中的数据集的所有更改(记录在oplog中)。在集群中，当主节点（master）失效，Secondary节点会变为master

21、复制集节点类型有哪些？
优先级0型(Priority 0)节点
隐藏型(Hidden)节点
延迟型(Delayed)节点

投票型(Vote)节点以及不可投票节点