##  生成ssh key步骤
这里以配置github的ssh key为例：

1 配置git用户名和邮箱git config user.name "用户名"

	git config user.name "用户名"
	git config user.email "邮箱"

2 在config后加上 --global 即可全局设置用户名和邮箱。生成ssh key 

	ssh-keygen -t rsa -C "邮箱"

	然后根据提示连续回车即可在~/.ssh目录下得到id_rsa和id_rsa.pub两个文件，id_rsa.pub文件里存放的就是我们要使用的key。

3 上传key到githubclip < ~/.ssh/id_rsa.pub

	1. 复制key到剪贴板
	2. 登录github
	3. 点击右上方的Accounting settings图标
	4. 选择 SSH key
	5. 点击 Add SSH key

4 测试是否配置成功

	ssh -T git@github.com 

如果配置成功，则会显示：

	Hi username! You’ve successfully authenticated, but GitHub does not provide shell access.
