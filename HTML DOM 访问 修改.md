## HTML-DOM 访问
##### getElementById()方法
```javascript
document.getElementById("intro")；
```
##### getElementByTagName() 方法
```javascript
document.getElementsByTagName("p");
```
##### getElementsByClassName() 方法
在IE5、6、7、8中无效
## HTML DOM 修改
##### 修改 HTML 元素
修改 HTML DOM 意味着许多不同的方面：

    改变 HTML 内容
    改变 CSS 样式
    改变 HTML 属性
    创建新的 HTML 元素
    删除已有的 HTML 元素
    改变事件（处理程序）
##### 创建 HTML 内容
```javascript
document.getElementById("test").innerHTML="New Text!";
```
##### 改变HTML样式
```javascript
document.getElementById("test").style.color="#000";
```
##### 创建新的HTML元素
```javascript
var para=document.createElement("p");
var node=document.createTextNode("This is now");
para.appendChild(node);

var element=document.getElementById("d1");
element.appendChild(para);
```
