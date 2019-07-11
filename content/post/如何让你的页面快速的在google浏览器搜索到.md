---
title: "如何让你的页面快速的在google浏览器搜索到"
date: 2019-07-03T15:49:46+08:00
draft: true
---
   在你的博客或者网站中搜索框内输入搜索内容，将点击事件直接redirect到google搜索页面，前提是你必须在你的html里面设置了关键字，等等；

```
  //输入的内容
  q = encodeURIComponent(q);
  redirect to('https://www.google.com.hk/#hl=zh-CN&q=site:example.com' + q);
```
