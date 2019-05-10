##  vue自动保存eslint

### 配置环境

``` js
npm i -g eslint-plugin-vue
```



### .eslint.js 文件规则修改

```js
//　添加插件
"plugins": [
    "vue"
]
```

### vscode setting.json文件修改， 先添加eslint和vetur插件

```js
// 添加进你的vscode的 setting.json

"eslint.autoFixOnSave": true,
"eslint.validate": [
    "javascript",{
        "language": "vue",
        "autoFix": true
    },"html",
    "vue"
],

```

