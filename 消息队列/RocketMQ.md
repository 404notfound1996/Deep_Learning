## RocketMQ

[https://blog.csdn.net/qq_42877546/article/details/125425061]

#### 1、RocketMQ Broker中的消息被消费后会立即删除吗？

不会，每条消息都会持久化到CommitLog中，每个Consumer连接到Broker后会维持消费进度信息，当有消息消费后只是当前Consumer的消费进度（CommitLog的offset）更新了。

追问：**那么消息会堆积吗？什么时候清理过期消息？**
默认72小时后会删除不再使用的CommitLog文件

检查这个文件最后访问时间
判断是否大于过期时间
指定时间删除，默认凌晨4点

#### 2、RocketMQ消费模式有几种？

消费模型由Consumer决定，消费维度为Topic。

**集群消费**
一条消息只会被同Group中的一个Consumer消费
多个Group同时消费一个Topic时，每个Group都会有一个Consumer消费到数据

**广播消费**
消息将对一个Consumer Group下的各个Consumer实例都消费一遍。即使这些Consumer属于同一个Consumer Group，消息也会被Consumer Group中的每个Consumer都消费一次。