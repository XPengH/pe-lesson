<!--
 * @Author: your name
 * @Date: 2021-07-04 18:09:37
 * @LastEditTime: 2021-07-04 20:49:07
 * @LastEditors: Please set LastEditors
 * @Description: In User Settings Edit
 * @FilePath: /pe-lesson/微课学习记录/提高代码可靠性.md
-->
# （复合函数）compose函数和pipe函数

## compose函数
- 将需要嵌套执行的函数平铺
- 嵌套执行指的是一个函数的返回值将作为另一个函数的参数
- 实现函数式编程中的pointfree，使我们专注于转换而不是数据（无参数风格）
- 从右往左执行

```js
let add = x => x + 10;
let multiply = y => y * 10;
let compose = function() {
  let args = [].slice.call(arguments);
  return function(x) {
    return args.reduceRight(function(res,cb) {
      return cb(res)
    },x)
  }
}
let calculate = compose(add, muiltiply)
calculate(10)

// es6写法
const compose = (...args)=> (x)=> args.reduceRight((res,cb)=> cb(res), x)
```

## pipe函数

- 与compose函数不同的地方就是数据流方向不同
- reduceRight改为reduce