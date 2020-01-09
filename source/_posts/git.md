## 版本控制（git）

> 版本控制软件大致分为： 本地，集中式(SVN)，分布式版本控制系统(git)。

### git工作原理

- git的三个区域及三种状态

  - modified：工作目录是对项目的某个版本独立提取出来的内容，这些从git压缩数据库中提取出来的文件，放在磁盘上供你使用或修改。
  - staged：暂存区域是一个文件，保存了下次将提交的文件列表信息，一般在git仓库目录中。有时也被称为索引，不过一般还是叫暂存区域。
  - committed：git仓库是git用来保存项目的元数据和对象数据库的地方，是git最重要的部分。
- git的基本指令

  1. git init : 创建了一个.git 目录（仓库）
  2. git config --global user.name / user.email  配置用户信息。--list  以列表形式查看信息
  3. git status: 查看仓库状态
  4. git add :将文件放入暂存区       ./*/-A   把所有文件放入暂存区
  5. git checkout 文件名 :  可以丢弃工作区的修改 
  6.  git reset HEAD file  可以把暂存区的修改撤销掉 
  7. git commit -m '标记' ： 将暂存区内容放到仓库永久存储
  8. git log ： 查看当前版本日志
  9. git reset --hard 提交ID : 可以把特定ID的版本还原到本地
  10. git commit --amend   可以修改最后一次的提交日志
  11.  git reflow 查看操作历史
  12.   git diff HEAD -- readme.txt   可以查看工作区和版本库里面最新版本的区别 
  13.  git rm  用于删除一个文件 
  14.  git stash  可以把当前工作现场“储藏”起来，等以后恢复现场后继续工作 
  15.  git stash pop  恢复的同时把stash内容也删了 
  16.  git  cherry-pick 4c805e2  复制一个特定的提交到当前分支 
- git 分支
     * 至少要commit一次才会创建一个分支；分支有继承，新创建的会继承父分支的所有提交历史
     * git  branch  分支名  创建新分支
     * git  branch  显示所有分支
     * git  checkout  分支名    切换分支
     * git  checkout  -b  分知名   创建并切换到新分支
     * git checkout -b dev origin/dev  创建远程`origin`的`dev`分支到本地 
     * git  merge  分支名  合并分支
     * git  branch  -d/-D   分支名   删除分支

##  远程仓库

### 远程仓库的创建条件

> 1. 创建一个xxx.git的文件夹
> 2. 创建一个裸仓库（git   init --bare）

### 远程仓库的指令

> 1. git	push	远程仓库地址		master	    把master放到远程仓库
> 2. git    pull        远程仓库地址          master       把远程仓库的master分支pull过来
> 3. git    remote  add   别名   地址     给远程仓库创建一个别名
> 4. git    clone    远程仓库地址  自己的文件夹     把远程仓库直接拷贝到相应的文件夹中
> 5. 添加别名后可以通过 git  remote  查看所有别名
> 6. clone过来的文件夹操作仓库时默认有个别名  origin
> 7. git   remote show   origin  显示远程地址的详细信息
> 8. 拉取过程出错 ： git pull --rebase  别名   分支名



`本地生成SSH密钥指令		ssh-keygen  -t  rsa`

## bash指令

* pwd	查看当前目录
* ls   -a   -l   以列表形式查看文件夹下的所有文件
* touch    创建一个文件(touch   index.html)
* cat    查看文件中的所有内容
* more/less   查看文件       q:  退出
* rm   删除文件         rm  -r   js/   循环删除文件夹下的所有文件
* rmdir    删除空文件夹
* mv    移动/重命名文件
* cp     复制同时也可以修改文件名
* head  -5   a.txt /    tail   -5    a.txt   查看文件前5行或后5行内容
* history  查看操作历史
* '> '  和  >> 重定向    >  覆盖原内容   >>在后面追加
* curl   网络请求    curl   http://baidu.com
* whoami   查看当前用户
* ls   |   grep   s    把ls的输出作为grep的输入.grep后面跟的是正则  然后是从那个文件/输入找

##  vi编辑器

> vi  文件名  进入命令行模式` 再输入 i/a/A/o/O  `  进入输入模式  `输入esc`  退回到命令行模式 `输入: `进入底部模式

命令行模式指令: 	

ZZ 	保存并退出		u	撤销操作		dd	删除当前行	yy复制当前行			p 	粘贴

ctrl+f	向下翻页				ctrl+b	向上翻页

底行模式: 

w	保存 	w	index.html 另存为一个文件		q	退出	wq	保存并退出

e!	撤销更改返回到上一次		q!	不保存强制退出

set	nu	设置行号