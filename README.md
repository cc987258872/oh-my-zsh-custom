# oh-my-zsh-custom

基于 [oh-my-zsh](https://github.com/robbyrussell/oh-my-zsh) 的自定义配置，增加了一些个人常用插件与皮肤。

采用的是 `git submodule` 来维护，包括 `oh-my-zsh`，之所以这么搞，主要是手头有多台 linux 需要维护，
每台机器、每个用户都配置一遍比较麻烦，索性将个人常用的工具都打包在一起，简化一下配置。

这么搞的好处是只需要在 clone 一份，然后在各个用户的 `.zshrc` 下面配置一下 source 指向即可。具体可参加下面的 `安装步骤`。

配置很简单，具体可参加 [oh-my-zsh-custom.sh](oh-my-zsh-custom.sh)

## Requirements

-   zsh
-   git
-   Mac OS X: [Nerd fonts](https://github.com/ryanoasis/nerd-fonts)
-   Linux: none

## 安装步骤

### git clone

> git clone --recursive https://github.com/someok/oh-my-zsh-custom.git

### .zshrc

> source /path/to/oh-my-zsh-custom/oh-my-zsh-custom.sh

## 覆盖变量

可以在根目录下创建 `override.sh`，在其中定义的内容可以覆盖默认配置。

## 目录结构

-   **[oh-my-zsh](https://github.com/robbyrussell/oh-my-zsh)**: 不用多说，基石
-   **custom**: oh-my-zsh 的 custom 目录，在 `oh-my-zsh-custom.sh` 中通过 `ZSH_CUSTOM` 配置
    -   **plugins**
        -   [zsh-syntax-highlighting](https://github.com/zsh-users/zsh-syntax-highlighting)
        -   [zsh-autosuggestions](https://github.com/zsh-users/zsh-autosuggestions)
    -   **themes**
        -   someok-linux.zsh-theme: 基于 [aphrodite-terminal-theme](https://github.com/win0err/aphrodite-terminal-theme) 的简单定制，用于 `Linux` 环境
-   **modules**
    -   [alien](https://github.com/eendroroy/alien): 集成的 theme
    -   [powerlevel9k](https://github.com/bhilburn/powerlevel9k): 集成的 theme
-   **override**: 用于覆盖 `oh-my-zsh-custom.sh` 中的配置
    -   mac.sh: Mac 下可用
    -   linux.sh: Linux 下可用
    -   override.sh: 在 `oh-my-zsh` 实际执行前调用，优先级比 mac.sh、linux.sh 更高
    -   \*.template: 一些模板文件，可基于此复制并去掉后缀
    -   \*.theme.sh: 集成的几个 theme 的个性配置
-   **example**
    -   .zshrc: 示例实现

## plugins 功能概述

-   autojump: 支持 `j` 跳转，需安装 `autojump`
-   extract: 解压命令，可根据扩展名自动执行相应解压命令
-   sudo: 按两次 `ESC` 可在命令前面添加 `sudo`
-   history: 增加几个查看历史的 alias: h, hs, hsi
-   copydir: 输入 `copydir` 可拷贝当前所在路径
-   copybuffer: 按 <kbd>CTRL</kbd>+<kbd>O</kbd> 可拷贝当前输入内容
-   colored-man-pages: 给 man 页面着色
-   zsh_reload: 提供 `src` 命令用于重载 `zsh` 配置
-   zsh-navigation-tools: <kbd>CTRL</kbd>+<kbd>R</kbd> 可打开 history 面板，功能很多很强大
-   zsh-syntax-highlighting: 命令着色
-   zsh-autosuggestions: 自动建议

### Mac OS X 上启用插件

-   brew: 增加几个 brew 的 alias
-   forklift: 增加几个命令用于在 forklift 中打开文件夹
-   npm: npm 的一些 alias
-   sublime: `st` 可打开给定文件，`stt` 可将当前所在文件夹发送到 sublime

## 更新方式

-   git 更新:
    > git fetch && git pull
-   submodule 更新:
    > git submodule update --remote
-   submodule 初始化:
    > git submodule update --init --recursive
