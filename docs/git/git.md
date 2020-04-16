#### 01、Git的安装

下载地址：[git-for-windows 镜像](http://npm.taobao.org/mirrors/git-for-windows/)



#### 02、Git查看命令

查看用户名：`git config user.name`

查看用户邮箱：`git config user.email`



#### 03、Git修改提交信息

修改用户名：`git config --global user.username “Zi Jun”`

修改邮箱：`git config --global user.email “zijun2030@163.com”`

 

#### 04、检查是不是已经存在SSH密钥

`cd ~/.ssh` 如果能进入说明已经存在



#### 05、生成SSH密钥

`ssh-keygen -t rsa -C “zijun2030@163.com”` 按3个回车键，密码为空

文件存放位置 `~/.ssh`,如果是window的话，Administrator用户，位置：`C:\User\Administrator.ssh` 下面，如果是其他用户，需要换成对应的用户