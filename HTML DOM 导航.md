## HTML DOM 节点列表
getElementsByTagName() 方法返回节点列表。节点列表是一个节点数组。
```javascript
x=document.getElementsByTagName("p");
document.write("The innerHTML of the second paragraph is: " + x[1].innerHTML);
```
## HTML DOM 节点列表长度
length 属性定义节点列表中节点的数量。
您可以使用 length 属性来循环节点列表：
```javascript
x=document.getElementsByTagName("p");
for (i=0;i<x.length;i++)
  { 
  document.write(x[i].innerHTML);
  document.write("<br>");
  }
```
## HTML DOM 导航节点关系
您能够使用三个节点属性：parentNode、firstChild 以及 lastChild ，在文档结构中进行导航。
```javascript
```
## HTML DOM 根节点
这里有两个特殊的属性，可以访问全部文档：
    document.documentElement - 全部文档
    document.body - 文档的主体
```javascript
```
## HTML DOM childNodes 和 nodeValue
除了 innerHTML 属性，您也可以使用 childNodes 和 nodeValue 属性来获取元素的内容。
下面的代码获取 id="intro" 的 <p> 元素的值：
```javascript
var txt=document.getElementById("intro").childNodes[0].nodeValue;
document.write(txt);
```
