# Git 备忘录

### 1. 创建新仓库

```powershell
$ git init
```

### 2. 添加文件到缓存区

- #### 添加单个文件

```powershell
$ git add <filename>
```

- #### 添加全部文件

```powershell
$ git add *
```

### 3. 提交

```powershell
$ git commit -m '本次提交备注信息'
```

### 4. 分支

- 新建一个叫“xxx”的分支并且从当前分支切换过去

```powershell
$ git checkout -b xxx
```

- 切换回主分支

```powershell
$ git checkout master
```

- 删除“xxx”分支

```powershell
$ git branch -d xxx
```

### 5. 把本地改动推送到远端仓库

- 如果本地仓库已经和远端仓库进行了连接（使用过连接命令或者是 Git clone 过了）

```powershell
$ git push origin master
```

- 如果本地仓库还没有克隆远端仓库，但又想和远程服务器进行连接，那么可以使用如下命令：

```powershell
$ git remote add origin git@github.com:zllLeft/learngit.git
```

### 6. 更新与合并

- 把远端仓库的最近的改动更新到本地仓库，执行下面命令用来在本地仓库获取（fetch）并合并（merge）远端的改动：

```powershell
$ git pull
```

- 把其他分支（假设是 xxx）合并到当前分支（假设是 master）

```powershell
$ git merge xxx
```

- 以上两种情况下，git 都会尝试去自动合并改动，遗憾的是，这可能并非每次都成功，并可能出现*冲突（conflicts）*。 这时候就需要你修改这些文件来手动合并这些*冲突（conflicts）*。改完之后，你需要执行如下命令以将它们标记为合并成功：

```powershell
$ git add <filename>
```

- 在合并改动之前，你可以使用如下命令预览差异：

```powershell
$ git diff <source_branch> <target_branch>
```

### 7. 标签

- 一般来说，软件发布的时候都会创建一个标签用来作为该次发布的标识，你可以执行如下命令创建一个叫做 _1.0.0_ 的标签：

```powershell
$ git tag 1.0.0 1b2e1d63ff
```

- _1b2e1d63ff_ 是你想要标记的提交 ID 的前 10 位字符。可以使用下列命令获取提交 ID：(当然，你也可以使用少一点的提交 ID 前几位，只要它的指向具有唯一性。)

```powershell
$ git log
```

### 8. 仓库变更日志

- 如果你想了解本地仓库的历史记录，最简单的命令就是使用:

```powershell
$ git log
```

- 你可以添加一些参数来修改他的输出，从而得到自己想要的结果。 只看某一个人(zllLeft)的提交记录:

```powershell
$ git log --author=zllLeft
```

- 每一条提交记录只占一行的输出:

```powershell
$ git log --pretty=oneline
```

- 或者你想通过 ASCII 艺术的树形结构来展示所有的分支, 每个分支都标示了他的名字和标签:

```powershell
$ git log --graph --oneline --decorate --all
```

- 看看哪些文件发生了改动：

```powershell
$ git log --name-status
```

- 这些只是你可以使用的参数中很小的一部分,更多信息，参考：

```powershell
$ git log --help
```

### 9. 替换本地改动：

- 假如你操作失误，你可以使用如下命令替换掉本地改动：

```powershell
$ git checkout -- <filename>
```

- 上述命令会使用 HEAD 中的最新内容替换掉你的工作目录中的文件。已添加到暂存区的改动以及新文件都不会受到影响。
- 假如你想丢弃你在本地的所有改动与提交，可以到服务器上获取最新的版本历史，并将你本地主分支指向它：

```powershell
$ git fetch origin
$ git fetch origin
```

### 10. 实用小贴士：

- 内建的图形化 git：

```powershell
gitk
```

- 彩色的 git 输出：

```powershell
git config color.ui true
```

- 显示历史记录时，每个提交的信息只显示一行：

```powershell
$ git config format.pretty oneline
```

- 交互式添加文件到暂存区：

```powershell
$ git add -i
```

### 11. Git 客户端

- GitHub desktop [https://desktop.github.com/]()

- Source Tree https://www.sourcetreeapp.com/

### 12. Git 学习资源

- ##### learn by reading :

  Git 简明指南： http://rogerdudler.github.io/git-guide/index.zh.html

  图解 Git： http://marklodato.github.io/visual-git-guide/index-zh-cn.html

  Pro git： https://git-scm.com/book/en/v2

  Pro git 中文版： https://progit.bootcss.com/

  Cheat Sheets: https://services.github.com/on-demand/downloads/zh_CN/github-git-cheat-sheet/

  廖雪峰 git 教程： https://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000

  猴子都能懂得 git 入门： https://backlog.com/git-tutorial/cn/

  阮一峰 git 常用命令： http://www.ruanyifeng.com/blog/2015/12/git-cheat-sheet.html

* ##### learn by doing:

  学习 git 分支: https://progit.bootcss.com/

  Visualizing Git: http://git-school.github.io/visualizing-git/

  Git it: https://github.com/jlord/git-it-electron#what-to-install

### 13. Google 图片学 git

![image-20181106174836885](/var/folders/t1/ggft1jj54b73305_j9rmbcq00000gn/T/abnerworks.Typora/image-20181106174836885.png)
