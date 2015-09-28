#IDT
拉勾网前端集成开发环境


* `npm install idt@1.1.16 -g` 需要注意版本号,只能安装1.1.16版本. 高版本会有兼容问题

* `idt install` 安装依赖

* `idt install` 再次运行将提示 `you have installed 'grunt' & 'edp'.`，可验证是否安装完成

* 新安装的idt会自动install最新版本的edp，build时候不会引入依赖的common目录下的组件文件，需要手动更新如下版本：

	> edp@1.0.1 /usr/local/lib/node_modules/edp

	> Builtin Commands:

	>   edp-config (1.0.2)

	>   edp-core (1.0.28)

	>   edp-build (1.0.14)

* `idt ws start` 启动服务
* `idt build` 发布资源
* 详细请参考：[idt README](https://github.com/Lagou-Frontend/idt)
