# 说明 
本repository为阅读论文及总结记录，未经本人允许不得作商业用途

本组成员（东北大学）：

* 郅**
* 郑** 
* 胡**

* tool文件夹中的为可用的攻击工具
## 删除github远端文件夹
因为我老是一不小心把不需要的文件夹传上去，所以记录一下删除远端文件夹的办法。

删除文件夹时要加`-r`参数，不知道为什么，但是照做就好了。

		git rm --cache -r 你的文件夹名
		git commit -m "你删除该文件夹的记录日志"
		git push

## git 设置代理
### 启用
		git config --global http.proxy http://proxyuser:proxypwd@proxy.server.com:8080
		git config --global https.proxy https://proxyuser:proxypwd@proxy.server.com:8080
		git config --global http.sslVerify false
###禁用
		git config --global --unset http.proxy
		git config --global --unset https.proxy
###检查
		git config --global --get http.proxy
		git config --global --get https.proxy

## 使用git导入仓库到gitee(ssh方式)
* 先在码云中创建仓库
* 在本地配置好用户名，邮箱,命令： `git config user.name YourName`,`git config user.email YourMail`
* 生成密钥：`ssh-ketgen -t rsa -C "YourEmail"`,再三次回车以完成
* 查看密钥：`cat ~/.ssh/idrsa.pub`
* 将密钥复制到你的码云中
* 在本地输入`ssh -T git@gitee.com`
* 本地仓库中进行 git init,git remote等基本操作
* 一般是可以pull的，但有时会提示 unrelated histories，这时就需要 `$git pull origin master --allow-unrelated-histories
`,如果成功后，使用 `git push origin master:master`即可，意思是：git push 远程主机名 本地分支名：远程分支名

#合作人

本人：https://github.com/forrestk3/paper_summary_hubing.git

郅：https://github.com/Ajoyzhi/my_literature

郑：https://github.com/zhengyjs/TorinoZone.git