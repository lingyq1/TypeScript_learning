# TypeScript 联合类型和接口

- 联合类型
> 通过管道(|)将变量设置多种类型，赋值时可以根据设置的类型来赋值。
只能赋值至指定的类型，赋其他类型的值会报错。
```js
var x: string|number
x = 'Hello';    // 字符串类型
x = 1;    // 数字类型
x = false;    // 布尔类型 ，会报错
```
> 也可以将联合类型作为函数参数使用：

> 也可以将数组声明为联合类型
```js
var arr:number[]|string[];
var i:number;
arr = [1,2,3];           //  数字数组
for(i = 0 ;i<arr.length;i++>){
   console.log(arr[i])   //  结果为 1，2，3
}
arr= ["A","B","C"]；      // 字符串数组
for(i = 0 ;i<arr.length;i++>){
   console.log(arr[i])   //  结果为 A，B，C
}
```

- 接口
> 是一系列抽象方法的声明，是一些方法特征的集合，这些方法都应该是抽象的，需要由具体的类去实现，然后第三方就可以通过这组抽象方法调用，让具体的类执行具体的方法。
定义的接口不会编译出来，它是TypeScript的一部分。
```js
interface interface_name {  //格式
}
```

- 联合类型和接口
```js
interface RunOptions {
    name: string,
    favouriteFood: string[] | string | (() => string)

}

var options: RunOptions = { name: "Anzo", favouriteFood: "orange" };
console.log(options.favouriteFood);    // orange

options = { name: "A", favouriteFood: ["B", "C"] }
console.log(options.favouriteFood[0]);  // B
console.log(options.favouriteFood[1]);  // C

options = { name: "John", favouriteFood: () => { return "Hello World!" } }
console.log(options.name);              // Hello World!
var functionCall: any = options.favouriteFood;   // 这里必须定义类型，否则函数不能调用。

console.log(functionCall());

```

- 接口和数组
> 接口中可将数组的索引值和元素设置成不同类型，索引值可以是数字或字符串
```js
interface numblist {
    [index: number]: string
}
var list: numblist = ["one", "two", "three"]

interface nameList {
    [index: string]: number
}
var list1: nameList;
list1["jacky"] = 15;    // 正确
list1[2] = "Faith";     //错误，不能将类型"string"分配给类型"number",即索引值应为number类型。
```

- 接口继承
> 接口可以通过其他接口来扩展自己。Typescript 允许接口继承多个接口。
1. 单接口格式:
Child_interface_name extends super_interface_name

```js
interface member {
    name: string
}

interface supplement extends member {
    age: number;
    gender: string;
}
var full = <supplement>{}; //接口的另一种表示方式
full.gender = "male";
full.age = 12;
full.name = "Anzo";
// 或者这样写： var full:supplement ={age:"16",gender:"male"};
console.log(full.gender);  //male
```
编译后:
```js
var full = {}; 
full.gender = "male";
full.age = 12;
full.name = "Anzo";
console.log(full.gender);
```

2. 多接口格式:
Child_interface_name extends super_interface_name1,super_interface_name2,...,super_interface_nameN

```js
interface member1 {
    name: string
}
interface member2 {
    age: number
}
interface childMember extends member1, member2 { }
var mine: childMember = {
    name: "Anzo",
    age: 12
}
console.log(mine.name);  //Anzo
console.log(mine.age);   //12
```