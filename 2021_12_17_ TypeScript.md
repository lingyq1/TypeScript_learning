# TypeScript

1. 是 JavaScript 的一个超集
2. TypeScript 设计目标是开发大型应用，它可以编译成纯 JavaScript，编译出来的 JavaScript 可以运行在任何浏览器上。
3. TypeScript 是一种给 JavaScript 添加特性的语言扩展。增加的功能包括：

- 类型批注和编译时类型检查
  > 类型注解是一种轻量级的为函数或变量添加约束的方式
- 类型推断
- 类型擦除
- 接口
- 枚举
- Mixin
- 泛型编程
- 名字空间
- 元组
- await

类型注解

```js
function greeter(person: string) {
  return "Hello, " + person;
}
let user = "Anzo";
document.body.innerHTML = greeter(user);
```

如果把数组：[1,2]赋值给 user，会报错 （类型“number[]”的参数不能赋给类型“string”的参数）。TypeScript 提供了静态的代码分析，它可以分析代码结构和提供的类型注解。

接口

```js
interface Person {
    firstName: string;
    lastName: string;
}

function welcome(person: Person) {
    return "Welcome," + person.firstName + "" + person.lastName;
}
let member = { firstName: "Anzo", lastName: "Ling" };
document.body.innerHTML = welcome(member);
```

类

```js
class Student {
    fullName: string;
    constructor(public firstName, public middleInitial, public lastName) {
        this.fullName = firstName + " " + middleInitial + " " + lastName
    }
}

interface Person {
    firstName: string;
    lastName: string;
}

function welcome(person: Person) {
    return "Welcome," + person.firstName + " " + person.lastName;
}

let member = { firstName: "Anzo", middleInitial: "M.", lastName: "Ling" };

document.body.innerHTML = welcome(member);
```
