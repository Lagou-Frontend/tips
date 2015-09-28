# Sublime Text 3
	
## 安装

进入[下载地址](http://www.sublimetext.com/3)选择相应版本下载，正常安装即可。


## 配置
`Sublime Text` -> `Preferences` -> `Settings - User`，推荐一些配置：

*  `"translate_tabs_to_spaces": true` 开启自动将Tab替换为空格
*  `"trim_trailing_white_space_on_save": true` 开启自动删除行末空格
*  `"ensure_newline_at_eof_on_save": true` 开启保存文件时在文件末尾保留一个空行
* `"save_on_focus_lost": true` 开启文件失去焦点立即保存
* `"font_size": 18` 设置字体大小，默认10
* `"highlight_line": true` 开启光标所在行高亮
* `"bold_folder_labels": true` 开启侧边栏文件夹名显示加粗

## 插件
可以到[官网](https://packagecontrol.io/)查找自己喜欢的插件，下面推荐一下插件，欢迎大家编辑补充

* Package Control<br/>
sublime包安装工具，安装方式：
	* `view` -> `show console`
	* 输入下方命令:
		```
		import urllib.request,os; pf = 'Package Control.sublime-package';ipp=sublime.installed_packages_path();urllib.request.install_opener(urllib.request.build_opener( urllib.request.ProxyHandler()) ); open(os.path.join(ipp, pf), 'wb').write(urllib.request.urlopen( 'http://sublime.wbond.net/' + pf.replace(' ','%20')).read())
		```
	* 等待安装完成即可
* All Autocomplete<br />
扩展了sublime只在当前文件进行搜索匹配的自动补全提示，会在所有打开的文件中搜索匹配自动补全提示
* AutoFileName<br />
自动补全提示文件名字
* Clipboard Manager<br />
可以查看剪贴板历史纪录，`Sublime Text` -> `Preferences` -> `Key Bindings - User`，添加以下配置

	```json
	{ "keys": ["super+c"], "command": "clipboard_manager_copy" },
	{ "keys": ["super+x"], "command": "clipboard_manager_cut" },
	{ "keys": ["super+v"], "command": "paste_and_indent" },
	{ "keys": ["super+shift+v"], "command": "clipboard_manager_choose_and_paste" }
	```
查看剪贴板历史纪录快捷键：`cmd` + `shift` + `v` 
* HTML-CSS-JS Prettify<br />
HTML/css/js/json格式化，快捷键：`cmd` ＋ `shift` + `h`
* LESS<br />
less文件代码高亮显示
* Markdown Preview<br />
markdown文件预览查看，编辑略卡，快捷键`cmd` ＋ `shift` + `p`调用命令行窗口后，输入preview查找相关命令
* SideBarEnhancements<br />
侧边栏增强工具，强烈建议安装，为侧边栏右键菜单增加剪贴，复制，粘贴，浏览器中打开等选项
* Terminal<br />
终端快捷启动插件，快捷键：`cmd` ＋ `shift` + `t`，会在终端直接cd到当前文件的父文件夹


### [回导航页](../README.md)



