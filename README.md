# npm-脚手架
编写脚手架

* npm init创建一个package.json
* 几个比较重要的字段：name,version,main,bin。
> name是表示包发布的名字；
>
> version是每次发布的时候要修改版本好才能生效（供npm识别），因为每次都要修改，所以建议自动化处理；
>
> main是项目的入口（别人以npm或commonJS方式来使用），
>
> bin npm 的入口文件,没有后缀的一个文件 `（#!/usr/bin/env node）` 这是此文件的标识，并不是注释
>
> <span style="color:'red'"> #! 告诉系统其后路径所指定的程序即是解释此脚本文件的 node 程序。(这句话解释的有误)</span>
>

```
{
    "name": "yjjtest",
    "version": "0.0.1",
    "description": "前端写作开发流程的脚手架",
    "main": "index.js",
    "bin": "bin/init",
}

```
