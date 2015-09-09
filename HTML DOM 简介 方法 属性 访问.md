## HTML DOM 简介
HTML DOM 文档对象模型 （DOM） 定义了访问和操作 HTML 文档的标准。
## HTML DOM 节点
##### 节点
在 HTML DOM 中，所有事物都是节点。DOM 是被视为节点树的 HTML。
##### HTML DOM 节点树
![images](https://github.com/sunshine9/HTML-DOM/blob/master/images/HTML%20DOM_Tree.jpg)
##### 节点父、子和同胞
节点树中的节点彼此拥有层级关系。
父（parent）、子（child）和同胞（sibling）等术语用于描述这些关系。父节点拥有子节点。同级的子节点被称为同胞（兄弟或姐妹）。
## HTML DOM 方法
HTML DOM 对象 - 方法和属性

一些常用的 HTML DOM 方法：

    getElementById(id) - 获取带有指定 id 的节点（元素）
    appendChild(node) - 插入新的子节点（元素）
    removeChild(node) - 删除子节点（元素）

一些常用的 HTML DOM 属性：

    innerHTML - 节点（元素）的文本值
    parentNode - 节点（元素）的父节点
    childNodes - 节点（元素）的子节点
    attributes - 节点（元素）的属性节点
![images](https://github.com/sunshine9/HTML-DOM/blob/master/images/filehelper_1441781746579_39.jpg)
## HTML DOM 属性
属性是节点（HTML 元素）的值，您能够获取或设置。
##### innerHTML 属性
innerHTML 属性对于获取或替换 HTML 元素的内容很有用。
```javascript
var txt=document.getElementById("Intro").innerHTML;
document.write(txt);
```
##### nodeValue 属性

nodeValue 属性规定节点的值。

    元素节点的 nodeValue 是 undefined 或 null
    文本节点的 nodeValue 是文本本身
    属性节点的 nodeValue 是属性值
##### nodeType 属性

nodeType 属性返回节点的类型。nodeType 是只读的。

比较重要的节点类型有：
元素类型 	NodeType
元素 	1
属性 	2
文本 	3
注释 	8
文档 	9
