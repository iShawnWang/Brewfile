# My Brewfile

Make your MacBook ready to use in few minutes  :D


# Usage
1. 安装 [Homebrew](https://brew.sh/index_zh-cn.html)
2. 安装 [homebrew-file](http://homebrew-file.readthedocs.io/en/latest/installation.html)
3. `cd Brewfile`
4. `brew file install`

---
# 关于此 Repo

# Homebrew 系
> The missing package manager for macOS

##### 1.  [Homebrew](https://brew.sh) 就像 ubuntu 中的 `apt-get` 或者 CentOS 中的 `yum`, 是一个包管理器, 我们可以用命令行安装一些包, 
eg : 

    brew install mongodb

##### 2. [Homebrew-cask](https://caskroom.github.io) : 是 Homebrow 的一个扩展, 可以用命令来安装 OSX 的 App, 这相当于一个平台, 许多 App 的 cask 是由相关的社区维护的, 你也可以贡献一个自己的 cask
eg : 

    brew cask install google-chrome


##### 3. [mas](https://github.com/mas-cli/mas) : Mac App Store command line interface, 它是一个 Mac AppStore 的命令行版

eg : 
    
    $ mas search Xcode
    497799835 Xcode
    ...
    $ mas install 497799835
    

##### 4. [homebrew-bundle](https://github.com/Homebrew/homebrew-bundle) : 这个相当于 npm 的 `package.json` 或者 Cocoapods 的 `Podfile`, 将所有依赖都写入到这个一个 `Brewfile` 中, 然后执行 `brew bundle` 就会安装配置好所有东西


## 所以使用

1. Homebrew 安装所有的基础包 : Nginx MySql
2. Homebrew Cask 安装大部分 App : Chrome, iterm2, WebStorm 
3. mas 安装小部分 AppStore 中的 app
4. Brewfile 来管理这些记录这些包和 App

我们就能实现用一个配置文件几分钟搭建好 MacBook 的基本环境

# 开始环境配置
## [homebrew-file](https://github.com/rcmdnk/homebrew-file) 
**是一个帮助我们管理 `Brewfile` 的非常方便的命令行工具**

它会帮我们创建和管理一个默认的 `Brewfile`, 在 `~/.brewfile/Brewfile`

如果需要备份或者分享 `Brewfile` 的话, `homebrew-file` 也支持 用 Dropbox 和 Github 仓库 管理 `Brewfile` 的功能, 也只需要非常简单的配置, 本仓库就是使用 `homebrew-file` 的 Github 接口管理的

> [使用 Github | Dropbox 管理 Brewfile](http://homebrew-file.readthedocs.io/en/latest/getting_started.html)

然后我们只要使用

     brew file install mongodb
    
替代原来的 

     brew install mongodb

即可,   
此时 mongodb 这个包名就会被记录在默认的 `Brewfile` 上

## brew-wrap
在安装过程中, `homebrew-file` 推荐配置 

将

    if [ -f $(brew --prefix)/etc/brew-wrap ];then
        source $(brew --prefix)/etc/brew-wrap
    fi
    
写入到 `.bashrc 或者 .zshrc` 文件中, (我写入到了 .base_profile 中)
这个配置就像为 `brew file` 起了个别名, 
下次安装使用

    brew install mongodb
    
就等价于

    brew file install mongodb

很方便

> [brew-wrap](http://homebrew-file.readthedocs.io/en/latest/installation.html)

# 关于
本仓库中的 [Brewfile](https://github.com/iShawnWang/Brewfile/blob/master/Brewfile) 是我自己的配置文件, 供参考

