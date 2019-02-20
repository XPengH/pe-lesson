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
>* 

