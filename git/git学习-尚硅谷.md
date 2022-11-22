## 基本

#### git的基本结构

![image-20201004103355449](C:\Users\Wang Ce\AppData\Roaming\Typora\typora-user-images\image-20201004103355449.png)

#### git和代码托管中心

#### 本地库和远程库

- 团队内：![image-20201004103630131](C:\Users\Wang Ce\AppData\Roaming\Typora\typora-user-images\image-20201004103630131.png)

- 跨团队操作：

	![image-20201004103845191](C:\Users\Wang Ce\AppData\Roaming\Typora\typora-user-images\image-20201004103845191.png)

## 4. Git命令行

### 4.1 本地库初始化

- linux命令：
	- `ll` : 当前目录下的资源
	- `ls -lA` : 带隐藏资源
	- `ls -l|less` : 
	- `cd` : 
	- `mkdir` : 
	- `cd ~`
	- `pwd` :
	- `vim good.txt` : 新建一个文件
		- `:set nu`: vim中显示行号
		- `i`: 编辑
		- esc: 退出vim
	- `rm` : 删除
- `git init` : 初始化一个git的仓库
	
- .git 目录中存放的是本地库相关的子目录和文件
	
- **设置签名：**

	- 形式

		用户名：

		Email地址：

	- 作用：区分不同开发人员的身份

	- 辨析：签名和登录远程库的账号密码没有关系

	- 级别：

		- 项目级别/仓库级别：仅在当前本地库范围内有效
		- 系统用户级别：登录当前操作系统的用户范围
		- 优先级：
			- 就近原则：项目级别优先于系统用户级别
			- 二者都没有不允许

	- 命令：

		`git config` : 项目级别

		`git config -- global` : 系统用户级别

		```
		git config user.name tom
		git config user.email shide@qq.com
		```

		查看仓库的信息：

		`cat .git/config`

		系统用户级别保存位置：

		`cat ~/.gitconfig`

- `git status` 查看仓库状态

### 4.2 添加和提交

- 命令：`git add` 添加：红变绿

	`git rm --cached <file>` 移除：绿变红

- `git commit <file>` : 提交

- 修改之后

	```linux
	git add good.txt
	git commit -m "这是我的修改日志" good.txt
	```
### 4.3 版本的穿梭
- 查看版本信息：
  - `git log` ：查看版本记录
    - 空格向下翻页
    - b 向上
    - q 退出
  - `git log --pretty=oneline` : 每个版本显示一行
  - `git log --oneline` : 更简洁一些
  - `git reflog` : 对前进和后退移动指针有帮助
- 版本前进后退：
	- 基于索引值操作：
		- `git reset --hard 9a9ebe0`
	- 使用^和~符号：只能后退
		- `git reset --hard HEAD^`
		- `git reset --hard HEAD~3`后退3步
- hard 和 soft 以及 mixed 参数对比
	- soft 仅仅在本地库移动HEAD指针
		- 只是本地库前移，可能会显得暂存区有所修改
	- mixed 在本地库移动HEAD指针，重置暂存区
	- hard 在本地库移动HEAD指针，重置暂存区，重置工作区
- 删除文件找回总结：
  - 删除文件和找回
  	指针指向历史记录
  - 添加到暂存区的删除文件找回
		指针指向HEAD
- 比较文件差异
	- `git diff apple.txt`
		将工作区和暂存区的文件进行比较
	- `git diff HEAD apple.txt`
		工作区和某个版本进行比较
	- `git diff HEAD`
		不指定名称，则比较所有文件
#### 4.4 分支

- 什么是分支：

	![image-20201004130015124](C:\Users\Wang Ce\AppData\Roaming\Typora\typora-user-images\image-20201004130015124.png)

- 分支的操作：

	- 查看所有分支：`git branch -v`
	- 创建分支：`git branch hot_fix`
	- 切换分支：`git checkout hot_fix`
	- 合并分支：
		1. 切换到接收修改的分支上（被合并，增加新内容）
		2. `git merge hot_fix`

- 冲突解决

	![image-20201004130921535](C:\Users\Wang Ce\AppData\Roaming\Typora\typora-user-images\image-20201004130921535.png)

	1. 编辑文件，删除特殊符号，满意后保存退出
	2. 用`git add good.txt` 标记为冲突已解决。
	3. 用`git commit -m "daddaw" `结束merge的过程。

## 5. Git 的基本原理