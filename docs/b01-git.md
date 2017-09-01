# 通过Git拉去远端仓库并且提交
> 拉取github中项目仓库,
本地修改项目文件,
提交到远端仓库



## 创建新项目
1 创建项目仓库

![create-repository](_images/git-use/b01-01-create-repository.png)

2 查看创建的项目

![show-the-new-repository](_images/git-use/b01-02-show-the-new-repository.png)


## 拉取github中的仓库到本地
3 进到任意文件目录 

![cd](_images/git-use/b01-03-cd.png)

4 复制仓库ssh地址 
> SSH非对称加密方式建立信任

![copy-ssh](_images/git-use/b01-03-copy-ssh.png)

5 克隆github中的远端项目到本地
```
git clone "仓库ssh地址"
```

![clone](_images/git-use/b01-04-clone.png)

> 这样复制下来的项目可以本地修改,做版本,如果要做远端提交我们设置一些全局信息生成项目秘钥


## 初始化设置全局信息 

6 添加github用户名
```
git config --global user.name "Your Name"
```

![set-globe-1](_images/git-use/b01-05-set-globe-1.png)

7 添加github邮箱
```
git config --global user.email "email@example.com"
```

![set-globe-2](_images/git-use/b01-06-set-globe-2.png)

> 无论Linux还是Windows，安装完后都要初始化配置。
```	
	git config --global user.name "Your Name"
	git config --global user.email "email@example.com"
```
目的：git操作身份记录，--global全局配置，也可不加。


## 生成秘钥具备项目发布权限

8 生成rsa密钥对


```
ssh-keygen -t rsa
```

![genrate-key](_images/git-use/b01-07-genrate-key.png)

9 复制秘钥

![copy-key](_images/git-use/b01-08-copy-key.png)

10 项目秘钥添加页面

![add-keypage](_images/git-use/b01-09-add-keypage.png)

11 添加秘钥

![add-key](_images/git-use/b01-10-add-key.png)



## 本地项目添加新文件做版本发布到远端仓库

12 添加 做版本 发布

__以下命令为高频命令__

```
git add -A 添加所有文件及目录
git commit -m "message" 做一个版本,版本留言
git push 项目发布到远端仓库
```

![add-commit-push](_images/git-use/b01-12-add-commit-push.png)

13 以上添加的具体流程图

`git add` 将本地项目提交到stage中 

![add-commit-push](_images/git-use/b01-15-git-principle-1.png)

`git commit`  将stage中的项目做成版本到master分支中

![add-commit-push](_images/git-use/b01-16-git-principle-2.png)


* git工作流


![git-work-flow](_images/git-use/b01-17-git-work-flow.jpg)


## 查看远端仓库和版本信息

14 查看远端github仓库
![check-repository](_images/git-use/b01-13-check-repository.png)

15 查看仓库中项目的版本信息
![check-commit-info](_images/git-use/b01-14-check-commit-info.png)





