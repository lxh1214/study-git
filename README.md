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
	git log --pretty=oneline --abbrev-commit 显示提交的 版本

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

	git push origin branch-name //推送 分支到github

    git clone git@github.com:username/project-name.git // 克隆 远程 资源. username github上的用户名，project-name 远程创库名称
	git clone https://github.com/username/project-name.git // 也是克隆远程 资源

	git checkout -b branch-name // 创建并 切换到 branch-name 分支名
	git branch //列出所有 分支

	git checkout branch-name // 切换分支

	git stash //保存当前的 工作  
	git stash list //暂时保存的 状态 列表
	git stash apply // 恢复最近一个保存的工作 时间
	git stash apply stash@{0} // 恢复指定的暂时保存的 工作装填
	git stash pop //删除 list 中的状态

	git checkout -b local-branch-name origin/branch-name  //获取区远程的分支

	git branch --set-upstream-to=origin/branche-name local-brance-name //把本地创建的分支和远程的分支 关联上
	
	git pull // 获取远程的 对应分支的 资源  会merge 到相关的本地分支 以便于 push 操作

	git fetch origin master // 获取远程 分支 master 的最新 版本 但不合并

	git fetch origin master:tmp // 获取远程 分支master 最新的版本 并命名为tmp ，
	git diff tmp //当前版本 与tmp 的不同 以便于 merge

	git merge dev // 把dev分支的内容合并到 当前的 分支
				merge 也可以加 -m "description" 合并的描述
	
	git branch -d branch-name // 删除分支
	git branch -D branch-name //强制删除分支

	git tag tagName //最近的commit 打标签
	git tag 显示所有标签

	git tag tagName commit-id // 给已提交的版本打标签
	
	git show tagName // 查看标签对应的提交信息
	
	git tag -d tagName //删除本地打好的标签
	
	git push origin tagName //把本地标签 推送到远程 
	git push origin --tags // 推送所有 遍地标签

	
	git remote -v // 获取远程 资源库的名称
	(fetch) 是可 获取的
	(push) 可提交的

	
	git branch --vv 查看 本地分支和远程分支 关联信息
	git config --list 同上 更详细的信息
	111
     概念 
	1. add 是到 staged 暂存区
    2. commit 是到 资源库  也就是.git 下管理版本的
    3. 工作区 就是文件创建的那个文件
    4. 公钥 秘钥 生成 是认证 谁可以
    5. push 代码到 github 上
         



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
