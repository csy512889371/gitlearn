# git 总结

# 服务器
* https://github.com
* https://coding.net/

# GIT使用流程
* 提交、checkout
* [workspace] -> **add** -> [local cache] -> commit ->[local repository] -> push ->[remote git repository]
* [remote git repository] -> clone -> [git repository] checkout -> [workspace]

主要步骤:
* 添加add
* 提交commit
* 远程推送push
* 远程克隆clone
* 远程更新pull
* 其他命令: branch、tag 、remote 、checkout、 merge 、log 、status、 fetch 、rebase等

# GIT与svn主要区别
1.基于本地进行完整的版本管理，不强制依赖远程仓库
2.GIT把内容按元素方式存储，而SVN是按文件
3.GIT分支和SVN的分支不同


# GIT常用命令讲解

##安装git客户端
[官方客户端](https://git-scm.com/downloads)
[其他客户端](https://tortoisegit.org/download)

# 项目添加到push过程
* 创建项目
* 初始化git仓库
* 提交文件
* 远程关联

## 脚本

### 提交代码过程

```shell
git config --global user.name 'nick'
git config --global user.email '512889371@qq.com'
git init gitlearn # 初始化项目
git status # 查看状态
git add 1.txt # 添加修改到本地缓存
git add -A # 添加所有到本地缓存
git commit -am '1.txt' # 添加提交到本地仓库
git remote add origin https://github.com/csy512889371/gitlearn.git #添加远程仓库
git remote #查看远程
git push origin master -u

```

### 拉取代码过程

```shell
git clone https://github.com/csy512889371/gitlearn.git #克隆项目
git pull # 拉取代码

```

### 分支管理


```shell

git branch [-v] # 查看当前分支
git branch <branch name># 基于当前分支新建分支
git branch <branch name> <commit id># 基于提交新建分支
git checkout <branch name> #切换分支
git merge <merge target> #合并分支

# 解决冲突，如果因冲突导致自动合并失败，此时status为mergeing状态
# 需要手动修改后重新提交(commit)
```

创建分支
```shell
git branch 
git branch -a 
git branch dev #创建分支dev
git checkout dev #切换到dev分支
git branch -d dev #删除分支
git push origin dev -u #将分支提交到远程服务器

git branch -av
git branch -avv

```


提交代码冲突
```shell
git pull
# 本地合并
git commit -am '重新提交'
git push #提交到服务器
```

如果本地项目和远程都有项目且未做关联
```shell
git branch --set-upstream-to=origin/master master
git pull --allow-unrelated-histories
```

### 标签 tag
```shell
git tag v1.0 #创建标签
git tag #标签状态
git push origin v1.0 -u #提交标签到远程仓库

git tag -d v1.0 #删除标签
git branch v1.0_dev v1.0 #基于标签创建分支
git log #查看日志
```
# 实际开发中版本控制
![image](https://github.com/csyeva/eva/blob/master/img/github/bb1.png)
![image](https://github.com/csyeva/eva/blob/master/img/github/bb2.png)
