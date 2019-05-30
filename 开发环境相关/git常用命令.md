#### git的几个概念：
工作区：就是当前所看到的整个项目

暂存区：顾名思义，就是暂时存放代码的区域。

版本库：包括本地版本库与远程版本库。

代码提交的过程一般为：新增或修改->通过git add命令将文件添加到暂存区->通过git commit提交版本修改记录(本地版本库)
                  ->通过git push推送本地版本库版本到远程版本库


#### git常用命令：

- 添加所有改动的文件到暂存区
```
git add -A
git add .
```

- 添加指定文件或目录到暂存区
```
git add [file]
git add [path]
```

- 提交版本修改记录
```
git commit
git commit -m "message"
```

- 创建分支
```
git checkout -b [branch]
```

- 切换分支
```
git checkout [branch]
```

- 拉取远程仓库更新的代码，此命令只是把远程仓库代码拉取到本地，并没有把新的代码合并进工作区
```
git fetch
```

- 合并拉取的远程仓库代码
```
git rebase origin master
```
注：origin是一个标签，指向远程仓库，可以用git remote -v命令查看当前的origin。master是本地仓库的一个分支，上面这条命令的意思就是把origin
指向的远程分支代码合并到本地的master分支。

- git rebase合并代码时，如果发生冲突，解决完冲突后通过
```
git add .
git rebase --continue
```
命令继续合并过程，在此后的合并过程中可能还会出现冲突导致合并中断，此时需要重复进行冲突解决直至合并完成。

- 拉取远程仓库代码并合并至本地分支,此命令相当于git fetch和git rebase两条命令的总和，具体区别感兴趣的可以自己google。
```
git pull
```

- git pull合并代码时，如果发生冲突，解决完冲突代码后通过
```
git add .
git commit
```
两条命令继续完成合并

