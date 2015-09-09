# IE和DOM事件模型之间存在哪些主要差别(转载）
在浏览器解析事件的时候，有两种触发方式，一种叫做Bubbling(冒泡)，另外一种叫做Capturing(捕获)。冒泡的方式效果就是当一个DOM元素的某事件例如click事件被fire时，依次它的父元素的click事件也被fire(触发)，一直传递到最顶层的body元素为止。而捕获的触发方式正好相反，当某个元素的click事件被触发时，先从最顶层的body元素click事件被触发开始，一直传递到真正被触发的元素为止。
 <br>
这次我将讨论W3C的标准DOM事件模型和IE独立门户的DOM事件模型到底有多少区别，首先我们可以回想一下目前大多数Js程序员习惯如何绑定事件到DOM元素上，最常见的就是obj.onclick=handler这种方式(更恶劣的是在Html代码的元素标签中直接加上onclick属性，完全没达到视图和动作分开的原则)。我们暂时称这种方式的事件添加为Traditional(传统方式)吧，IE有自己的IE Event Module，而火狐等浏览器则遵循的W3C方式的Event Module，下面看看这三者各自的优缺点在哪里——
 
##### 1、 Traditional Module
传统方式的事件模型即直接在DOM元素上绑定事件处理器，例如—
```javascript
window.onload=function(){…}
obj.onmouseover=function(e){…}
obj.onclick=function(){…}
```
首先这种方式是无论在IE还是Firefox等其他浏览器上都可以成功运行的通用方式。这便是它最大的优势了，而且在Event处理函数内部的this变量无一例外的都只想被绑定的DOM元素，这使得Js程序员可以大大利用this关键字做很多事情。
 <br>
至于它的缺点也很明显，就是传统方式只支持Bubbling，而不支持Capturing，并且一次只能绑定一个事件处理器在DOM元素上，无法实现多Handler绑定。最后就是function参数中的event参数只对非IE浏览器有效果(因为IE浏览器有特制的window.event)。
 
##### 2、 W3C (Firefox.e.g) Event Module
Firefox等浏览器很坚决的遵循W3C标准来制定浏览器事件模型，使用addEventListener和removeEventListener两个函数，看几个例子—
```javascript
window.addEventListener(‘load’,function(){…},false);
document.body.addEventListener(‘keypress’,function{…},false);
obj.addEventListener(‘mouseover’,MV,true);
function MV(){…}
```
 
addEventListener带有三个参数，第一个参数是事件类型，就是我们熟知的那些事件名字去掉前面的’on’，第二个参数是处理函数，可以直接给函数字面量或者函数名，第三个参数是boolean值，表示事件是否支持Capturing。
 <br>
W3C的事件模型优点是Bubbling和Capturing都支持，并且可以在一个DOM元素上绑定多个事件处理器，各自并不会冲突。并且在处理函数内部，this关键字仍然可以使用只想被绑定的DOM元素。另外function参数列表的第一个位置(不管是否显示调用)，都永远是event对象的引用。
 <br>
至于它的缺点，很不幸的就只有在市场份额最大的IE浏览器下不可使用这一点。
 
##### 3、 IE Event Module
IE自己的事件模型跟W3C的类似，但主要是通过attachEvent和detachEvent两个函数来实现的。依旧看几个例子吧—
```javascript
window.attachEvent(‘onload’,function(){…});
document.body.attachEvent(‘onkeypress’,myKeyHandler);
```
可以发现它跟W3C的区别是没有第三个参数，而且第一个表示事件类型的参数也必须把’on’给加上。这种方式的优点就是能绑定多个事件处理函数在同一个DOM元素上。
 <br>
至于它的缺点，为什么如今在实际开发中很少见呢？首先IE浏览器本身只支持Bubbling不支持Capturing；而且在事件处理的function内部this关键字也无法使用，因为this永远都只想window object这个全局对象。要想得到event对象必须通过window.event方式，最后一点，在别的浏览器中，它显然是无法工作的。
 <br>
最后我在推荐两个必须知道的IE和W3C标准的区别用法吧—<br>
1、 当我们需要阻止浏览器某DOM元素的默认行为的时候在W3C下调用e.preventDefault()，而在IE下则通过window.event.returnValue＝false来实现。<br>
2、当我们要阻止事件冒泡的时候，在W3C标准里调用e.stopPropagation()，而在IE下通过设置window.event.cancelBubble=true来实现。<br>


