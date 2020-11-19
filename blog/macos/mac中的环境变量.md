---
title: Mac中的环境变量
tag: mac
category: mac环境
---

# 引言

​	在安装jdk的时候无脑安装的jdk，居然可以直接的在终端进行编译运行不需要像Windows下重新配置环境变量。因为这个原因我想看看mac的环境变量在哪里是怎么设置的。

# Mac中的环境变量

​	在mac中设置环境变量需要从文件中修改，~~win好像可以直接在设置里面设置~~。

* /etc/profile  
* /etc/paths

这两个文件是系统级别的，在macos启动的时候就会加载。查看这些文件需要显示隐藏文件夹，快捷键``shift+command+.``

*  ~/.bash_profile
*  ~/.bash_login
* ~/.profile

如果说/.bash_profile 存在的话后面的两个文件就不会读取

* ~/.bashrc

在启动bash shell的时候加载，如果你用的是zsh那文件就是/.zshrc

## 查看环境变量

​	一般来说，我们需要修改环境变量就直接修改/etc/paths 就行了，需要在启动bash的时候运行某些脚本文件就可以直接修改/.bashrc，比如给终端设置代理的时候。

​	我们从finder中显示隐藏文件，然后查看etc/path可以看到每一行都有一个PATH，你也可以在终端中输入`` echo $PATH``也可以看到环境变量。

​	然后我们就看看到底是哪个文件夹有有Java相关的指令，然后我们就在/usr/local/bin中找到了java，javac这两个编译java文件和运行.class文件的指令。接着探索你还会发现其他的一些指令，比如说npm，pip，brew之类的，当然前提是安装了这些东西。

​	注意：在编辑paths文件的时候你不能直接修改文件，你必须用一个新的文件替换他，或者是在终端使用vim进行编写。

