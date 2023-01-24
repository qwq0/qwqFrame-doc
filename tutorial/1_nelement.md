# 1 NElement

NElement 类 是 qwqframe 控制 HTMLElement 的关键类 也是对其的封装  
一个 NElement 对应一个 HTMLElement  
一个 HTMLElement 也只能对应一个 NElement

你可以通过这两种方法获取 NElement 实例

```javascript
import { NElement, getNElement } from "qwqframe";
let bodyElement = NElement.byElement(document.body); // 获取HTMLElement对应的NElement
let bodyElement_1 = getNElement(document.body); // 上面方法的别名
```

然后你使用 NElement 类的方法代替直接对 HTMLElement 进行操作

- NElement 类的常用方法
  - addChild(NElement 或 HTMLElement)  
    添加子元素
  - addChild(多个 NElement 或 HTMLElement 或数组)  
    添加多个子元素
  - insChild(NElement, pos: number)  
    插入指定元素到索引为指定值的元素前
    若为负数则为从后往前数
  - insChild(NElement, pos: NElement)
    插入指定元素到另一子元素前
  - remove()
    从 dom 树中移除此元素 就像原生 js 一样
  - removeChilds(begin: number, end: number)  
    移除子元素(包括第 begin 个元素 不包括第 end 个元素)
  - setStyle(name: string, value: string)  
    设置 style
  - setStyles(object)  
    设置多个样式 传入的对象中每个键值对对应一个 styleName 和 value
  - addEventListener(eventName, callBack, options)
    添加事件 就像原生 js 一样
  - animate(keyframes, options)
    播放动画 就像原生 js 一样
  - asse(Function)
    将元素通过指定函数处理

此外 可通过 NElement 的 element 属性直接访问到对应的 HTMLElement
