# MongoDB笔记

### MongoDB 简介

MongoDB 是一个基于分布式文件存储的数据库。由 C++ 语言编写。皆在为 web 应用提供可扩展的高性能数据存储解决方案。在高负载的情况下，添加更多的节点，可以保证服务器性能。

MongoDB 是一个介于关系数据库和非关系数据库之间的产品，是非关系型数据库数据库中功能最丰富的，最像关系型数据库的。

MongoDB 将数据存储为一个文档，数据结构由键值（key => value）对组成。MongoDB 文档类似于 JSON 对象。字段值可以包含其他文档，数据以及文档数据。



**主要特点：**

- DocumentOriented 文档导向：MongoDB 的数据格式是 JSON 风格的文档（Document）比传统的行列方式更为灵活，可以包含复杂的嵌套对象和数组。
- 高性能：MongoDB 提供了高性能的数据持久化方式，内存计算、索引等使其有非常高的读写性能。
- 高可用性：支持副本集实现高可用，当某节点故障时，可自动故障转移。
- 分片：支持无限水平拓展，可以通过集群和分片支持海量数据和高并发。
- 丰富的查询语言：支持丰富的查询表达式，查询语言同样是 JSON 风格的，可快速查询文档中的内嵌数据。
- 高度灵活的数据模型：非规范的文档模型使 MongoDB 可在不同应用场景中应用更加灵活。
- 索引支持：对任何属性进行索引支持查询优化和排序。

### NoSQL 简介

NoSQL (NoSQL = Not Only SQL)，意即“不仅仅是SQL”。

NoSQL 不使用 SQL 作为查询语言、不强制要求特定的表结构、易扩展、高性能、数据库类型多样种类繁多

在现代计算机系统上每天网络上都会产生庞大的数据。这些数据有很大一部分是由关系型数据库管理系统（RDBMS）来处理的。1970年 E.F.Codd's 提出的关系模型论文“A relational model of data for large shared data banks”，这是的数据建模和应用程序编程更加简单。

通过应用实践证明，关系模型是非常适合客户端服务器编程，远远超出预期的利益，今天它是结构化数据存储在网络和商务应用的主导技术。

NoSQL 是一项全新的数据库革命性运动，早期就有人提出，发展至 2009 年趋势越发高涨。NoSQL 的拥护者们提倡运用非关系型的数据存储，相对于普天盖的的关系型数据库运用，这一概念无疑是一种全新的思维注入。



### MongoDB 概念解析

| SQL术语/概念 | MongoDB术语/概念 | 解释/说明                           |
| :----------- | :--------------- | :---------------------------------- |
| database     | database         | 数据库                              |
| table        | collection       | 数据库表/集合                       |
| row          | document         | 数据记录行/文档                     |
| column       | field            | 数据字段/域                         |
| index        | index            | 索引                                |
| table joins  |                  | 表连接,MongoDB不支持                |
| primary key  | primary key      | 主键,MongoDB自动将_id字段设置为主键 |

<img src="./img/MySQL_MongoDB.png" />

#### 数据库

一个 MongoDB 中可以建立多个数据库。 MongoDB的默认数据库微 “db”，该数据库存储在 data 目录中。

MongoDB 的单个实例可以容纳多个独立的数据库，每一个都有自己的集合和权限，不同的数据库也放置在不同的文件中。

有一些数据库名是保留的，可以直接访问这些有特殊作用的数据库。

- **admin：**从权限角度来看，这是 “root” 数据库。要是将一个用户添加到这个数据库，这个用户自动继承所有数据库权限。一些特定的服务器端命令也只能从这个数据库运行，比如列出所有的数据库或者关闭服务器。
- **local：**这个数据永远不会被复制，可以用来存储限于本地单台服务器的任意组合
- **config：**当 Mongo 用于分片设置时，config 数据库在内部使用，用于保存分片相关信息。



### MongoDB 数据类型

常用的几种数据类型。

| 数据类型           | 描述                                                         |
| :----------------- | :----------------------------------------------------------- |
| String             | 字符串。存储数据常用的数据类型。在 MongoDB 中，UTF-8 编码的字符串才是合法的。 |
| Integer            | 整型数值。用于存储数值。根据你所采用的服务器，可分为 32 位或 64 位。 |
| Boolean            | 布尔值。用于存储布尔值（真/假）。                            |
| Double             | 双精度浮点值。用于存储浮点值。                               |
| Min/Max keys       | 将一个值与 BSON（二进制的 JSON）元素的最低值和最高值相对比。 |
| Array              | 用于将数组或列表或多个值存储为一个键。                       |
| Timestamp          | 时间戳。记录文档修改或添加的具体时间。                       |
| Object             | 用于内嵌文档。                                               |
| Null               | 用于创建空值。                                               |
| Symbol             | 符号。该数据类型基本上等同于字符串类型，但不同的是，它一般用于采用特殊符号类型的语言。 |
| Date               | 日期时间。用 UNIX 时间格式来存储当前日期或时间。你可以指定自己的日期时间：创建 Date 对象，传入年月日信息。 |
| Object ID          | 对象 ID。用于创建文档的 ID。                                 |
| Binary Data        | 二进制数据。用于存储二进制数据。                             |
| Code               | 代码类型。用于在文档中存储 JavaScript 代码。                 |
| Regular expression | 正则表达式类型。用于存储正则表达式。                         |

