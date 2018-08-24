# 编写脚手架

### 参考文档
* https://blog.csdn.net/zhaolandelong/article/details/79782885
* https://www.cnblogs.com/webARM/p/6505683.html
* https://segmentfault.com/a/1190000006190814
* commander 写自己的Nodejs命令  http://blog.fens.me/nodejs-commander/  https://github.com/tj/commander.js/
* eaa.js  跟 koa.js https://eggjs.org/zh-cn/intro/egg-and-koa.html
* npm link  使用  https://www.cnblogs.com/CyLee/p/6195022.html

### [ 一些基本概念](https://github.com/yangjingjing1234/node-self-cli)

## 技术选型

* node.js：整个脚手架工具的根本组成部分，推荐使用最新的版本。

* es6：新版本的node.js对于es6的支持度已经非常高，使用es6能够极大地提升开发效率和开发感受。

* commander：TJ大神开发的工具，能够更好地组织和处理命令行的输入。

* co：TJ大神开发的异步流程控制工具，用更舒服的方式写异步代码。

* co-prompt：还是TJ大神的作品……传统的命令行只能单行一次性地输入所有参数和选项，使用这个工具可以自动提供提示信息，并且分步接收用户的输入，体验类似npm init时的一步一步输入参数的过程。


## 指定 CLI入口

```
{
    "name": "yjjtest",
    "version": "0.0.1",
    "description": "前端写作开发流程的脚手架",
    "main": "index.js",
    "bin": "bin/init", // 安装之后执行 yjjtest 即为执行命令
    // 或者以下写法
    "bin":{
        "yjjself":"bin/init",// 给入口命令指定别名 ，安装之后执行  yjjself 即可
    }
}
    
```


* 在根目录下建立\bin文件夹，在里面建立一个无后缀名的init文件。这个bin\init文件是整个脚手架的入口文件，所以我们首先对它进行编写。

```
#!/usr/bin/env node --harmony
'use strict'
 // 定义脚手架的文件路径
process.env.NODE_PATH = __dirname + '/../node_modules/'

const program = require('commander')

let arguments = process.argv.splice(2);

console.log("进入脚手架");
console.log("arguments:", arguments); // 

 // 定义当前版本
program
    .version(require('../package').version )

// 定义使用方法
program
    .usage('<command>')
```

##  commander 简单使用

*
*
*


