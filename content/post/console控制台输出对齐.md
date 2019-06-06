---
title: "Console控制台输出对齐"
author: "ray"
cover: "/img/cover.jpg"
tags: ["nodejs"]
date: 2019-06-06T11:30:22+08:00
draft: true
---

利用占位符  '\t'来进行对齐


```
const obj = {
    version:'2.5.6',
    des:'test is a test',
    create_time:'2019-12-12'
}


console.log('version:\t\t'+obj.version)
console.log('des:\t\t\t'+obj.des)
console.log('create_time:\t'+obj.create_time)

```

在控制台输出的结果就是行之间对齐的
