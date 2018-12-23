# GIT
	源代码管理工具
	SVN、CVS、VSS、git都是版本管理工具
## GIT安装
	+ 32位
	+ 64位
## GIT使用
	+ git init:初始化一个仓库目录.git
	+ 用户信息配置
		- 配置用户名
			git config --global user.name "GiSingLee"
		- 配置邮箱
			git config --global user.email "498596715@qq.com"
	+ 代码存储到仓库中
		- git add 文件名.XXX :把文件放到暂存区
		- git add ./ :把所有的文件添加到暂存区
		- git commit -m "提交日志" ：把文件从暂存区移到仓库
		- git commit --all -m "提交日志"：把所有修改过后的文件提交到仓库，不经过暂存区，一步到位到仓库中。
	+ 查看当前状态
		- git status:查看当前的状态
	+ 查看提交日志
		- git log：查看历史commit的log
		- git log --oneline:查看简单的commit的log
	+ 回退到指定的版本
		- git reset --hard Head~0:回退到最新一次代码的提交状态
		- git reset --hard Head~1:回退到上上次代码的提交状态
		或者
		- git reset --hard commitID
	+ 查看每次切换版本的记录
		- git reflog：可以查看每一次切换版本的记录以及所有提交的版本号
	+ 分支
		git默认有一个主分支(master)，创建好的分支与主分支拥有的记录是一样的。
		- git branch 分支名：创建分支
		- git checkout 分支名：切换到指定的分支
		- git branch ：查看所有分支
		- 合并分支到主分支
			首先，git checkout 主分支(切换到主分支)
			然后，git merge 分支名(合并分支)
			注意：合并过程中，遇到冲突，需要手动处理，处理完再提交一次。
## GitHub
	是一个网站，相当于git的服务器。该站允许其他人通过git上传下载代码。
	+ 提交代码到GitHub上
		首先，在GitHub上创建一个仓库，创建完成后会生成一个仓库连接。
		然后，git push https://github.com/Marjor/git-demo.git master：把当前主分支的代码根据连接上传到GitHub的主分支上。
	+ 使用HTTPS从GitHub上下载代码
		首先，在本地创建一个项目；
		然后，初始化仓库，git init;
		然后，git pull (GitHub的仓库连接)https://github.com/Marjor/git-demo.git master:从GitHub的主分支master上下载代码。
		- 或者
		git clone (GitHub的仓库连接)https://github.com/Marjor/git-demo.git 名称：会得到远程仓库的数据，多次执行会覆盖本地的内容。第一次一般使用clone。
		注意：名称如果不写则默认为GitHub的项目名称，写了的话表示给这个项目命名。
	+ 使用SSH从GitHub上下载密码(比较安全)
		公钥和私钥之间有联系的。
		- 生成公钥
			ssh-keygen -t rsa -C "合法邮箱"：
		- 生成私钥
			打开公钥文件，全选复制一份，打开GitHub的setting，单击SSH and GPG keys选项，New SSH，填入名称及公钥文件的信息即可创建。
		- 生成公钥私钥后，即可使用git命令push、pull上传下载代码。
	+ 使用一个变量把链接保存起来，方便调用：
		git remote add 变量名 链接(仅限在本bash窗口使用)
		git remote add origin git@github.com:Marjor/git-demo.git
	+ 把本地代码推送到服务器上，推送时指定-u
		git push 链接变量名 -u master
		这样提交后，以后再次提交或拉取直接输入git push(pull)即可。
	+ 多人协作
		push和pull操作，先进行pull动作，保持自己的版本与服务器的版本同步。


