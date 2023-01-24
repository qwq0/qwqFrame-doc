# 3 hook

hook object 是一种可以很方便的创建动态内容的方法  
他可以将 javascript 对象上的修改实时同步到 dom 中

```javascript
import {
    NList,
    NTagName,
    createNStyle as style,
    NAttr,
    NEvent,
    NElement,
    createHookObj,
    bindValue,
} from "qwqframe";

const bodyElement = NElement.byElement(document.body);

let dataObj = createHookObj({
    key: "value",
});

bodyElement.addChild(NList.getElement([
    bindValue(dataObj, "key")
]));

setInterval(() => { dataObj.key += "-"; }, 1500);

```
