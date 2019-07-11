---
title: "Mysql基本查询语句"
author: "码哥ray"
cover: "/img/cover.jpg"
tags: ["mysql"]
date: 2019-07-05T16:29:23+08:00
draft: true
---
Mysql 入门最基本的语句
```
	Mysql -uusername -ppassword  //连接Mysql服务器
```

当脸上服务器后，首先面对的是库，有１个或者多个库，那想要对表进行操作的话，得选则对应的库
可以使用 Show databases 来查看有哪些库

```
	use test //选库的语句	 
```

选库之后就是面对了表
查看库下面所有的表
```
	show tables
```

创建一个数据库 (create database 数据库名称［charset 字符集］)
```
	create databases test1  charset utf8
```

删除一个数据库 (drop databases 数据库名称)
```
	drop databases test1
```
>注意：Mysql中的数据库不能重命名．可以修改表和列的名称



