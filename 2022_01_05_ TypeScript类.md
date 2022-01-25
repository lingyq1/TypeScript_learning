# TypeScript 类

### 类

> 定义类的关键字为 class，后面紧跟类名，类可以包含以下几个模块（类的数据成员）：

- 字段 − 字段是类里面声明的变量。字段表示对象的有关数据。
- 构造函数 − 类实例化时调用，可以为类的对象分配内存。
- 方法 − 方法为对象要执行的操作。
```js
class member {
    //字段
    name: string;

    constructor(name: string) {
        this.name = name;
    }

    func(): void {
        console.log("My name is" + " " + this.name);
    }
}
//创建一个对象
let me = new member("Anzo"); 
console.log(me.name);    //Anzo
console.log(me.func());  //My name is Anzo
```
### 类继承类

> 也可以将数组声明为联合类型
```js
class member {
    name: string;

    constructor(name: string) {
        this.name = name;
    }

    func(): void {
        console.log("My name is" + " " + this.name);
    }
}

class greet extends member {
    hobby(): void {
        console.log("Welcome to " + this.name + "'s home");
    }
}

let me = new greet("Anzo");
console.log(me.hobby());  // Welcome to Anzo's home
```

#### 继承类的方法重写
类继承后，子类可以对父类的方法重新定义，这个过程称之为方法的重写。
其中 super 关键字是对父类的直接引用，该关键字可以引用父类的属性和方法。
```js
class pa {
    print(): void {
        console.log("父类"); // 父类
    }
}
class kid extends pa {
    print(): void {
        super.print();    //这里调用了父类
        console.log("子类");  // 子类
    }
}
let children = new kid();
children.print();
```

#### 类的关键字 static
> static 关键字用于定义类的数据成员（属性和方法）为静态的，静态成员可以直接通过类名调用。
```js
class staticNumber {
    static num: number;
    static func(): void {
        console.log("I have " + staticNumber.num + " apples!");
    }
}
staticNumber.num = 6;  // 初始化静态变量,因为是静态成员，直接通过类名staticNumber调用
staticNumber.func();  // 调用静态方法  //结果：I have 6 apples!
```

#### instanceof 运算符
> 用于判断对象是否是指定的类型，如果是返回 true，否则返回 false。
```js
class member { }

const obj = new member();

var isMember = obj instanceof member;
console.log("obj 对象是 Person 类实例化来的吗？" + isMember); //obj 对象是 Person 类实例化来的吗？true
```