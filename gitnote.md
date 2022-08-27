# git 学习笔记
---
## 基础命令
```bash
# 查看 git 版本
git version

# 配置个人信息
git config --global user.name "<username>"
git config --global user.email <mail address>

# 初始化 git 仓库
git init

# 查看 git 状态
git status
git status --short
git status -s

# 将暂存区文件提交到本地仓库
git commit
git commit -m "<提交信息>"

# 查看提交记录
git log
```
---
## git add 命令详解
```bash
# git add 命令将文件添加到暂存区，add 后，git 会追踪文件的变化。
# git add 后的文件如果没有 commit，该文件被修改后需要再次 git add。
# 因为暂存区存储的是 add 后的文件快照和这些快照的索引文件。
# 所以第二次 git add 后，修改后的文件快照和索引文件会覆盖修改前的文件。
```
---
## git status -s 输出标记详解 []
- ' ' = unmodified [ 未修改 ]
- M = modified [ 已修改 ]
- T = file type changed [ 文件类型已更改 ]
- A = added
- D = deleted
- R = renamed
- C = copied (if config option status.renames is set to "copies")
- U = updated but unmerged
```
X          Y     Meaning
-------------------------------------------------
         [AMD]   not updated
M        [ MTD]  updated in index
T        [ MTD]  type changed in index
A        [ MTD]  added to index
D                deleted from index
R        [ MTD]  renamed in index
C        [ MTD]  copied in index
[MTARC]          index and work tree matches
[ MTARC]    M    work tree changed since index
[ MTARC]    T    type changed in work tree since index
[ MTARC]    D    deleted in work tree
            R    renamed in work tree
            C    copied in work tree
-------------------------------------------------
D           D    unmerged, both deleted
A           U    unmerged, added by us
U           D    unmerged, deleted by them
U           A    unmerged, added by them
D           U    unmerged, deleted by us
A           A    unmerged, both added
U           U    unmerged, both modified
-------------------------------------------------
?           ?    untracked
!           !    ignored
-------------------------------------------------
```
---
## tips
- git log 退出方法: 按下Q键
- 修改默认git编辑器:  git config --global core.editor "vim"
- git ignore 用法: [Git ignore](https://github.com/onlynight/ReadmeDemo/tree/master/Readmes/GitIgnore)