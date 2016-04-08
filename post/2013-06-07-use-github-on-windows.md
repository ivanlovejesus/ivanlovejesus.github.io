## step1 注册github##
注册 github 账号并创建一个repo，假设帐户为**YourAccount**，repo为*test_repo*，your_email@your_email.com
## step2 下载必要的软件##
下载git 软件：

	https://code.google.com/p/msysgit/
我用的是Git-1.8.3-preview20130601.exe
## step3 安装git并配置##
下载后安装，注意选择

![](http://freewind.me/wp-content/uploads/2011/09/image_thumb9.png)

![](http://freewind.me/wp-content/uploads/2011/09/image_thumb11.png)
## step4 生成公私钥##
打开git 命令行界面测试本地是否有ssh，在命令行输入：

`cd ~/.ssh`  

此时系统应该反馈“系统找不到指定文件”，那么我们继续输入:

`ssh-keygen -t rsa -C "your_email@your_email.com"`

然后问你保存的目录，请直接回车即可。 输入一个密码（passphrase）或直接回车，你注册github时候的密码，会生成如下内容：

![](http://static.wojilu.com/upload/image/2011/11/9/9134204169061194_m.jpg)

在命令行输入以下代码将密钥拷贝到剪贴板（或者用编辑器打开id_rsa.pub并复制其中的内容）：
	
`clip < ~/.ssh/id_rsa.pub`
## step5  拷贝公私钥到帐户##

打开github  Account Settings > SSH Keys > Add SSH key >  ctrl+v按粘贴 >save
##step6 ##
请打开Git Bash，输入如下代码:

`ssh -T git@github.com`

如果提示“can't be established.”什么东西（如下代码），请不要管，直接按yes

> The authenticity of host 'github.com (207.97.227.239)' can't be established.
> RSA key fingerprint is 16:27:ac:a5:76:28:2d:36:63:1b:56:4d:eb:df:a6:48.
> Are you sure you want to continue connecting (yes/no)?

然后提示输入密码（passphrase）
如果看到 
> You've successfully authenticated, but GitHub does not provide shell access 

信息，就表示连接成功。

##step7 设置用户名##

`$ git config --global user.name "YourAccount"`

`$ git config --global user.email "your_email@your_email.com"`

##stetp8 开始fork ##

`cd /myfolder`

`git clone git@github.com/YourAccount/test_repo.git`

在克隆过程中，会要求你输入密码(passphrase)。
git会自动把代码下载下来，放在当前目录下的myfolder目录下
##stetp9 获取原始库的最近更新#
##step10 将你的修改提交给 test_repo 原始库 ##


参考文章：

	- http://www.wojilu.com/Forum1/Topic/2266
	- http://www.worldhello.net/gotgithub/04-work-with-others/010-fork-and-pull.html