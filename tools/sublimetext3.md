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
    import urllib.request,os; pf = 'PackageControl.sublime-package';ipp=sublime.installed_packages_path();urllib.request.install_opener(urllib.request.build_opener( urllib.request.ProxyHandler()) ); open(os.path.join(ipp, pf),'wb').write(urllib.request.urlopen( 'http://sublime.wbond.net/' + pf.replace(' ','%20')).read())
    ```
    * 等待安装完成即可

* All Autocomplete<br />
扩展了sublime只在当前文件进行搜索匹配的自动补全提示，会在所有打开的文件中搜索匹配自动补全提示

* AutoFileName<br />
自动补全提示文件名字

* Babel<br />
es6语法高亮插件，具体设置参考[这里](https://github.com/babel/babel-sublime)，可配合[Oceanic Next Color Scheme](https://github.com/voronianski/oceanic-next-color-scheme)主题。

* Bufferscroll<br />
保存折叠行

* Clipboard Manager<br />
可以查看剪贴板历史纪录，`Sublime Text` -> `Preferences` -> `Key Bindings - User`，添加以下配置

    ```json
    { "keys": ["super+c"], "command": "clipboard_manager_copy" },
    { "keys": ["super+x"], "command": "clipboard_manager_cut" },
    { "keys": ["super+v"], "command": "paste_and_indent" },
    { "keys": ["super+shift+v"], "command": "clipboard_manager_choose_and_paste" }
    ```
查看剪贴板历史纪录快捷键：`cmd` + `shift` + `v`

* CSS3<br />
更好的CSS3语法高亮支持。

* CSScomb<br />
格式化css样式；选中css样式右键选中csscomb即可，还能在usersetting中自定义css格式化规则！

* compare side-by-side <br />
文件对比，打开要对比的文件，在title处单击右键选择对比即可

* DocBlockr<br />
像java等语言的块注释，使用方法，`/**`Tab就ok

* Emmet<br />
Sublime Zen Coding插件，建议安装，可以用来快速编写html/css，[具体用法](http://www.w3cplus.com/tools/emmet-cheat-sheet.html)。

* javascript completion<br />
javascript api自动补全插件，它相比SublimeCodeIntel的优势是
    1. 轻量，只是用来补全javascript api
    2. 支持es5语法
    3. 有参数提示
    4. 自动纠错

* Java​Script & Node​JS Snippets<br />
js代码片段，快捷输入请参考[这里](https://packagecontrol.io/packages/JavaScript%20%26%20NodeJS%20Snippets)。

* HTML-CSS-JS Prettify<br />
HTML/css/js/json格式化，快捷键：`cmd` ＋ `shift` + `h`

* LESS<br />
less文件代码高亮显示

* Markdown Extend<br />
markdown文件高亮扩展，文件中的代码块也会相应高亮。

* Markdown Preview<br />
markdown文件预览查看，编辑略卡，快捷键`cmd` ＋ `shift` + `p`调用命令行窗口后，输入preview查找相关命令

* Nodejs<br />
Nodejs API 自动补全

* SideBarEnhancements<br />
侧边栏增强工具，建议安装，为侧边栏右键菜单增加剪贴，复制，粘贴，浏览器中打开等选项

* SublimeLinter<br />
Sublime代码检查工具。

* SublimeLinter-eslint<br />
SublimeLinter的ESLint插件，javascript代码质量检查工具对比可以参考[这里](http://efe.baidu.com/blog/js-lints/)，如何使用这个插件可以参考[这里](http://jonathancreamer.com/setup-eslint-with-es6-in-sublime-text/?utm_source=tuicool&utm_medium=referral)，ESLint的Rules可以查阅[官网](http://eslint.org/docs/rules/)。

* Terminal<br />
终端快捷启动插件，快捷键：`cmd` ＋ `shift` + `t`，会在终端直接cd到当前文件的父文件夹

## 主题
可以到[colorsublime](http://www.colorsublime.com/)里查找自己喜欢的主题。下面推荐一些有特色的主题：

* [Oceanic Next Color Scheme](https://github.com/voronianski/oceanic-next-color-scheme)<br />
支持es6/react语法高亮，需要先安装[babel-sublime](https://github.com/babel/babel-sublime)语法高亮插件。

* [Material Theme for Sublime Text 3](https://github.com/equinusocio/material-theme)<br />
Google Material风格主题，同时支持Oceanic Next Color Scheme color theme，不同文件类型会有相应的精美icon。

* [Spacegray](https://github.com/kkga/spacegray)<br />
简约扁平配色看起来很舒服的主题。

## 在sublime中运行js
我们可以在浏览器的console里运行js，也可以在node的REPL里运行js，但是都不是很方便，其实在sublime里也是可以直接运行js的，能够很方便的帮助我们测试javascript api以及验证正则。<br />
下面介绍三种在sublime里运行js的方法

#### JSC
JSC为Mac内置的javascript控制台程序。

1. Tools > Build System > New Build System
2. 在打开的文件中添加如下代码

    ``` javascript
    {
        "cmd": ["/System/Library/Frameworks/JavaScriptCore.framework/Versions/A/Resources/jsc", "$file"],
        "selector": "source.js"
    }
    ```
3. 保存为`JSC.sublime-build`
4. Tools > Build System，选择刚才创建的`JSC`
5. 打开js文件，`cmd` + `b`<br />
![](http://netsh.qiniudn.com/wp-content/uploads/2014/07/sublime-javascript-console-500x297.png
)

注意用`debug()`替换`console.log()`，可支持到es5。

#### Node
首先确保已安装node

1. Tools > Build System > New Build System
2. 在打开的文件中添加如下代码

    ``` javascript
    {
        "path": "/Users/wangjinliang/.nvm/versions/node/v4.2.3/bin",
        "working_dir": "${project_path:${folder}}",
        "selector": "source.js",
        "encoding": "utf-8",
        "shell": true,
        "windows": {
            "cmd": ["taskkill /f /im node.exe >nul 2>nul & node $file"]
        },
        "osx": {
            "cmd": ["killall node >/dev/null 2>&1; node $file"]
        },
        "linux": {
            "cmd": ["killall node >/dev/null 2>&1; node $file"]
        }
    }
    ```
3. 通过`which node`获取node的安装目录，添加到对应的path属性上
4. 保存为`node.sublime-build`
5. Tools > Build System，选择刚才创建的`node`
6. 打开js文件，`cmd` + `b`

对es6的支持情况视node版本而定。

#### Babal 5.x
首先确保已安装node，

1. `npm install babel@5.x -g`全局安装babel命令行模块
2. Tools > Build System > New Build System
3. 在打开的文件中添加如下代码

    ``` javascript
    {
        "path": "/Users/wangjinliang/.nvm/versions/node/v4.2.3/bin",
        "working_dir": "${project_path:${folder}}",
        "selector": "source.js",
        "encoding": "utf-8",
        "shell": true,
        "windows": {
            "cmd": ["taskkill /f /im node.exe >nul 2>nul & babel-node $file"]
        },
        "osx": {
            "cmd": ["killall node >/dev/null 2>&1; babel-node $file"]
        },
        "linux": {
            "cmd": ["killall node >/dev/null 2>&1; babel-node $file"]
        }
    }
    ```
4. 通过`which node`获取node的安装目录，添加到对应的path属性上
5. 保存为`babel.sublime-build`
6. Tools > Build System，选择刚才创建的`babel`
7. 打开js文件，`cmd` + `b`

全面支持es6，以及部分es7，相比第二种直接通过node运行略慢

#### Babal 6.x
与bable5.x有一些区别，请参考[这里](http://fedvic.com/2015/12/24/es6InSublime/)。

### [回导航页](../README.md)
