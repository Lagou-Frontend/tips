# NVM(node version manager - node及io版本管理工具)

> 分为npm安装和独立安装

## [github官网]( https://github.com/creationix/nvm)

	https://github.com/creationix/nvm

## 安装及配置

* 运行

	```curl https://raw.githubusercontent.com/creationix/nvm/v0.24.0/install.sh | bash```

* 在 `~/.zshrc` 下 添加 `source ~/.nvm/nvm.sh`
* 安装node  `nvm install v0.10`
* 测试node是否安装成功 `node -v`
* 设置nvm默认node版本 `nvm alias default stable`