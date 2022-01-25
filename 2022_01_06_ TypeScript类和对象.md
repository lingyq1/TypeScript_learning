## TypeScript 类

#### 访问控制修饰符

> 使用访问控制符来保护对类、变量、方法和构造方法的访问。TypeScript 支持 3 种不同的访问权限。

- public（默认） : 公有，可以在任何地方被访问。
- protected : 受保护，可以被其自身以及其子类访问。
- private : 私有，只能被其定义所在的类访问。

```js
class member {
    public name: string;
    private gender: string = "male";
    protected age: number = 6;
}

var obj = new member();
console.log(obj.name);  
console.log(obj.gender); //属性“gender”为私有属性，只能在类“member”中访问
console.log(obj.age);  //属性“age”受保护，只能在类“member”及其子类中访问。
```
#### 类和接口

> 类可以实现接口，使用关键字 implements，并将接口中的字段（例如下例的“name”字段）作为类的属性使用。

```js
interface mem {
    name: string
}
class member implements mem {
    name: string;
    age: number;

    constructor(name: string, age: number) {
        this.name = name;
        this.age = age;
    }
}

var obj = new member("banana", 6);
console.log(obj.name); // banana
console.log(obj.age);  // 6
```

## typeScript 对象
> 对象是包含一组键值对的实例。 值可以是标量、函数、数组、对象等

```js
var obj = {
    name: "Anzo",
    func: function () { } //类型模板
}
obj.func = function () {
    console.log("Hi " + obj.name);
}
obj.func();      // Hi Anzo
```

#### 对象也可以作为一个参数传递给函数

```js
var obj1 = {
    name: "Sunny"
}
var func = function (obj: { name: string }) {
    console.log("Hi " + obj.name);
}

func(obj1);      // Hi Sunny
```