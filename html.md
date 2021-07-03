1.script 正常加载，以及defer/async加载的区别

## 普通 script

先来看一个普通的 script 标签。

```js
<script src="a.js"></script>
```

浏览器会做如下处理

- 停止解析 document.
- 请求 a.js
- 执行 a.js 中的脚本
- 继续解析 document

## defer

```js
<script src="d.js" defer></script>
<script src="e.js" defer></script>
```

- 不阻止解析 document， 并行下载 d.js, e.js
- 即使下载完 d.js, e.js 仍继续解析 document
- 按照页面中出现的顺序，在其他同步脚本执行后，`DOMContentLoaded` 事件前 依次执行 d.js, e.js。

## async

```js
<script src="b.js" async></script>
<script src="c.js" async></script>
```

- 不阻止解析 document, 并行下载 b.js, c.js
- 当脚本下载完后立即执行。（两者执行顺序不确定，执行阶段不确定，可能在 `DOMContentLoaded` 事件前或者后 ）

## 其他

- 如果 script 无 src 属性，则 defer, async 会被忽略
- 动态添加的 script 标签隐含 async 属性。

## 结论

- 两者都不会阻止 document 的解析
- defer 会在 DOMContentLoaded 前依次执行 （可以利用这两点哦！）
- async 则是下载完立即执行，不一定是在 DOMContentLoaded 前
- async 因为顺序无关，所以很适合像 Google Analytics 这样的无依赖脚本