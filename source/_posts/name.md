---
title: Array
date: 2018-11-20 14:39:48
type: "tags"
tags:
    -JS
categories: "JS"
description: "数组的方法"
---

## forEach  循环数组

> 一个 # 表示一级标题 相当于 h1 ~ h6

```javascript
// 这里面是代码块
var arr = [1,2,3,4]
arr.forEach((item,index) => {
   console.log(item,index)
})
```

<!-- - 这是无序列表
- 第二项
- 第三项

1. 这是有序
2. 
3. xxxx -->
## Array.isArray
- 用来确定是否为数组
```javascript
Array.isArray([])  true
Array.isArray({})  false
```

## every 
- 判断数组数组是否通过条件筛选
```javascript
var arr = [1, 2, 3, 4]
arr.every(function(item,index){
    if(item<2){
        return true
    }
})
```
## some 
- 判断数组的某一项通过条件即可
```javascript
var arr = [1, 2, 3, 4]
arr.every(function(item,index){
    if(item<2){
        return true
    }
})
```
## sort 
- 排序
```javascript
var arr = [9,1,343,6,43]
arr.sort(function(a,b){
    return a-b
})  // 从小到大
arr.sort(function(a,b){
    return b-a
}) // 从大到小

```
## map
- map 会返回一个新的数组
```javascript
var arr = [1,2,3]
var result = arr.map(item =>{3
  return  item = item +1
})
console.log(result)
```
## filter 
- filter() 方法创建一个新的数组，新数组中的元素是通过检查指定数组中符合条件的所有元素。
```javascript
var arr = [43,45,47]
var result = arr.filter(function(item,index){
    return item>45
})
console.log(result)
```
## concat
-合并数组，并且返回一个新的数组
 ## join(',')
 - 把数组的每一项用逗号连接起来，成为字符串