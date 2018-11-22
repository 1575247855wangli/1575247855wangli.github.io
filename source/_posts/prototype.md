---
title: prototype
date: 2018-11-21 10:42:11
type: "tags"
tags: -JS
categories: "JS"
descroption: "原型规则"
---
- 所有的引用类型(数组，对象，函数)，都具有对象的特性，即可自由扩展性(除了'null'例外)
- 自由扩展性
```javascript
var obj={}
obj.a = '1'

var arr =[]
arr.a = '1'

function fn(){}
fn.a= '1'

```
- 所有的函数（不包括数组），都有一个prototype 属性，属性值也是一个普通的对象
- 所有的引用类型(数组，对象，函数), __proto__ 属性值指向他的构造函数的"prototype"属性值
- 当试图得到一个对象的某个属性时，如果这个对象本身没有这个属性，那么会去它的 __proto__ (即它的构造函数的prototype) 中寻找

## this
1 普通函数调用时,this指向全局window
```javascript
function fn(){
    console.log(this) //window
}
```
2 call, apply,bind this指向call,apply,bind 第一个参数
- call, apply 在传递参数的时候，call直接传参，apply 是把参数放在数组里面进行传递 (立即执行)
- bind 是返回的一个副本,不会立即执行 

3 对象调用this指向调用的这个对象

##作用域
- 分为函数和全局作用域
```javascript
var a = 1000
function fn(){
    var b = 200
    console.log(a)
    console.log(b)
}
fn()  //当函数fn里面没有a 这个属性时，会一层一层往上找，形成作用域链
```
## 函数声明，和通过var定义的属性，会提升