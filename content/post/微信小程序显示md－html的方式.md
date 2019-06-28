---
title: "微信小程序显示md－html的方式"
author: "码哥ray"
cover: "/img/cover.jpg"
tags: ["小程序"]
date: 2019-06-28T09:03:41+08:00
draft: true
---

###实现微信小程序中对html 和　markdown　的渲预染有多种方法，可以利用第三方插件，比如wxParse, toWxml等，但是从1.4版本之后，微信退出了自己组件，足以支持这些需求．


##riche-text组件
```
<rich-text nodes="{{nodes}}" bindtap="tap"></rich-text>
Page({
  data: {
    nodes: [{
      name: 'div',
      attrs: {
        class: 'div_class',
        style: 'line-height: 60px; color: red;'
      },
      children: [{
        type: 'text',
        text: 'Hello&nbsp;World!'
      }]
    }]
  },
  tap() {
    console.log('tap')
  }
})
```
###其中nodes参数支持数组和String　２种参数方式．但是一般不推荐字符串类型，会降低性能．
