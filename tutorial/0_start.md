# 0 开始

在开始学习使用 qwqFrame 前 请确保您已经具备以下前置知识:

- javascript 基础
- html 基础
- css 基础
- 基本 dom 操作和其他常见 webapi

## 安装

1. 从 github 的 qwqFrame 仓库下载库的发布版 你将会获得两个文件

   - qwqframe.js // 这是库的核心内容
   - qwqframe.d.ts // 这是库的 ts 类型定义文件 便于 ts 类型判断 帮助编辑器进行提示

2. 从 npm 仓库下载(todo)

## 创建项目

1. 就像是任何其他一般的前端项目一样 你需要创建一个文件夹

2. 然后 从你熟悉的结构开始创建 把 qwqframe 库丢进去

注意: qwqFrame 推荐的项目结构中 html 文件不应包含任何可见元素  
所有内容应当在 js 中动态生成

这是一种(qwq 常用的)推荐的项目结构:

- / 项目根文件夹
  - dist/ 你的项目打包后存放的文件夹
  - lib/ 库
    - qwqframe.js 如上
    - qwqframe.d.ts 如上
  - src/ 源码文件夹
    - main.js  
      然后你就可以从这里开始写 js 代码了
  - test/ 测试文件夹
    - test.html  
      测试文件 浏览器应当访问这个页面  
      这个文件里的 html 里不用写任何有实际显示的元素  
      只需要引用 src 中对应的 js 文件即可

3. 现在 你应该有一个 html 页面 引用了一个 js 文件  
   例如在上述项目结构中 test/test.html 文件中应当包含此内容

```html
<script type="module" src="../src/main.js"></script>
```

4. 跳转到下一节 开始你的 qwqframe 之旅叭
