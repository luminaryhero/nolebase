---
tags:
  - git
status: 已完成
---
# git常用命令

### 配置

```shell
# 设定身份
git config --global user.name "your_name"
git config --global user.email "your_email@example.com"
```

### 初始化

```shell
# 初始化一个新的仓库
git init
# 关联远程仓库
git remote add origin <repository-url>
# 拉取远程分支
git pull

# OR
# 克隆一个远程仓库
git clone <repository-url>
# 拉取远程分支
git pull
```


### 工作流

```shell
# 从远程仓库拉取
git pull
# 添加文件到暂存区
git add .
# 提交更改
git commit -m "Commit message"
# 推送数据到远程分支，如果远程分支不存在则创建同名远程分支
git push -u origin main 
```

### 分支

```shell
# 查看本地所有分支
git branch # -a：远程+本地 -r远程
# 创建一个新分支并切换至新分支
git checkout -b <new-branch-name>
# 合并一个分支到当前分支
git merge <branch-name>
# 出现冲突,修改文件后执行
git add .
# 继续修改合并
git merge  --continue
# 如果不想合并,直接终止
git merge --abort
```

### 撤销&回滚

```shell
# 恢复到最近一次commit
git reset --hard
git clean -df # 强制删除工作区未跟踪文件夹

# 回滚远程代码
git log #查看分支提交历史,确认需要回退的commit
git reset --hard <commit_id> #进行commit回退
git push -f origin main #推送至远程分支
```


### 其它

```shell
# 修改远程仓库地址
git remote set-url origin <repository-url>

# 将未提交的更改从当前分支移动到其他分支
git stash
git checkout branch2
git stash pop
```