#### ObjectId

ObjectId 类似唯一的主键，可以很快地去生成和排序，包含 12bytes，含义是：

- 前 4 个字节表示创建 unix 时间戳，格林尼治时间 UTC 时间，比北京时间晚 8 个小时

- 接下来的 3 个字节是机器标识码

- 紧接的两个字节由 id 组成的 pid

- 最后三个字节是随机数

  

  <img src="./img/objectId.jpg"/>

  

MongoDB 中存储的文档必须有一个 _id 键。这个键值可以是任何类型，默认是 ObjectId 对象。由于 ObjectId 中保存了创建的时间戳，所以你不需要为你的文档保存时间戳字段，可以通过 getTimestamp 函数来获取文档的创建时间：

```js
var newObject = ObjectId()
newObject.getTimestamp()
// 输出: ISODate("2023-09-27:14:12Z")
```

### MongoDB 连接

配置好环境变量后可以在终端打开 mongosh.exe 直接就连接到默认本地 test

```sh
mongosh.exe
# 或者
mongosh
```

MongoDB 7.0 之前的老版本可以输入 shell 命令来连接

```apl
# 标准的 URI 连接语法
mongodb://[username:password@]host[:port1][,host2[:port2]],...[/[database][?options]]

# 默认打开本地
mongodb://localhost

# 通过 shell 打开
mongo
```

- **mongodb://**  这是固定格式，必须要指定。
- **username:password@**   可选项，如果设置，在连接数据库服务器之后，驱动都会尝试登录这个数据库
- **host**  必须指定至少一个 host，host1 是这个 URI 唯一要填写的。它指定了要连接服务器的地址。如果要连接复制集，请指定多个主机地址。
- **port**  可选的指定端口，如果不填，默认为 27017
- **database/**  如果指定 username:password@，连接并验证登录指定数据库。若不指定，默认打开 test 数据库。
- **?options**  是连接选项。如果不使用 /database，则前面需要加上 / 所有连接选项都是键值对 key=>value，键值对之间通过 & 或 ; (分号) 隔开

标准的连接格式包含了多个 options ,

| 选项                | 描述                                                         |
| :------------------ | :----------------------------------------------------------- |
| replicaSet=name     | 验证replica set的名称。 Impliesconnect=replicaSet.           |
| slaveOk=true\|false | true:在connect=direct模式下，驱动会连接第一台机器，即使这台服务器不是主。在connect=replicaSet模式下，驱动会发送所有的写请求到主并且把读取操作分布在其他从服务器。false: 在 connect=direct模式下，驱动会自动找寻主服务器. 在connect=replicaSet 模式下，驱动仅仅连接主服务器，并且所有的读写命令都连接到主服务器。 |
| safe=true\|false    | true: 在执行更新操作之后，驱动都会发送getLastError命令来确保更新成功。(还要参考 wtimeoutMS).false: 在每次更新之后，驱动不会发送getLastError来确保更新成功。 |
| w=n                 | 驱动添加 { w : n } 到getLastError命令. 应用于safe=true。     |
| wtimeoutMS=ms       | 驱动添加 { wtimeout : ms } 到 getlasterror 命令. 应用于 safe=true. |
| fsync=true\|false   | true: 驱动添加 { fsync : true } 到 getlasterror 命令.应用于 safe=true.false: 驱动不会添加到getLastError命令中。 |
| journal=true\|false | 如果设置为 true, 同步到 journal (在提交到数据库前写入到实体中). 应用于 safe=true |
| connectTimeoutMS=ms | 可以打开连接的时间。                                         |
| socketTimeoutMS=ms  | 发送和接受sockets的时间。                                    |



### MongoDB 数据库

查看据库

```dart
// 查看所有数据库
show dbs
    
// 查看当前数据库名称
db
```



使用数据库；如果没有则会创建

```scss
use DATABASE_NAME  // 数据库名
```



删除当前数据库

```scss
db.dropDatabase()
```



### MongoDB 集合/合集

查看集合

```scss
show collections

// 或者 

show tables
```

创建集合

```scss
db.createCollection(name, options)

/*
	name：要创建集合的名称
	options：可选参数，指定有关内存大小及索引的选项
*/

// 例如： 创建一个集合
db.createCollection("student", { capped: true, autoIndexId: true, size: 6142800, max: 10000 })
```

options 参数列表

| 字段        | 类型 | 描述                                                         |
| :---------- | :--- | :----------------------------------------------------------- |
| capped      | 布尔 | （可选）如果为 true，则创建固定集合。固定集合是指有着固定大小的集合，当达到最大值时，它会自动覆盖最早的文档。 **当该值为 true 时，必须指定 size 参数。** |
| autoIndexId | 布尔 | 3.2 之后不再支持该参数。（可选）如为 true，自动在 _id 字段创建索引。默认为 false。 |
| size        | 数值 | （可选）为固定集合指定一个最大值，即字节数。 **如果 capped 为 true，也需要指定该字段。** |
| max         | 数值 | （可选）指定固定集合中包含文档的最大数量。                   |



删除集合

```scss
db.collection.drop()         // collection 集合名称

// 例如： 删除一个 student 集合
db.student.drop()
```
