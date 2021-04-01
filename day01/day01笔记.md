# 一.认识git

## 1.git的定义

**git是一个分布式的版本控制工具**

        分布式：在网络互不影响，独立操作      例如：git
    	集中式：有一个中心服务器来连接这些设备  例如：SVN
### 		1.git 如何使用

> git常用命令
>
> 1. 初始化git: git init
> 2. 查看当前git文件状态：git status
> 3. 添加文件到暂存区：git add 文件名1 
> 4. 提交到本地仓库：git commit -m '版本说明'
> 5. 添加可忽略文件：.gitignore
> 6. 提交到远程仓库  git push

### 	2.官网：

​		https://gitforwindows.org/

##    2.提交远程仓库的步骤：

#### 	1.创建远程仓库

​		注意：配置好公钥，秘钥

​			ssh-keygen -t ed25519 -C  "你的邮箱名：139.com"

​			秘钥：id_rsa      公钥:id_rsa.pub

​			测试连接成功： ssh  -T  git@github.com

#### 	2.配置连接的远程仓库

​			git remote add origin git@github.com：远程仓库地址

​			https://github.com/Carved-fined/05Epro.git

#### 	3.推送到远程仓库

​			git push origin 本地分支名

​			如果推送拒绝，拉取本地在推送：

​			git pull origin 远程分支名：本地分支名                                                                                                                                                                                                                                          