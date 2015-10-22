# 学习git. #
## 第二次change ##

    git init //初始化
    git add fileName //添加文件 
    git commit fileName -m "commit description"//提交  -m 后跟着提交 说明
    git status // 查看本地状态 
    git diff fileName // 查看文件版本的 修改的内容 注：没有提交的做与上一个版本对比
    git diff HEAD fileName //查看当前资源库里 与 工作区里()的 区别
	git log //查看所有 commit 版本
	git log --pretty=oneline //以一行的形式显示一个版本
	git reset --hard HEAD // 回归 历史版本 HEAD 是当前的版本也就是最近提交的版本 
						// HEAD^ 上一个版本 HEAD^^ 上上个版本  如果要回到那个 
						//需要注意的是 不管回到哪个版本  需要把 最近的版本 id 号记下 以免错误回滚
    git reset HEAD fileName 把当前 资源库里的版本对应的 fileName 文件 覆盖工作区
	git reflog // 查看所有提交和回滚的 id

	git checkout -- fileName 把文件 退回修改 工作区的当前版本

	git rm fileName  //删除资源管理库的 文件  接着提交才有用
    git commit // 提交


	ssh-keygen -t rsa -C "email" //在单个pc上生成 公钥 密钥  id_rsa.pub 公开  
	
	git remote add origin https://github.com/lxh1214/study-git.git // 关联远程库 study-git.git 是在远程创建好的 
	// 也就是 github.com上登录自己的帐号

	git push -u origin master // 推送本地 内容 上master 分支

	git push origin master //本地需要修改 远程master 分支时 

    git clone git@github.com:username/project-name.git // 克隆 远程 资源. username github上的用户名，project-name 远程创库名称

	git checkout -b branch-name // 创建并 切换到 branch-name 分支名
	git branch //列出所有 分支

	git checkout branch-name // 切换分支
     概念 
	1. add 是到 staged 暂存区
    2. commit 是到 资源库  也就是.git 下管理版本的
    3. 工作区 就是文件创建的那个文件
    4. 公钥 秘钥 生成 是认证 谁可以push 代码到 github 上
         



* a <br>
>a //引用 <br>
*斜体*


* [wang 超链接](http://www)<br>
* 
    **加粗**a


''a'' <br>
1. 1sdfa<br>
2. dsf

---
***斜体加粗***<br>
+ 1 <br>
+ sdf

- c
- c
xxx

[到下一点][3]

[3]: http://www.baidu.com

<exmpal@example.com>

`` `包裹起来` ``


<strong>Blockquotes 引用：</strong>
> Email-style angle brackets
> are used for blockquotes.
> > And, they can be nested.
> #### Headers in blockquotes
> * You can quote a list.
> * Etc.

***
* * * 






![图片](http://d.hiphotos.baidu.com/zhidao/pic/item/902397dda144ad345a0ed8b4d0a20cf431ad854b.jpg)<br>
