# 工作中遇到的git操作问题

## 生成ssh-key
- `ssh-keygen` 一路回车
- `cat ~/.ssh/id_rsa.pub` 进入到文件，显示ssh-key内容

### 常用命令
- 从远程仓库拉取master分支代码 先clone远程仓库master分支
`git clone 远程仓库地址`
- 拉取到本地之后，修改代码，提交到远程仓库(master)
 >##### 提交步骤
 >>`git add .` (把所有修改的文件提交到暂存区)
 >>`git status` (查看所有修改文件的状态)
 >>`git commit -m '提交的需要描述文字'`(commit 把所有改动文件提交到本地仓库)
 >>`git push` (提交到远程仓库)

-------
### 已有本地仓库远程还有仓库
###### 修改远程本地仓库的远程git源、
- `git remote rm origin` (先删除远程的origin)
- `git remote add origin <...>` (再添加远程仓库地址源) 

### git拉取远程仓库的指定分支代码
- `git clone -b <branch> ...仓库代码地址`

### 合并分支
- `git merge <branch>`

### 查看git提交历史
- `git commit`

### git版本回退
1. 先用git commit查看提交日志
- `git commit` (获取到commit历史)或者 `git log`
2. 回退到指定的commit版本
- `git reset --hard <commit提交的id>`

### git 查看本地分支
- `git branch`

### 查看所有分支
- `git branch -a`

### 创建新的分支
- `git ckeckout -b <branch>`

### 将创建好的本地分支，提交远程仓库
- `git push origin <本地分支>:<远程分支>`

### 删除本地分支
- `git branch -d <branch>`

### 删除远程分支
- `git push origin --delete <branch>`

### 切换分支
- `git checkout <branch>`

### 让本地分支和远程仓库的某个分支关联起来
- `git branch --set-upstream-to=<origin/branch> <local/branch>`
- 事例: `git branch --set-upstream-to=origin/master local`

### git 查看当前分支跟踪的远程分支是哪个
- `git branch -vv`

### git 强制覆盖本地代码
- `git fetch -all && git reset --hard origin/master && git pull`

### git 强制推送本地代码到远程仓库
- `git push -u origin master -f 或 git push -f origin master`







