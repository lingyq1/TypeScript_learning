## typeScript 
- 对象补充

> 对象是包含一组键值对的实例。不可以直接给定义好的对象添加新的方法，而应该先定义一个函数的类型模板。

```js
var obj = {
  name: "Anzo",
  gender: "male",
};
obj.func = function () {
  console.log("Hi " + obj.name);
};
obj.func(); // 报错
```

这样会报错 -- 类型“{ name: string; gender: string; }”上不存在属性“func”。
所以应该先在对象里定义函数，如下：

```js
var obj = {
  name: "Anzo",
  gender: "male",
  func: function () {}, //类型模板
};
obj.func = function () {
  console.log("Hi " + obj.name);
};
obj.func(); // 正确，输出 Hi Anzo
```

- typeScript 区分大小写
- typeScript 分号是可选的
以下代码是合法的
```js
 console.log("Hello!")
 console.log("Hello!");
```
两个语句在同一行，一定要用分号隔开，否则会报错。
```js
console.log("Hello!");console.log("World!");
```

### typeScript 模块
导入使用关键字：import
导出使用关键字：export
```js  
  // 文件名： SomeInterface.ts
export interface SomeInterface {

}
```

```js
   // 这是另一文件
import  someInterfaceRef = require("./SomeInterface");
```

## 对于 JSX 的书写形式

- 为了便于阅读，一般会把 JSX 拆分为多行。同时，将内容放在括号里面，这样可避免自动插入分号陷阱。

```js
const element = (
    <h1>
      Hi World!
    </h1>
    );

ReactDOM.render(
    element,
    document.getElementById('root')
  );
```

- 因为 JSX 语法上更接近 JavaScript 而不是 HTML，所以 React DOM 使用 camelCase（小驼峰命名）来定义属性的名称，而不使用 HTML 属性名称的命名约定。

## .TSX文件

> TSX 文件是使用 JSX语法编写的 TypeScript ( .TS ) 文件。它包含的代码很可能是单页或移动应用程序的一部分。TSX 文件可以在任何文本编辑器中打开，但应在源代码编辑器中打开。

JSX，也称为 JavaScript XML，是JavaScript编程语言的扩展。允许我们使用类似于HTML模板的语法来描述React的对象树。它只是一个类似xml的扩展，允许我们编写看起来像标记的JavaScript，并从组件中返回它。

使用 TypeScript 编程语言（JavaScript 的一种变体）的开发人员可以在他们的开发项目中使用 JSX 语法。当他们这样做时，他们将正在进行的加载 JSX 的代码保存为 TSX 文件，然后最终将这些文件转换为.JSX (React JavaScript) 或.JS (JavaScript) 文件。