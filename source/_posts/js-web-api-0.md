---
title: js-web-api
date: 2018-11-21 14:14:26
type: "tags"
tags:
- web-api
category: web-api
description: 事件绑定,事件冒泡
---
## 冒泡，往上冒泡
- 取消冒泡 stopPropadgation() a链接跳转
事件冒泡,根据Dom数冒泡
## 事件代理
好处 代码简洁, 效率高
## 事件绑定
-  addEventListener
-   attachEvent

## 手写ajax
```javascript
var xhr = new XMLHttpRequest()
xhr.open("GET","地址",false)   //false 异步
xhr.onreadystatechange = function(){
    if(xhr.readyState== 4){
        if(xhr.status==200){
            alert(xhr.responseText)
        }
    }
}
xhr.send(null) 
状态码 0 还没调用send方法 1 正在发送请求 2 send完成，已经获取全部信息 3 正在解析返回内容 4解析完成


2xx 表示成功处理
3xx 重定向
4xx 客户端请求错误
5xx 服务器端错误

```
## 跨域问题
- 什么是跨域
- 浏览器有同源策咯
- 协议，域名，端口有一个不同就算跨域
### 有三个标签可以跨域加载资源
- <img src=xxx> // 用于打点统计，统计网站可能是其他域
- <link href=xxx>   可以使用cdn
- <script></script> 用于jsonp
###jsonp
动态生成一个文件
```javascript
<script>
window.callback = function(data){
    console.log(data)
}
</script>
<script src="http:地址"></script>
```
## http header

##存储
- 描述cookie ，session Storage ， localStorage 的区别

###cookie
1 用于客户端和服务器通信
2 有本地存储的功能就被借用
3 使用document.cookie  (key,value)
##缺点
- 存储太小,只有4kb
- 所有http 请求都带着，会影响获取资源的效率
- API简单，需要封装才能用document.cookie = 
###localtionStorage 和sessionStorage
- html5 专门为存储而设计，最大为5M
sessionStorage 浏览器关了，就没数据了
 
## 从输入http到html的详细过程
1 加载资源的形式
- 输入url
- http:// 地址
- 加载html中的静态资源
- <script></script>

2 加载一个资源的过程
- 浏览器根据DNS服务器得到域名的ip地址
- 向这个ip的机器发送http请求
- 服务器收到，处理并返回http请求
- 浏览器得到返回的内容

3 浏览器渲染页面的过程
- html 生成 DOM tree
- css 生成 CSSOM
- 将DOM 和CSSOM 整合成 rendertree
- 遇到<script>时，会执行并阻塞渲染


## window.onload 和DOMContentLoaded的区别
- window.onload页面全部资源加载完成后才会执行，包括图片视频
- DOMContentLoaded DOM 渲染完成即可执行，此时图pain，视屏还可能没有加载完成完
## 性能优化
- 原则
1 多使用内存，缓存或者其他方法
2 减少请求
- 从哪里入手
1 加载页面和静态资源   // 静态资源的压缩合并   静态资源缓存   使用cdn让资源加载更快  使用ssr后端渲染，数据直接输出到html css放前面，js放后面 懒加载 减少DOM操作，多个操作尽量合并在一起执行 事件节流 
2 页面渲染


###事件节流
```javascript
var textarea= $('#textarea')
var timeoutId
textarea.addEventListener('keyup',function(){
    if(timeoutId){
        clearTimeout(titimeoutIdme)
    }
    timeoutId = setTimeout(function(){
        //操作
    },100)
})
```
## 
