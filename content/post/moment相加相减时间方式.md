---
title: "Moment相加相减时间方式"
author: "码哥ray"
tags: ["javascript"]
date: 2019-07-04T14:19:13+08:00
draft: true
---

利用moment对时间进行加减天数，小时数方法
var startTime = '2017-12-12'
对startTime进行加减一天的方法如下
moment(new Date(startTime)).add(1,'days')
moment(new Date(startTime)).subtract(1,'days')

>需要注意的是，moment(param).add()中的param必须是ＩＳＯ格式的时间．不然无效．

