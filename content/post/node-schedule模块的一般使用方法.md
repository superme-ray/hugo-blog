---
title: "Node Schedule模块的一般使用方法"
author: "ray"
tags: ["nodejs"]
date: 2019-06-21T11:46:41+08:00
draft: true
---
## node-schedule做定时任务有《两种》方式可以选择

**方式1「Date-based Scheduling」**

```
"use strict";
var schedule = require("node-schedule");  

//1. 确定的时间执行
var date = new Date(2016,6,13,15,50,0);  
schedule.scheduleJob(date, function(){  
   console.log("执行任务");
});

//2. 秒为单位执行 
//比如:每5秒执行一次
var rule1     = new schedule.RecurrenceRule();  
var times1    = [1,6,11,16,21,26,31,36,41,46,51,56];  
rule1.second  = times1;  
schedule.scheduleJob(rule1, function(){
    console.log("执行任务秒为单位");
});

//3.以分为单位执行
//比如:每5分种执行一次
var rule2     = new schedule.RecurrenceRule();  
var times2    = [1,6,11,16,21,26,31,36,41,46,51,56];  
rule2.minute  = times2;  
schedule.scheduleJob(rule2, function(){  
    console.log("执行任务分为单位");
});  

//4.以天单位执行
//比如:每天6点30分执行
var rule = new schedule.RecurrenceRule();
rule.dayOfWeek = [0, new schedule.Range(1, 6)];
rule.hour = 6;
rule.minute =30;
var j = schedule.scheduleJob(rule, function(){
 　　　　console.log("执行任务天为单位");
        getData();
});

}
```

**方式2「Cron-style Scheduling」**
```
//其他规则见 https://www.npmjs.com/package/node-schedule
// 规则参数讲解    *代表通配符
//     *    *    *    *    *    *
//     ┬    ┬    ┬    ┬    ┬    ┬
//     │    │    │    │    │    │
//     │    │    │    │    │    └ day of week (0 - 7) (0 or 7 is Sun)
//     │    │    │    │    └───── month (1 - 12)
//     │    │    │    └────────── day of month (1 - 31)
//     │    │    └─────────────── hour (0 - 23)
//     │    └──────────────────── minute (0 - 59)
//     └───────────────────────── second (0 - 59, OPTIONAL)
// 每分钟的第30秒触发： '30 * * * * *'
// 每小时的1分30秒触发 ：'30 1 * * * *'
// 每天的凌晨1点1分30秒触发 ：'30 1 1 * * *'
// 每月的1日1点1分30秒触发 ：'30 1 1 1 * *'
// 每周1的1点1分30秒触发 ：'30 1 1 * * 1'

let date = '10 * * * * *';//每分钟的第10秒触发
schedule.scheduleJob(date, function () {
    console.log("执行任务参数形式");
});
```

