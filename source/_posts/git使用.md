---
title: git快速上手
categories: 
- git


---


## 什么是git

*Git 是一个开源的分布式版本控制系统，用于敏捷高效地处理任何或小或大的项目。*

<s>用于和小伙伴们一起整个大活</s>

<!--more-->

## git安装配置

安装这个资源太多了，俺也是新手俺就不献丑了

git工作流程

- 克隆 Git 资源作为工作目录。
- 在克隆的资源上添加或修改文件。
- 如果其他人修改了，你可以更新资源。
- 在提交前查看修改。
- 提交修改。
- 在修改完成后，如果发现错误，可以撤回提交并再次修改并提交。

## git创建仓库

使用

```
git init [name]
```

在当前目录下创建一个名为name 的仓库

如果不加name 会以当前目录作为仓库

始化后，会在 newrepo 目录下会出现一个名为 .git 的目录，所有 Git 需要的数据和资源都存放在这个目录中。

如果当前目录下有几个文件想要纳入版本控制，需要先用 git add 命令告诉 Git 开始对这些文件进行跟踪，然后提交：

```
git add 123.c
git add README
git commit -m ”first“ //不加-m参数会打开vim详细编辑ti'jiao说明
```

```
git add * //跟踪全部文件
```

### git clone

```
git clone <repo>
```

克隆一个仓库到本地仓库

## git基本操作

### git remote

远程仓库操作

- `git remote`：列出当前仓库中已配置的远程仓库。
- `git remote add <remote_name> <remote_url>`：添加一个新的远程仓库。指定一个远程仓库的名称和 URL，将其添加到当前仓库中。
- git remote show [remote]  显示某个远程仓库信息

### 提交远程仓库

```
git push <远程主机名> <本地分支名>:<远程分支名> 
```

本地与远程分支相同可以省略冒号

## git 分支管理

创建分支命令：

```
git branch (branchname)
```

切换分支命令:

```
git checkout (branchname)
```

当你切换分支的时候，Git 会用该分支的最后提交的快照替换你的工作目录的内容， 所以多个分支不需要多个目录。

合并分支命令:

```
git merge 
```

列出分支基本命令：

```
git branch
```

## 查看提交历史

git log
