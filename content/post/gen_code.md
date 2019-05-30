---
title: "计算时间差的方法"
tags: [ "javascript"]
date: 2019-05-29T14:59:59+08:00
draft: true
---
```
const formatDiffTime = (endDate) => {
    let startTime = moment().toDate();  //开始时间
    let endTime = moment(endDate, 'YYYY:MM:DD HH:mm:ss').toDate();    //结束时间
    let diffTime = startTime.getTime() - endTime.getTime();  //时间差的毫秒数
    //计算出相差天数
    let days = Math.floor(diffTime / (24 * 3600 * 1000));
    //计算出小时数
    let leave1_h = diffTime % (24 * 3600 * 1000); //计算天数后剩余的毫秒数
    let hours = Math.floor(leave1_h / (3600 * 1000));
    //计算出分钟数
    let leave1_m = leave1_h % (1000 * 3600);//计算小时后剩余的毫秒数
    let minutes = Math.floor(leave1_m / (1000 * 60));

    if (days && !hours && !minutes) {
        return `${days}天`;
    } else if ((days && hours) || (days && minutes)) {
        return `${days + 1}天`;
    } else if (!days && hours && minutes) {
        return `${hours + 1}小时`;
    } else if (!days && hours && !minutes) {
        return `${hours}小时`
    } else if (!days && minutes) {
        return `${minutes}分钟`;
    } else {
        return '1分钟'
    }
};
```
