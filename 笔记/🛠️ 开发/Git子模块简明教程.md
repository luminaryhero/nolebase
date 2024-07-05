---
tags:
  - git
  - submodule
  - 子模块
status: 已完成
---
# Git子模块简明教程

> 传送门: [https://iphysresearch.github.io/blog/post/programing/git/git_submodule/](https://iphysresearch.github.io/blog/post/programing/git/git_submodule/)

## 添加子模块

添加一个远程仓库项目 `https://github.com/iphysresearch/GWToolkit.git` 子模块到一个已有主仓库项目中。代码形式是 `git submodule add <url> <repo_name>`， 如下面的例子：

```bash
$ git submodule add https://github.com/iphysresearch/GWToolkit.git GWToolkit
```

这时，你会看到一个名为 `GWToolkit` 的文件夹在你的主仓库目录中。

## 更新子模块

更新项目内子模块到最新版本：

```bash
$ git submodule update
```

更新子模块为远程项目的最新版本

```bash
$ git submodule update --remote
```


## `Clone` 包含子模块的项目

对于你的主仓库项目合作者来说，如果只是 `git clone` 去下载主仓库的内容，那么你会发现子模块仓库的文件夹内是空的！

此时，你可以像上面「添加子模块」中说到的使用 `git submodule update --init --recursive` 来递归的初始化并下载子模块仓库的内容。

也可以分初始化和更新子模块两步走的方式来下载子模块仓库的内容：

```bash
$ git submodule init		# 初始化子模块
$ git submodule update	# 更新子模块
```

但是，如果你是第一次使用 `git clone` 下载主仓库的所有项目内容的话，我建议你可以使用如下的代码格式来把主仓库和其中子模块的所有内容，都**一步到位**的下载下来：

```bash
$ git clone --recursive <project url>
```

以后可以在子模块仓库目录下使用 `git pull origin main` 或者 `git push` 等来进行更新与合并等操作。
