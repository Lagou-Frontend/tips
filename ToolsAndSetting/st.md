# Sublime Text 3 安装配置及插件推荐

> mcdong@lagou.com

## 不得不说...ST已经成为了前端乃至PHP界最好用的轻量级编辑器.
	ONE PEOPLE ONE STYLE的插件安装模式
	
	支持多语言的编译及运行
	
	多重配色方案支持
	
	minimap导航
	
	.....
	
## 安装及配置

### 下载安装

===

* 下载地址
	* `http://www.sublimetext.com/3`
* 正常安装即可

### 配置、安装插件 

===

####必备插件
* package control

用于其他插件的管理控制.

可以到[官网](https://packagecontrol.io/)查看、探索各种sublime插件。

安装步骤如下：（如不成功可以参考[官网安装说明](https://packagecontrol.io/installation)。）

	* 打开软件
	* `view` -> `show console`
	* 输入下方命令:
		
		import urllib.request,os; pf = 'Package Control.sublime-package';ipp=sublime.installed_packages_path();urllib.request.install_opener(urllib.request.build_opener( urllib.request.ProxyHandler()) ); open(os.path.join(ipp, pf), 'wb').write(urllib.request.urlopen( 'http://sublime.wbond.net/' + pf.replace(' ','%20')).read())
	
	* 等待安装完成即可

####其他插件
* 
* 

