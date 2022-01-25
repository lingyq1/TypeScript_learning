# TypeScript基础数据类型

- 任意类型
> 关键字 any (声明为 any 的变量可以赋予任意类型的值)
```js
let x: any = 1;    // 数字类型
x = 'Hello';    // 字符串类型
x = false;    // 布尔类型
```
如果不加any注释，也会表示为任意类型
```js
let x =1; //x 可以是任意类型
```

- 字符串类型 
> 关键字 string (反引号（`）来定义多行文本和内嵌表达式)
```js
let fruit:string = "orange";
let word:string = `你好，欢迎${name}的到来！`
```

- 元组
> 无关键字（用来表示已知元素数量和类型的数组，各元素的类型不必相同，对应位置的类型需要相同）
```js
let x: [string, number];
x = ['Hello', 1];    // 运行正常`
x = [1, 'Hello'];    // 报错
```

- void
> 关键字void（用于标识方法返回值的类型，表示该方法没有返回值）
```js
function hello(): void {
    alert("Hello World");
}
```




