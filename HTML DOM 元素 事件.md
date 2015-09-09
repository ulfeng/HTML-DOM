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
<body onload="checkCookies()">

<script>
function checkCookies()
{
if (navigator.cookieEnabled==true)
	{
	alert("Cookies are enabled")
	}
else
	{
	alert("Cookies are not enabled")
	}
}
</script>
```
##### onchange事件
```javascript
function myFunction()
{
var x=document.getElementById("fname");
x.value=x.value.toUpperCase();
}
```
##### onmouseover和onmouseout事件
```javascript
<div onmouseover="mOver(this)" onmouseout="mOut(this)" style="background-color:#D94A38;width:120px;height:20px;padding:40px;">Mouse Over Me</div>

<script>
function mOver(obj)
{
obj.innerHTML="Thank You"
}

function mOut(obj)
{
obj.innerHTML="Mouse Over Me"
}
</script>
```
##### onmousedown、onmouseup 以及 onclick 事件
```javascript
<div onmousedown="mDown(this)" onmouseup="mUp(this)" style="background-color:#D94A38;width:90px;height:20px;padding:40px;">Click Me</div>

<script>
function mDown(obj)
{
obj.style.backgroundColor="#1ec5e5";
obj.innerHTML="Release Me"
}

function mUp(obj)
{
obj.style.backgroundColor="#D94A38";
obj.innerHTML="Thank You"
}
</script>
```
