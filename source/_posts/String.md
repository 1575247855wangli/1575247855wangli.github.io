---
title: String
date: 2018-11-21 09:53:30
type: "tags"
tags: 
    -"JS"
categories: "JS"
description: "常用字符串方法"
---
## length属性
-可以用length属性取得字符串的长度
```javascript
var str = "hello"
str.length //5
```
##charAt()
- 返回字符串的第 n 个字符，如果不在 0~str.length-1之间，则返回一个空字符串。
```javascript
var str = "javascript"
str.charAt(0) // "j"
str.charAt(15) // ''
```
##indexof() ：在字符串中从前向后定位字符和字符串；所有的返回值都是指在字符串的绝对位置，如为空则为- 1
```javascript
string test="asdfjsdfjgkfasdsfsgfhgjgfjgdddd";

test.indexof('d') =2 //从前向后 定位 d 第一次出现的位置

test.indexof('d',1) =2 //从前向后 定位 d 从第二个字符串开始 即s开始 第一次出现的位置

test.indexof('d',5,2) =6 //从前向后 定位 d 从第5 位开始查，查2位，即 从第5位到第7位；
```

## lastIndexOf()
- 返回从 start 到 end（不包括）之间的字符，start、end均为 非负整数。若结束参数(end)省略，则表示从start位置一直截取到最后。

## replace 替换
```javascript
var str = "I love you"
str.replace('love','hate')
```
## trim()  去除空格  去除 str 开头和结尾处的空白字符，返回 str 的一个副本，不影响字符串本身的值
```javascript
var str ="     123"
str.trim()  //"123"
```
##split 
- 把字符串转换为数组 split()

## 截取
1 slice
- str.slice(start[,end])
-  返回从 start 到 end （不包括）之间的字符，可传负值
```javascript
var str = "hello,javascript"
str.slice(0,4) //hell
str.slice(5,-1)  //,javascript
```
2  substring()
- str.substring(start[, end])
- 返回从 start 到 end（不包括）之间的字符，start、end均为 非负整数。若结束参数(end)省略，则表示从start位置一直截取到最后。
```javascript
var str = 'abcdefg';
str.substring(1, 4); //"bcd"
str.substring(1); // "bcdefg"
str.substring(-1); //"abcdefg" 传入负值时会视为0
```

3 substr()
- str.slice(start[,end])
-  返回 str 中从指定位置开始到指定长度的子字符串，start可为负值