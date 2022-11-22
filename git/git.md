### 1. Git历史

### 2. Git与svn对比

#### 2.1 Svn

- 集中式的版本管理器
- 实际开发中使用也挺多
- 优点：
	- 管理
- 缺点：
	- 服务器单点故障
	- 容错性差

#### 2.2 Git

- 分布式的版本管理工具

- ![image-20200719163228998](C:\Users\Wang Ce\AppData\Roaming\Typora\typora-user-images\image-20200719163228998.png)

- 常用命令流程

	![image-20200719163423129](C:\Users\Wang Ce\AppData\Roaming\Typora\typora-user-images\image-20200719163423129.png)

### 4. Git的安装

#### 4.1 软件下载

### 5. Git的使用

#### 5.1 创建版本库（仓库）

- 什么是版本库？

	Repository

- 创建版本库

	- `git init`
	- Git的GUI
	- 乌龟：不要制作纯版本库

- 向本地仓库添加文件

  - 工作目录：包含.git文件夹的文件夹
  - 如果要向本地仓库添加文件，就必须得把文件放在工作目录下
  - 右键->乌龟->添加，文件显示一个加号
  - 右键->提交->文件显示一个√

- 修改文件并提交

	- 修改之后直接右键提交即可
	- 查看版本库：右键->tortoiseGit->版本库浏览器
	- 查看各个版本有啥不同：右键，查看日志

- 文件的删除

	- 直接删除，如果误删，可以右键->tortoiseGit->还原
	- 要是提交，文件的删除也算是一次修改

5.2.2 工作区和暂存区

- 工作区：工作目录
- 暂存区：在版本库里面的一个区域，添加操作是加入暂存区![image-20200721100826047](C:\Users\Wang Ce\AppData\Roaming\Typora\typora-user-images\image-20200721100826047.png)

### 6. 远程仓库

- 通信协议：
	- https:
	- ssh协议：安全外壳协议，比较可靠的安全的通信协议
	- 公钥和私钥

#### 6.1 创建SSH密钥以及在gitHub上配置公钥

- `ssh-keygen -t rsa`

	运行结果：

	```
	$  ssh-keygen -t rsa
	Generating public/private rsa key pair.
	Enter file in which to save the key (/c/Users/Wang Ce/.ssh/id_rsa):
	Created directory '/c/Users/Wang Ce/.ssh'.
	Enter passphrase (empty for no passphrase):
	Enter same passphrase again:
	Your identification has been saved in /c/Users/Wang Ce/.ssh/id_rsa
	Your public key has been saved in /c/Users/Wang Ce/.ssh/id_rsa.pub
	The key fingerprint is:
	SHA256:QVZkh8oG4XEw6SFltp3Kl8bRk7fbkwp4eokdHAhx2wE Wang Ce@LAPTOP-OCU0QS4R
	The key's randomart image is:
	+---[RSA 3072]----+
	|     .X=E+=..    |
	|    .+=X *.+     |
	|     oo=*o= .    |
	|     ..o=+.o .   |
	|      o.S. ..    |
	|       o .o  o . |
	|        .ooo. +  |
	|        .o+. . . |
	|        ..  .    |
	+----[SHA256]-----+
	
	
	```

- 密钥存在：C:\Users\Wang Ce\.ssh 中

#### 6.2 使用https推送至

#### 6.3 克隆远程仓库到本地

- 命令行

	`git clone git@github.com:WangCece-real/repo1.git`

#### 6.4 推送修改的文件以及冲突解决

- 修改之后存到本地仓库之后再推送到远程端
- 远端修改之后同步到本地，点击拉取，就将远程仓库的东西更新到本地仓库

##### 冲突解决

- 如果服务器的内容已经更新，你需要在最新的内容基础上进行修改，才可以完成新的推送。
- 如果服务器修改了，本地也修改了，从服务器拉取也会出现冲突，冲突会罗列出在文件中，必须要手动处理。然后右键->解决冲突->提交到本地仓库->推送到远程仓库

#### 6.5 搭建私有Git服务器

其实就是搭建一个服务器，将其当做远程仓库使用

6.5.1 服务器的搭建



### 7 分支管理

- 什么是分支：

	master分支是一条时间线，每次提交，master就会向后移动一个节点。

	![image-20200722163859608](C:\Users\Wang Ce\AppData\Roaming\Typora\typora-user-images\image-20200722163859608.png)

	

#### 7.1 创建合并分支

- 创建分支

	![image-20200722163942174](C:\Users\Wang Ce\AppData\Roaming\Typora\typora-user-images\image-20200722163942174.png)

	- 乌龟->切换/检出->新建分支

	- 合并

		![image-20200722164840584](C:\Users\Wang Ce\AppData\Roaming\Typora\typora-user-images\image-20200722164840584.png)

- 分支合并和删除

	- 

