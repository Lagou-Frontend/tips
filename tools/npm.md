# npm(node package manager - node包管理工具)

安装node时会自动安装npm，可以在[npm官网](https://www.npmjs.com/)上学习用法，查找node模块以及查看模块相关信息。

## 常用命令

以gulp为例：

* `npm init` 创建package.json文件，如果此时node_modules下已经存在模块，文件创建成功后会自动把模块添加到devDependencies属性中
* `npm install gulp` 安装模块
* `npm install gulp --save` 安装模块并将依赖关系添加到dependencies属性中
* `npm install gulp --save-dev` 安装模块并将依赖关系添加到devDependencies属性中
* `npm install gulp@3.9.0` 安装指定版本模块
* `npm install gulp -g` 全局安装模块，可以在shell中直接使用gulp命令
* `npm uninstall gulp` 卸载模块
* `npm update gulp` 更新模块
* `npm dedup` 去除重复依赖，让node_modules下的依赖关系扁平化，只会操作package.json文件中dependencies属性声明的依赖，在使用browserify构建时，非常有用
* `npm root` 查看包安装路径，即node_modules目录，添加参数`-g`可以参看全局包安装路径
* `npm view gulp` 查看模块的相关信息
* `npm adduser` 在npm上注册后，使用该命令登陆
* `npm publish` 发布模块，不允许和已发布的模块同名，每次发布，package.json中的版本号必须更新
* `npm unpublish` 删除已发布的模块
* `npm link gulp` 将本地安装或者开发的模块link到全局，像全局安装的模块一样在任意处执行命令
* `npm unlink gulp` 取消本地模块的全局link
* `npm run test` 可直接在模块的根目录执行package.json文件中scripts属性所声明的命令的别名

## 前端包管理

> npm is for all javascript.

通过browserify可以让npm成为类似bower/duo/spm3的前端包管理工具，browserify是可以让按照CommonJS规范书写的JS模块在浏览器端正常使用的预编译工具。

* 全局安装browserify

	```
	npm install browserify -g 
	```
* 将main.js及其所有依赖打包压缩成bundle.js

	```
	browserify main.js > bundle.js
	``` 
* 在打包压缩过程中在bundle.js内嵌source map，方便调试

	```
	browserify main.js > bundle.js --debug
	``` 
* source map外置，需要额外安装exorcist模块，会在bundle.js同级目录下生成bundle.js.map<br />

	```
	npm install exorcist -g
	browserify main.js --debug | exorcist bundle.js.map > bundle.js
	```
* 实时编译，watchify是基于browserify封装的解决方案，基本支持了browserify的所有功能<br />

	```
	npm install watchify -g
	watchify main.js -o bundle.js
	```
* 按需打包，如将jQuery等基础库/框架打成一个包，其他js模块打成一个包
	
	```
	npm install jquery
	browserify --reuqire jquery > vendor.js
	browserify main.js --exclude jquery > bundle.js
	```
* 对于不支持commonjs规范的模块可以通过browerify-shim来处理，以jquery.colorbox.js为例
	* 安装browserify-shim

	```
    npm install browserify-shim --save-dev	
	```
	
	* package.json中添加如下配置
	
    ```json
    "browser": {
        "jquery.colorbox": "./js/jquery.colorbox.js"
    },
    "browserify": {
        "transform": [ "browserify-shim" ]
    }
    "browserify-shim": {
        "jquery.colorbox": { depends: [ "jquery:jQuery" ] }
    },
    ```
    
    * js中如下使用
    
	```javascript
	var $ = require('jquery');
	require('jquery.colorbox');
	```
* browserify也提供了API，可以方便的在gulp中使用，具体可以查看[Gulp Recipes](https://github.com/gulpjs/gulp/tree/master/docs/recipes)，另外有一份正在翻译中的[browserify handbook](https://github.com/magicdawn/browserify-handbook)，也可以帮助大家尽快了解browserify
	
