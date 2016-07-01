#linux network io 模型#
	
##io 的整个过程##
- 涉及到两个对象 1. 调用IO process (对应io处理函数) 2. 系统内核（kernel）
- 当用户发起read操作时 1. 等待数据(io process) 2. 内核拷贝准备好的数据到用户内容并返回状态
##blocking io##

	在linux系统中，默认的情况下所有的socket都是blocking，一个典型的read操作流如果下
	recvfrom    1. -----系统调用(system call) ----- kernel 等待 所有的数据 到达
                上面数据到达后
               2. kernel 获取上面的数据并复制数据给当前用户内存
               以上就存在两个等待时间的地方 "等待数据到达的时间" "kernel拷贝数据到用户内存里"
			   也就是所谓的blocking （阻塞的地方)
	以上就是用户读取数据的过程.

##non-blocking io##

	在blocking io 的过程1.中有不同的地方。
	1. 当用户调用recvfrom 时会立刻返回是否数据已经到达，如果没有完全到达则返回error 
	 这样就不用阻塞了， 然而继续发送recvfrom 确认状态 （反复则个过程）直到有数据达到，后在进入 。
	2. kernel 复制数据到用户内存. (和blocking io 第二的阶段一样)

##io multiplexing ##
	
	select/epoll 单个process 可以处理多个network io。 select/epoll 这个function 不断轮询自己所负责的socket，
    查看socket 如果有某个socket 数据到达后就通知 系统，执行recvfrom （因为数据到达后就进入，kernel 拷贝数据到用户内存阶段）
	
	整体的逻辑是 用户调用select 后 处于阻塞模式，同时kernel 会监听所有 select 负责的socket， 当有任何一个socket数据准备
    好了 select就返回，并让当前的用回调用recvfrom - kernel 拷贝 data 
    以上的处理过程 阻塞的地方 是select 而不是 blocking io 了。
	注意： 这个模式的优势在于可以同时 监视多个 socket 只要有任一个 完成 则就不阻塞 退出select，然后去处理

##asynchronous io ##
	
	用户发起read操作后， 立刻就可以开始做别的事情。  kernel 接收到 asynchronous read 的后立刻返回， 然后不会用户任何进程
    产生block， 然后kernel 等到数据准备完 并且 kernel包数据拷贝到用户内存，完成后会发一个signal给用户 告诉它read操作完成。

	全部交给 kernel 的 asynchronous 处理.



## 总结 ##
	1. blocking io  是在 recvfrom 发出后  datagram ready (block) , kernel copy to user (blcok)
	2. non-blocking io 是 在不段的发出 recvfrom check 不管成功与否 都返回对应的状态。
						状态值为 error 就不会阻塞， 用户再次发送 recvfrom check 。 如果成功再次发送recvfrom 
                        然后在进入kernel data copy to user 阶段(block)
    3. io mutiplexing 是利用select/epoll 的阻塞 换取 datagrap waiting ready  这里的是select 可以同时监视多个
	    			  socket 只要有一个完成了 数据准备既调用 kernel data copy to user 阶段.
					  以上select 和 copy 都是 (block)
    4. asynchronous io 则是完全的异步 发出read操作后交由 kernel 的asynchronous read 处理，且立刻返回 kernel 会把
                       准本好的数据（包括 copy to user） 状态 发送一个signal 给用回表示已经ok（read 操作完成）
                       整个过程没有block
