[TOC]

# pull Request

拉去请求可以在这上面发送合并代码，并且可以针对代码的内容进行评论，@用户能让对面收到信息，@团队，能让团队的所有团队收到信息。

还能在此讨论还能查看拉取请求和合并请求。

# 开发环境网站

[Git for Windows](https://gitforwindows.org/)

## 组件

全部默认的即可

## 环境变量

这里建议用git bash环境

## 初始变量

+ 设置用户名和邮箱地址

首先来设置使用 Git 时的姓名和邮箱地址，名字请用英文输入。

```
 git config --global user.name "Firstname Lastname"
 git config --global user.email "your_email@example.com"
```

这个命令，会在“~/.gitconfig”中以如下形式输出设置文件。

```
[user]
 name = Firstname Lastname
 email = your_email@example.com
```

## 提高命令输出的可读性

顺便一提，将 color.ui 设置为 auto 可以让命令的输出拥有更高的可读性。 

```
git config --global color.ui auto
```

“~/.gitconfig”中会增加下面一行。

```
[color]
 ui = auto
```

这样一来，各种命令的输出就会变得更容易分辨

## 仓库初始化

如果在本地需要创建一个工作树的话，需要相对该目录进行git初始化，**指令如下：**

```
git inist
```

**注意：** ==前提是在github上先创建好仓库，在开始以上操作。==

初始化好仓库让该工作目录绑定指定仓库。

```
git remote add 用户名 仓库地址
```

绑定好了仓库再创建上游分支

```
 git push --set-upstream 用户名 master 
```

**注意：** 第一次使用必须先提交一个文件才能执行以上两个操作。

```
git add 文件名//添加文件到缓冲区
git commit -m "提交"//提交的代码描述
git push //提交至远程仓库
```

+ git commit
  
  如果描述的内容较多的话，就不用加-m选项直接提交然后会让你填写，第一行是描述的大概主题。
  
  第三行详细提交内容，**注意：#的是注释一定要去掉第三行的注释再写否则提交的时候会被注释掉**

+ git commit -amend——修改提交信息
  
  要修改上一条提交信息，可以使用 git commit --amend命令。

# 查看本地目录的状态 git status

status命令于查看本地目录是否有没提交至远程仓库的东西。

# git log——查看提 交日志

git log用于查看所有提交过的日志信息，里面主要包含提交信息还有一个重要的哈希值，这个是用于回溯的。

## 只显示最近一次提交的日志

`git log --pretty=short`

## 显示指定目录或文件的日志

`git log 文件名或目录`

## 显示文件的改动

`git log -p`显示文件的改动

也可以指定查看某个文件的改动

`git log -p README.md`

## git log --graph——以图表的形式查看分支

用`git log --graph`命令查看的话，能清楚的看到特性分支提交的内容被合并，同时特性分支的创建和合并都能看的一清二楚。

## git reflog查看当前仓库执行过的操作的日志

`git reflog`

# git diff——查看更改前后的差别

`git diff`命令可以查看工作树、暂存区、最新提交之间的差别。

```shell
$ git diff
diff --git a/README.md b/README.md
index e69de29..928f69a 100644
--- a/README.md
+++ b/README.md
@@ -0,0 +1 @@
+git 教程
\ No newline at end of file
```

这里解释一下显示的内容。“+”号标出的是新添加的行，被删除的行则用“-”号标出。我们可以看到，这次只添加了一行。

用 git add命令将 README.md 文件加入暂存区。

`git add README.md`

如果暂存区和工作目录没有区别那么使用`git diff`就什么都不会显示

**养成一个好习惯每次提交都查看一下最近一次提交的区别**      `git diff head`

# 分支合并

## 显示分支

`git branch`命令可以将分支名列表显示，同时可以确认当前所在分支。

## 分支创建&切换

### 分支创建

如果想以当前的 master 分支为基础创建新的分支，我们需要用到`git checkout -b 分支名`命令，这类分支我们称为培育分支。

实际上，连续执行下面两条命令也能收到同样效果。

```shell
$ git branch feature-A
$ git checkout feature-A
```

### 分支切换

`git checkout 分支名`执行吃命令即可切换

## 特性分支

特性分支顾名思义，是集中实现单一特性（主题），除此之外不进行任何作业的分支。在日常开发中，往往会创建数个特性分支，同时在此之外再保留一个随时可以发布软件的稳定分支。

稳定分的角色通常由 master 分支担当

之前我们创建了 feature-A 分支，这一分支主要实现 feature-A，除feature-A 的实现之外不进行任何作业。即便在开发过程中发现了 BUG，也需要再创建新的分支，在新分支中进行修正。

## 主干分支

一般都是用master分支作为主干分支，主干分支通常是由全部特性分支组成的，也就是正式发布的程序是主干分支。

有时我们需要让这个主干分支总是配置在正式环境中，有时又需要用标签 Tag 等创建版本信息，同时管理多个版本发布。拥多个版本发布时，主干分支也有多个。

## 合并分支

合并分支前需要回到主干分支，再执行`git merge --no-ff 分支名`

提交合并的时候会让你填写提交信息，这个时候不用填直接保存退出，因为合并过来的信息已经有无需要其它操作。

# 回溯历史版本——git reset

要让仓库的 HEAD、暂存区、当前工作树回溯到指定状态，需要用到 git rest --hard命令。只要提供目标时间点的哈希值 A，就可以完全恢复至该时间点的状态。

`git reset --hard 回溯的哈希值`

在日志中，我们可以看到 commit、checkout、reset、merge 等 Git 命令的执行记录。只要不进行 Git 的 GC（Garbage Collection，垃圾回收），就可以通过日志随意调取近期的历史状态，就像给时间机器指定一个时间点，在过去未来中自由穿梭一般。即便开发者错误执行了 Git 操作，基本也都可以利用 git reflog命令恢复到原先的状态，所以请各位读者务必牢记本部分

## git rebase -i——压缩历史

在合并特性分支之前，如果发现已提交的内容中有些许拼写错误等，不妨提交一个修改，然后将这个修改包含到前一个提交之中，压缩成一个历史记录。这是个会经常用到的技巧，让我们来实际操作体会一下。
