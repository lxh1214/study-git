# 学习git. #
## 第二次change ##
##3##
####d####

###3###

    git init //初始化
    git add fileName //添加文件 
    git commit fileName -m "commit description"//提交  -m 后跟着提交 说明
    git status // 查看本地状态 
    git diff fileName // 查看文件版本的 修改的内容 注：没有提交的做与上一个版本对比
	git log //查看所有 commit 版本
	git log --pretty=oneline //以一行的形式显示一个版本
	git reset --hard HEAD // 回归 历史版本 HEAD 是当前的版本也就是最近提交的版本 
						// HEAD^ 上一个版本 HEAD^^ 上上个版本  如果要回到那个 
						//需要注意的是 不管回到哪个版本  需要把 最近的版本 id 号记下 以免错误回滚



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
