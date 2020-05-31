#  求职需求与方向

## 1. 前端：数据可视化    (React/++Vue++)

### 数据可视化图表js库
##### 1. D3  
##### 2. Chart.js  
##### 3. Leaflet  
##### 4. *++ECharts++*
##### 5. Chartist-js  
##### 6. Sigma.js  
##### 7. Metrics-graphics  
##### 8. DC.js  
##### 9. Epoch  
##### 10. Vega

<html>
<a href="https://www.linuxprobe.com/most-popular-visual-project.html" target="_blank">图表js库-网页链接</a>
</html>


---
### Vue+echarts的数据可视化后台搭建项目

<html>
<a href="https://juejin.im/post/5d08405a5188253049042d72" target="_blank">项目1-数据可视化小白版前端</a>
<br/>
<a href="https://github.com/dongsuo/py_vislib" target="_blank">项目1-数据可视化小白版后端</a>
</html>

> 

<html>
<a href="https://github.com/PanJiaChen/vue-element-admin" target="_blank">项目2-潘神版</a>
</html>

---
### 可视化项目示例：
<html>
<a href="https://blog.csdn.net/xyjkhrq/article/details/104140097" target="_blank">可视化页面展示-网页链接</a>
</html>


---


## 2. 后端：数据持续化收集+分析
###### 工具：Hadoop、Hive、HBase、Kafka、MapReduce、Spark、Pig、es、Zookeeper、HDFS
---
##### Hadoop 是必学的，学完这个之后后面可以根据你想做的方向进行针对性学习。 
##### Hadoop 学习完之后就要分方向了：数仓离线计算、实时计算、流式计算等等。
###### 离线重点掌握 Hive、MapReduce。
###### 实时重点掌握 Spark、Flink。
###### 然后像 Zookeeper、Kafka、HDFS、Yarn 无论哪个方向都得学的。

### Hadoop：
##### Hadoop是一个开源框架，允许使用简单的编程模型在跨计算机集群的分布式环境中存储和处理大数据。它的设计是从单个服务器扩展到数千个机器，每个都提供本地计算和存储
Hadoop可运行于一般的商用服务器上，具有高容错、高可靠性、高扩展性等特点,特别适合写一次，读多次的场景

>
##### 适合
* 大规模数据
* 流式数据（写一次，读多次）
* 商用硬件（一般硬件）

##### 不适合
* 低延迟的数据访问
* 大量的小文件
* 频繁的修改文件（基本上就是写一次）

#### Hadoop架构
![image](https://atts.w3cschool.cn/attachments/image/wk/hadoop/architecture.png)

* HDFS: 分布式文件存储
* YARN: 分布式资源管理
* MapReduce: 分布式计算
* Others: 利用YARN的资源管理功能实现其他的数据处理方式
内部各个节点基本都是采用Master-Woker架构

> 

#### HDFS存储block的流程图
![image](https://atts.w3cschool.cn/attachments/image/wk/hadoop/hdfs-write.png)

#### HDFS - 读文件
![image](https://atts.w3cschool.cn/attachments/image/wk/hadoop/hdfs-read.png)

#### HDFS - 可靠性
1. DataNode可以失效

DataNode会定时发送心跳到NameNode。如果一段时间内NameNode没有收到DataNode的心跳消息，则认为其失效。此时NameNode就会将该节点的数据（从该节点的复制节点中获取）复制到另外的DataNode中

2. 数据可以毁坏

无论是写入时还是硬盘本身的问题，只要数据有问题（读取时通过校验码来检测），都可以通过其他的复制节点读取，同时还会再复制一份到健康的节点中

3. NameNode不可靠
### MapReduce(Map+Reduce):
##### Map负责将输入域的数据生成一组单一键值对，Reduce对键值对进一步缩小统计，使得键值对尽可能的高效

##### MapReduce本身就是用于并行处理大数据集的软件框架。MapReduce 的根源是函数性编程中的 map 和 reduce 函数。它由两个可能包含有许多实例（许多 Map 和 Reduce）的操作组成。Map 函数接受一组数据并将其转换为一个键/值对列表，输入域中的每个元素对应一个键/值对。Reduce 函数接受 Map 函数生成的列表，然后根据它们的键（为每个键生成一个键/值对）缩小键/值对列表 。

##### MapReduce的基本流程
![image](https://atts.w3cschool.cn/attachments/image/wk/hadoop/mapreduce-process-overview.png)

![image](https://atts.w3cschool.cn/attachments/image/wk/hadoop/mapreduce-data-process.png)

#### Hbase与Hadoop系各产品之间的关系：
##### HBase的数据通常存储在HDFS上。++==HDFS==为HBase提供了高可靠性的底层存储支持++。++==Hbase==是Hadoop data base即Hadoop数据库。它是一个适合于非结构化数据存储的数据库，HBase基于列的而不是基于行的模式++。HBase是Google Bigtable的开源实现，类似Google Bigtable利用GFS作为其文件存储系统，==HBase利用Hadoop HDFS作为其文件存储系统==；Google运行MapReduce来处理Bigtable中的海量数据，HBase同样利用==Hadoop MapReduce来处理HBase中的海量数据==      HDFS为HBase提供了高可靠性的底层存储支持，Hadoop ++MapReduce为HBase提供了高性能的计算能力++，==Zookeeper为HBase提供了稳定服务和failover机制==。==Pig和Hive==还为HBase提供了高层语言支持，使得在HBase上进行==数据统计处理==变的非常简单。 ==Sqoop则为HBase提供了方便的RDBMS（关系型数据库）数据导入功能==，使得传统数据库数据向HBase中迁移变的非常方便。

#### Hbase -> Hadoop的基础数据库
#### HDFS -> Hbase的文件存储器 用于提供可靠的底层存储支持
#### MapReduce -> 处理Hbase中的海量数据
#### Zookeeper -> 为Hbase提供稳定服务和failover机制（保证Hbase的稳定正常运行）
#### Sqoop为Hbase提供从关系型数据库（Mysql/Oracle）导入数据的功能



