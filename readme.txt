aaaaaaaaaaaaaaaaaaaa
1234567890
this is a git test file.

Git is a distributed version control system.
Git is a free software distributed under the GPL.

20200208_11_36
end

回退版本: git rest --hard HEAD^

git 操作步骤：
1、安装git，安装完成后，设置名字和邮件：
	git config --user.name "xxxx"
	git config --user.email "xxxx"

2、创建版本库,初始化git仓库：
	git init 

3、添加文件：
	git add <file name>
	git commit -m <message>

4、查看状态：
	git status //查看版本库当前状态；
	git diff <file> //查看修改

5、版本回退：
	git log //查看提交日志
	git reset --hard HEAD^ //回退到上一个版本
	git reset --hard commit—id //回退到指定版本
	git reflog //查看命令历史

6、版本管理：
	修改必须要git add，再git commit。如修改在工作区未添加到暂存区，则工作区的修改不会提交到版本库；
	git diff HEAD -- <file>

7、撤销修改：
	git checkout -- file//丢掉工作区的修改
	1、工作区文件修改后未添加到暂存区，撤销修改后回到和版本库一样；
	2、修改已添加到暂存区，又作了修改，撤销修改后回到和暂存区后的状态；

	git reset HRED file //把暂存区的修改回退到工作区；

8、删除文件：
	1、确实需要从版本库中删除文件：
		git rm file
		git commit -m “messgae”
	2、误删文件管理器里的文件，可以从版本库里恢复；
		git checkout -- file

9、远程仓库：
	1、创建远程仓库：
		1、ssh-keygen -t rsa -C "邮箱地址"
		2、把产生的公钥添加到github账户里
		3、在github创建新仓库
	2、关联仓库，并推送：
		1、git remote add origin git@gitgithub.com:"地址" //ssh加密方法，还有https协议
		2、git push -u origin master
	3、从远程仓库克隆：
		1、先建好远程仓库；
		2、git clone git@github.com：“地址”
	