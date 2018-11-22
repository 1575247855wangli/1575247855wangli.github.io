---
title: JS-Web-API
date: 2018-11-21 11:20:23
type: "tags"
tags: 
    - web-api
category: "web-api"
descript: "web-api"
---
## DOM的本质
DOM的本质是数,是由一个一个节点构成的
## DOM节点操作
1.访问/获取节点

```javascript
document.getElementById(id);　　　　　　　　 　　//返回对拥有指定id的第一个对象进行访问
document.getElementsByName(name);　　　　　　//返回带有指定名称的节点集合　　 注意拼写:Elements
document.getElementsByTagName(tagname); 　　//返回带有指定标签名的对象集合　  注意拼写：Elements
document.getElementsByClassName(classname);  //返回带有指定class名称的对象集合 注意拼写：Elements
```

2.创建节点/属性
```javascript
document.createElement(eName);　　//创建一个节点
document.createAttribute(attrName); //对某个节点创建属性
document.createTextNode(text);　　　//创建文本节点
```

3.添加节点

```javascript
document.insertBefore(newNode,referenceNode);　 //在某个节点前插入节点
parentNode.appendChild(newNode);　　　　　　　　//给某个节点添加子节点
```

4.复制节点

```javascript
cloneNode(true | false);　　//复制某个节点  参数：是否复制原节点的所有属性
```

5.删除节点

```javascript
parentNode.removeChild(node);　　//删除某个节点的子节点 node是要删除的节点
```

注意：为了保证兼容性，要判断元素节点的节点类型(nodeType)，若nodeType==1，再执行删除操作。通过这个方法，就可以在 IE和 Mozilla 完成正确的操作。

nodeType 属性可返回节点的类型.最重要的节点类型是：



6.属性操作

getAttribute(name)　　　　//通过属性名称获取某个节点属性的值
setAttribute(name,value);  //修改某个节点属性的值
removeAttribute(name);　 //删除某个属性

7.查找节点

parentObj.firstChild;　　//如果节点为已知节点的第一个子节点就可以使用这个方法。此方法可以递归进行使用 parentObj.firstChild.firstChild.....

parentObj.lastChild;　　//获得一个节点的最后一个节点，与firstChild一样也可以进行递归使用 parentObj.lastChild.lastChild.....

parentObj.childNodes;   //获得节点的所有子节点，然后通过循环和索引找到目标节点 

8.获取相邻的节点

curtNode.previousSibling;  //获取已知节点的相邻的上一个节点

curtNode.nextSlbling;　　  // 获取已知节点的下一个节点

10.获取父节点

childNode.parentNode;　　//得到已知节点的父节点

11.替换节点

replace(newNode,oldNode);