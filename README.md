[![xterm](https://img.shields.io/badge/local-xterm-blue.svg)](https://xtermjs.org/)
[![typescript](https://img.shields.io/badge/language-typescript-blue.svg)](https://www.tslang.cn/index.html)
![](https://img.shields.io/badge/license-MIT-000000.svg)

# Local Terminal

> 为 xterm 打造本地终端模拟功能

由于直接使用 xterm 模拟本地终端十分困难，官方 demo 也很简单，不能满足复杂需求。

所以，该项目希望提供一套常用的终端操作，帮助快速模拟本地终端。

## 特性

* 基于 Xterm 4.x
* 支持 TypeScript
* 多行输入
* 历史命令记录

## 安装

### 用户

``` shell
$ npm install local-terminal
```

### 开发者
``` sh
$ # cd to git repo
$ cd /path/to/local-terminal
$ yarn && yarn storybook
```

安装完成之后参考 [demo](https://github.com/KayneWang/local-terminal/blob/master/src/demos/react.stories.js) 使用

## API

### `constructor(term, option)`

* xterm: `Terminal` 实例
* _option_(可选): `IOptions` 配置项

`option` 的默认配置如下：

``` js
{
    historySize: 10
}
```

### `read(prompt, continuationPrompt) -> Promise`

* prompt: 命令行提示符
* _continuationPrompt_(可选): 多行输入时的提示符

读取输入后的单行命令，返回一个 `Promise` 用于处理完成输入后的操作:

``` js
const local = new localTerminal(xterm)
local.read("~ ")
    .then(input => console.log("command line: " + input))
    .catch(error => console.error("error: " + error))
```

### `print(message)`

输入命令

### `clear()`

清屏
