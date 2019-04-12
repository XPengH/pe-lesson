>* less 定义全局变量
>
>``` less
>@mDesginWidth: 3.75vw;
>@mDesginHeight: 6.09vh;
>```
>
>* 变量解构赋值的一些常见用法
>
>  1. 交换变量的值
>
>     ``` js
>     let x = 1;
>     let y = 2;
>     [x, y] = [y, x];
>     ```
>
>  2. 从函数返回多个值
>
>     ``` js
>     // 返回一个数组
>     function example() {
>       return [1, 2, 3];
>     }
>     let [a, b, c] = example();
>     
>     // 返回一个对象
>     function example() {
>       return {
>         foo: 1,
>         bar: 2
>       };
>     }
>     let { foo, bar } = example();
>     ```
>
>  3. 函数参数的定义
>
>     ``` js
>     // 参数是一组有次序的值
>     function f([x, y, z]) { ... }
>     f([1, 2, 3]);
>     
>     // 参数是一组无次序的值
>     function f({x, y, z}) { ... }
>     f({z: 3, y: 2, x: 1});
>     ```
>
>  4. 提取JSON数据
>
>     ``` js
>     let jsonData = {
>       id: 42,
>       status: "OK",
>       data: [867, 5309]
>     };
>     
>     let { id, status, data: number } = jsonData;
>     console.log(id, status, number);
>     ```
>
>  5. 设置参数默认值
>
>     ``` js
>     jQuery.ajax = function (url, {
>       async = true,
>       beforeSend = function () {},
>       cache = true,
>       complete = function () {},
>       crossDomain = false,
>       global = true,
>       // ... more config
>     } = {}) {
>       // ... do stuff
>     };
>     ```
>
>  6. 遍历map解构
>
>     ``` js
>     const map = new Map();
>     map.set('first', 'hello');
>     map.set('second', 'world');
>     
>     for (let [key, value] of map) {
>       console.log(key + " is " + value);
>     }
>     // 只获取键名
>     for (let [key] of map) {
>       // ...
>     }
>     // 只获取键值
>     for (let [,value] of map) {
>       // ...
>     }
>     ```
>
>  7. 输入模块的指定方法
>
>     ``` js
>     const { SourceMapConsumer, SourceNode } = require("source-map");
>     ```
>
>* 字符串相关
>
>  1. includes(),startsWith(),endsWith()
>
>     - **includes()**：返回布尔值，表示是否找到了参数字符串。
>
>     - **startsWith()**：返回布尔值，表示参数字符串是否在原字符串的头部。
>
>     - **endsWith()**：返回布尔值，表示参数字符串是否在原字符串的尾部。
>
>       ``` js
>       let s = 'Hello world!';
>       s.startsWith('Hello') // true
>       s.endsWith('!') // true
>       s.includes('o') // true
>       
>       let s = 'Hello world!';
>       s.startsWith('world', 6) // true
>       s.endsWith('Hello', 5) // true
>       s.includes('Hello', 6) // false
>       ```
>
>  2. repeat()
>
>  3. 
>
>* 对象相关
>
>  1. Object.defineProperty()
>
>     > ```js
>     > 
>     > Object.defineProperty(obj, prop, descriptor);
>     > // obj：必需。目标对象 
>     > // prop：必需。需定义或修改的属性的名字
>     > // descriptor：必需。目标属性所拥有的特性,具体属性如下
>     > {
>     >     configurable: true | false, //目标属性是否可以被删除或是否可以再次修改特性
>     >     enumerable: true | false, //目标属性是否可以被枚举。true | false
>     >     value: 任意类型的值, //设置属性的值
>     >     writable: true | false, //值是否可以重写。true | false
>     >     get:function (){
>     >         //当获取值的时候触发的函数
>     >         return initValue;    
>     >     },
>     >     set:function (value){
>     >         //当设置值的时候触发的函数,设置的新值通过参数value拿到
>     >         initValue = value;
>     >     }
>     > }
>     > // 注意：当使用了getter或setter方法，不允许使用writable和value这两个属性
>     > ```
>
>  2. 
>
>* 数组相关
>
>  1. 扩展运算符的用法
>
>     ```js
>     // 复制数组
>     // 方法1
>     const a1 = [1, 2];
>     const a2 = a1.concat();
>     a2[0] = 2;
>     a1 // [1, 2]
>     // 方法2
>     const a1 = [1,2];
>     const a2 = [...a1];
>     // 方法3
>     const [...a2] = a1;
>     
>     ```
>
>  2. 浅拷贝和深拷贝
>
>     ``` js
>     // 浅拷贝
>     // 方式1
>     let a = [1, 2];
>     let b = a;
>     // 方式2
>     Object.assign({}, { a: { b :1} });
>     // 方式3
>     [].concat(arr1, arr2);
>     // 方式4
>     [...arr1, ...arr2, ...arr3]
>     
>     // 深拷贝
>     // 方式1
>     Object.assign({}, { a: 1 });
>     // 方式2
>     JSON.parse(JSON.stringfy(obj))
>     // 方式3 
>     var _ = require('lodash');
>     let obj = _.cloneDeep(obj1);
>     // 方式4
>     var $ = require('jquery');
>     var obj = $.extend(true, {}, obj)
>     
>     ```
>
>  3. 对空位的处理
>
>     ``` js
>     // es5
>     // forEach方法
>     [,'a'].forEach((x,i) => console.log(i)); // 1
>     
>     // filter方法
>     ['a',,'b'].filter(x => true) // ['a','b']
>     
>     // every方法
>     [,'a'].every(x => x==='a') // true
>     
>     // reduce方法
>     [1,,2].reduce((x,y) => x+y) // 3
>     
>     // some方法
>     [,'a'].some(x => x !== 'a') // false
>     
>     // map方法
>     [,'a'].map(x => 1) // [,1]
>     
>     // join方法
>     [,'a',undefined,null].join('#') // "#a##"
>     
>     // toString方法
>     [,'a',undefined,null].toString() // ",a,,"
>     
>     // es6
>     Array.from(['a',,'b'])
>     // [ "a", undefined, "b" ]
>     [...['a',,'b']]
>     // [ "a", undefined, "b" ]
>     [,'a','b',,].copyWithin(2,0) 
>     // [,"a",,"a"]
>     new Array(3).fill('a') 
>     // ["a","a","a"]
>     let arr = [, ,];
>     for (let i of arr) {
>       console.log(1);
>     }
>     // 1
>     // 1
>     // entries()
>     [...[,'a'].entries()] // [[0,undefined], [1,"a"]]
>     
>     // keys()
>     [...[,'a'].keys()] // [0,1]
>     
>     // values()
>     [...[,'a'].values()] // [undefined,"a"]
>     
>     // find()
>     [,'a'].find(x => true) // undefined
>     
>     // findIndex()
>     [,'a'].findIndex(x => true) // 0
>     ```
>
>  4. 
>
>* 闭包
>
>* this指针
>
>  1. 直接函数调用，this指向window对象
>
>     ``` js
>     var name='pepe'
>     function sayName(name){
>         console.log(this.name);
>     }
>     sayName(); // 'pepe'
>     window.sayName(); // window.sayName() 等同于 sayName()
>     console.log(this.name, window.name); // 'pepe', 'pepe'
>     ```
>
>  2. 对象函数调用，this指向调用函数的对象本身
>
>     ``` js
>     var name='pepe';
>     function sayName(){
>         console.log(this.name);
>     }
>     var obj={'name':'pepepeng'};
>     obj.sayName=sayName; // 如果这里 obj.sayName = sayName(); 那么obj.sayName 为undefined
>     obj.sayName(); // pepepeng
>     sayName(); // pepe
>     ```
>
>  3. 构造函数调用，this指向新创建的对象
>
>     ```js
>     function fuckObj(name){
>         this.name = name;
>         console.log(this);      
>         console.log(this.name);
>     }
>     var myObj=new fuckObj('pepe');
>     
>     function Dog(name){
>         this.name=name;
>         console.log(this.name);    //输出'泰迪'
>         console.log(this);        //输出：Object { name: "泰迪" }
>     }
>     Dog.prototype.sayName=function sayName(){
>     console.log("my name is "+this.name);
>     }
>     var animal= new Dog("泰迪");
>     animal.sayName();       //输出：'my name is 泰迪'
>     
>     
>     function Cat(){
>         console.log(this);   //输出：Object {  }
>         console.log("cat"); 
>     }
>     function Dog(name){
>         this.name=name;
>         console.log(this.name);
>         console.log(this);    //输出：Object { name: "泰迪" }
>         return new Cat();    //关键代码，在构造函数返回了一个对象
>     }
>     var animal=new Dog("泰迪");   //输出：Object {  }
>     console.log(animal); // {} 最终animal是个空object
>     ```
>
>  4. 间接函数调用，this指向要指向的对象(call(),apply(), bind())
>
>     ``` js
>     // call(this指针要指向的对象，参数1，参数2,.....)
>     function Cat(age,name){
>         this.name='cat';
>         console.log(this);
>         console.log('cat: age:'+age+",name:"+name);
>     }
>     var cat = new Cat(4,'Bob');   //Cat {name: "cat"}和cat: age:4,name:Bob
>     Cat.call(this,3,'Tom');     //this指向了Window和cat: age:3,name:Tom
>     
>     // apply(this指针要指向的对象,参数数组或arguments对象)
>     // apply方法和call方法的作用相同，唯一不同的是call方法要将参数一一传入，而apply方法传入的是数组或者arguments对象。arguments对象包含了函数的所有参数。
>     function Cat(age,name){
>         this.name='cat';
>         console.log(this);
>         console.log('cat: age:'+age+",name:"+name);
>     }
>     var cat=new Cat(4,'Bob');    // Cat {name: "cat"}和cat: age:4,name:Bob
>     Cat.apply(this,[3,'Tom']);   // this指向了Window和cat: age:3,name:Tom
>     function getCat(age,name){
>         Cat.apply(this, arguments);
>     }
>     getCat(5,"kitty");  // this指向了Window和cat: age:5,name:kitty
>     
>     // bind这个方法会创建一个函数的实例，其 this 值会被绑定到传给 bind()函数的值。
>     window.color = "red";
>     var o = { color: "blue" };
>     function sayColor(){ 
>         console.log(this.color);
>     } 
>     var objectSayColor = sayColor.bind(o); 
>     objectSayColor(); // "blue"
>     window.objectSayColor();   // "blue"
>     
>     ```
>
>  5. 
>
>* windows上input 和textarea的字体默认不一致如需统一需要单独设置

