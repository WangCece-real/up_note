**常用命令**

```Linux
# 清屏：
clear
# 查看文件列表
ll
ll -la(查看所有文件，包括隐藏文件)
# 删除某个文件
rm Test.txt
# 查看文件内容
cat Test.txt
# 创建文件夹
mkdir deded
# 进入用户主目录
cd ~
```

```Linux
# 查看版本：
git --version
# 设置签名：
# 设置用户名：
git config --global user.name "WangCe"
# 设置邮箱
git config --global user.email "wang_cei@163.com"
# 初始化本地仓库
git init
# 添加文件(提交到暂存区)
git add filename
# 提交文件（提交到本地库）
git commit -m "这是提交的信息"
# 查看工作区和暂存区的状态
git status
# 查看提交的从最近到最远的日志
git log
git log --pretty=oneline
git log --oneline
git reflog (HEAD@数字)
## key:索引(Hash)
## value:历史记录对应的内容
# 历史日志分页
## 下一页空格
## 上一页d
## 结束Q
# 前进或者后退历史版本
git reset --hard 637c87(移动本地库指针，暂存区、工作区都进行重置)
git reset --mixed 637c87(移动本地库指针，重置暂存区，工作区不变)
git reset --soft 637c87(移动本地库指针，暂存区和工作区都不变)
# 找回本地库删除的文件（切换历史版本）
# 找回暂存区删除的文件（切换历史版本）
git reset --hard HEAD
# 比较文件的差异
## 比较工作区和暂存区中的区别(git按照行管理数据)
git diff(比较工作区和暂存区中所有的文件)
git diff Test.txt（比较一个特定的文件）
## 比较暂存区和本地库之间的区别
git diff HEAD Test.txt
git diff ff92656 Test.txt
# 查看分支
git branch -v
# 创建分支(*显示在哪个分支)
git branch new_branch_name
# 切换分支
git checkout new_branch_name
# 合并到主分支
## 进入到主分支
git checkout master
## 将其他分支内容合并过来
git merge new_branch_name
### 出现冲突:同一个文件同一个位置(merge conflict in test.txt)
### 解决冲突，人为操作
### 仍然处于合并中，利用commit解决(All conflict fixed but you are still merging)
git commit (解决冲突不可以带文件名)
# 查看是否存有远程库别名
git remote -v
# 给远程库起别名
git remove add [别名] [地址https]
# 推送操作(要求输入账号密码)
git push [别名] [分支]
# 克隆操作
## 初始化本地库
## 克隆内容
## 替我们创建远程库的别名
git clone [地址]
# 拉取操作（fetch + merge）
## 一步到位
git pull [远程库别名]/[远程库分支]
## fetch
git fetch [远程库别名] [远程库对应分支]
(远程库下载到本地，但是不更新工作区)
## 切换到远程库的分支中
git checkout [远程库别名]/[远程库分支]
## 进行合并(合并之前先切换分支)
git merge [远程库别名]/[远程库分支]
```
**分支(branch)：**

- 新的独立功能开辟一个新的分支。

- 分支的合并。
- hot_fix热修复。
- 分支好处：
  - 并行开发，互相不影响

- 冲突问题：

本地库和远程库的交互

- 创建本地库

- 创建远程库（名字一般和本地库同名）

- 在本地创建远程库地址的别名

  远程库地址：……

- 推送操作：

- 没有加入团队push会失败，必须邀请加入团队

  - settings-> manage access

- 删除git缓存的账号密码：管理你的凭据

- 拉取操作

**协同开发：**

- 协同开发的冲突：*在冲突的情况下直接推送会产生错误，需要先拉取，解决冲突之后再推送。*

**跨团队合作**：

1. fork操作
2. 克隆到本地，进行修改
3. 推送
4. 进行pullrequest

另一团队：

1. 审核，可以互相留言
2. filechange查看具体提交的内容
3. merge request

**SSH免密登录：**

1. 进入用户主目录

2. 生成一个.ssh的目录`ssh-keygen -t rsa -C wang_cei@163.com`

   三次回车，邮箱是github注册邮箱

3. 在.ssh目录有两个文件 `id_rsa`和`id_rsa.pub`

   打开pub，复制内容，打开github->settings->ssh and GPG keys->new ssh -> title随便取

4. 生成密钥之后，就可以正常push

5. git remote add origin_ssh [地址]

   git remote -v

**利用idea集成Git**

本地库初始化：

