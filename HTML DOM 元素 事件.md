## HTML DOM 元素
##### 创建新元素 appendChild()
```javascript
var para=document.createElement("p");
var note=document.createTextNode("This is now!");
para.appendChild(note);

var element=document.getElementById("test");
element.appendChild(para);
```
##### 创建新元素 insertBofore()
```javascript
var para=document.createElement("p");
var note=document.createTextNode("This is now!");
para.appendChild(note);

var element=document.getElementById("test");
var child=document.getElementById("P1");
element.insertBefore(para,child);
```
##### 删除元素 removeChild()
```javascript
var parent=document.getElementById("parent");
var child=document.getElementById("child")
parent.removeChild(child);
```
##### 替换元素 replaceChild()
```javascript
var para=document.createElement("p");
var note=document.createTextNode("This is now!");
para.appendChild(note);

var element=document.getElementById("test");
var child=document.getElementById("child");
element.replaceChild(para,child);
```
## HTML DOM 事件
##### onload和onunload事件
```javascript
```
##### onchange事件
```javascript
```
##### onmouseover和onmouseout事件
```javascript
```
##### onmousedown、onmouseup 以及 onclick 事件
```javascript
```
