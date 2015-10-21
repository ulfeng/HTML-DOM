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
##### createDocumentFragment()
DocumentFragment：表示文档的一部分（或一段），更确切地说，它表示一个或多个邻接的 Document 节点和它们的所有子孙节点。<br>
使用appendChild 逐个向DOM文档中添加1000个新节点，使用示例：
```javascript
for(var i = 0; i<1000; i++){
    var el = document.createElement("p");
    el.innerHTML = i;
    document.body.appendChild(el);
}
```
使用 createDocumentFragment() 一次性向DOM文档中添加1000个节点
```javascript
var frag = document.createDocumentFragment();
for(var i=0;i<1000;i++){
    var el=document.createElement("p");
    el.innerHTML = i;
    frag.appendChild(el);
}
document.body.appendChild(frag);
```
使用createDocumentFragment()在添加1000个新节点的情况下，可使程序的运行速度提高10-30%；

