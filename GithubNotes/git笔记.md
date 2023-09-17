## git log

图形化查看

```shell
git log --graph --pretty=oneline --abbrev-commit # 查看 Head 指针往后的日志
git reflog # 查看最近的十条日志
```

## git merge

合并分支

```shell
git merge --no-ff -m "merge dev2 done" dev2
#合并分支同时提交一个commit信息
```

## git stash

文件add之后保存到stash区

```shell
git stash list #查看列表
git stash pop #把之前保存的弹出
git stash  # 需要把代码从工作区提交到暂存区才能保存，也就是add之后才能
```

## git 更改别名

```shell
git config --global alias.别名 指令 # --global是全局没有这个就是当前文件
```

## 修改分支名称

```shell
git branch -M 修改的名字 # 本地名字分支
git push -u origin 远程库新名字 # 远程控分支名字
```

## 添加远程库

```shell
git remote add origin 远程库地址 # 增加推送的远程哭名字 origin是远程库别名
```

##  添加标签

```shell
git tag 标签名字 commitId # 给某个版本打上标签，建立新标签 
git tag # 查看标签列表
git tag -a 标签名字 -m "message " commitId #给某个版本打上标签同时添加commit信息
git show 标签名字 # 查看标签的commit 信息
git push origin 标签名字 # 标签推送至远程库
git push origin --tags # 推送所有标签
```



## 删除标签

```shell
git tag -d 标签名字 #删除标签
git push origin :标签名字 # 删除远程仓库的标签
```



## 本地分支跟远程分支建立连接

```shell
git branch --set-upstram-to=origin/远程分支名 本地分支名 #如果本地已经有分支请使用这个指令
git checkout -b 分支名 origin/远程分支名 # 新建立一个分支同时给跟远程库的分支建立连接，下次push不需要指定分支，前提是远程库有这个分支，没有的话不能进行次操作 
```



