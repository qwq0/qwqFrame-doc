# 2 NList

NList 类 是能帮助你快速构建元素的强力类

## 更优雅的生成元素

HTML 元素 是简单却又复杂的  
他的常用属性有

-   标签名
-   属性
-   样式
-   内部文本
-   内部元素
-   事件

对于 html 语法 可以这样写

```xml
<元素名 属性名="属性值" style="样式名: 样式值">
    内部文本
    <内部元素></内部元素>
</元素名>
```

但是这样的写法 将元素生成和动作脚本分离了  
并不能优雅的获取元素 然后执行操作和绑定事件

那么在原生 js 中动态生成呢?

```javascript
let element = document.createElement("元素名");
element.属性名 = "属性值";
element.style.样式名 = "样式值";
element.innerText = "内部文本";
element.appendChild(document.createElement("内部元素"));
element.addEventListener("事件名", (event) => {});
```

但是好像不太优雅

假设我们可以把上述种种元素的属性 全部塞到一起呢?

```javascript
import {
    NList,
    NTagName,
    createNStyle as style,
    NAttr,
    NEvent,
    NElement,
} from "qwqframe";

const bodyElement = NElement.byElement(document.body);

let element = NList.getElement([
    new NTagName("标签名"),

    "内部文本",

    style("样式名", "样式值"),
    new NAttr("属性名", "属性值"),
    new NEvent("事件名", (event) => {}),

    [
        // 子元素
        new NTagName("子元素"),
    ],
]);
bodyElement.addChild(element);
```

这便是 NList 的方便之处  
仅需将这些属性放进一个数组 NList.getElement 就会用这些属性生成元素  
数组中还能够嵌套多层数组 表示创建子元素

## 这不是 css 的 class 这是 flat NList

css 的 class 可以将样式赋予一组元素   
这样做可以复用很多样式   
NList也可以这样做 并且不止样式 其他NList支持的属性也可以   

```javascript
let flatList = NList.flat([
    style("border", "1px black solid"),
    style("margin", "5px")
]);
```
同样flat NList也只需要塞进NList的数组就会在构建元素时被使用