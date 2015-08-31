# Lagou-FE TEAM Tips

> 工作学习日常总结

## 列表导航

### 环境/开发工具类
* [Xcode] app store (先装)
* [TotalTerminal](./ToolsAndSetting/TotalTerminal.md)
* [oh-my-zsh](./ToolsAndSetting/oh-my-zsh.md)
* [nvm & node](./ToolsAndSetting/nvm.md)
* [nrm](./ToolsAndSetting/nrm.md)
* [sublime text](./ToolsAndSetting/st.md)
* [eclipse](./ToolsAndSetting/macEclipseSetup.md)

### IDT安装
> 安装以上环境工具后进行IDT的安装

`npm install idt@1.1.16 -g`需要注意版本号,只能安装1.1.16版本. 高版本会有兼容问题

`idt install` 安装依赖

`idt install` 再次运行将提示 `you have installed 'grunt' & 'edp'.` 验证是否安装完成

> 如安装出现问题 使用 ```nrm test``` ```nrm test```来选取速度更快的源 切换源后再次安装即可

> 新安装的idt会自动install最新版本的edp，build时候不会引入依赖的common目录下的组件文件，需要手动更新到低版本，如下：

> edp@1.0.1 /usr/local/lib/node_modules/edp

> Builtin Commands:

>   edp-config (1.0.2)

>   edp-core (1.0.28)

>   edp-build (1.0.14)



### 读书笔记

* JavaScript

* NodeJS

	* [了不起的NodeJS(mcdong)](./readingNotes/the-great-nodejs.md)

* HTTP

* HTML & CSS

### 工具合集

#### MAC

* [百度脑图](http://naotu.baidu.com)

持续更新中 by <mcdong@lagou.com>

[![拉勾网](./img/logo.png "lagou.com")](http://lagou.com)
