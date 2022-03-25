# *高效学习

1.思维导图做读书笔记

 读书时，试着用思维导图做梳理，你会发现读完了可以很方便地回顾，以后时长翻翻自己的思维导图笔记，再也不用发愁读过的书会忘记了，而且脑子中往往会结构性地出现整本书的模型，非常有用。

2.横向读书法

   当你了解一个有立场的学科或者主题时，不妨几个立场的书一起读，可以有效帮助你辨别更全面的事实，尤其是历史、宗教、哲学等。

3.纵向读书法

   想快速了解一个学科，最好的办法就是迅速大量阅读同学科的书，不求甚解，多读几本你就懂了，因为精华的部分会重复出现的。

4.主动分享

​    想真正掌握所学，就要不吝分享，分享是把所学化为所用最快的方法

5.学会做计划

​    凡事预则立，学会做年度大事件计划，月度计划，周计划，最好每天早上也做个晨间计划，1分钟搞定高效率的一整天。其他事情也是如是，不要迷茫，按照计划走，才有方向感。

6.学会做总结

   每天晚上给自己一个独处的时间，思考自己的言行，得与失，最好做个记录，比如日记。完成一个大的项目或者事件时学会做总结，为下一次同样的事情打基础。

7.利用碎片时间

   学会利用碎片时间，集腋成裘，比如阅读、思考，甚至休息。

8.常用的东西要舒服

​    常用的鼠标、键盘、手机、包等，这方面不要吝啬，甚至要学会适当奢侈，选择最舒适的，工欲善其事，必先利其器。（不要轻易选择、决定，量力而为，**严进宽出**，贵的也不一定好，实事求是根据自身情况做选择）

9.学会放松

​    会娱乐会放松，才能更快乐地活着，所以学会主动放松，投入地放松。

10.冥想

​     冥想是非常值得学习的技巧，可以再冥想中仔细观察自己，体会自己，彻底放松自己，了解自己。

11.把锻炼和兴趣联合起来

​     比如跑步是一件很痛苦的事，我就在跑步的时候听评书，一下就觉得跑步得痛苦好像消失了，听书的乐趣让我慢慢坚持了下来。



12.可以先试着这些简单的tips

（1）早睡早起；

（2）坚持在同样的时间睡觉和起床；

（3）少食多餐(正餐不要吃太多，正餐之间吃一些低糖低热零食)；

（4）饮食健康，营养均衡；

（5）减少单糖化合物摄入；

（6）每天吃早餐；

（7）每天喝1.4~1.8L水；

（8）每天进行适量身体活动；

（9）工作每90min休息片刻（根据情况做调整）

# *关于将项目上传到GitHub等仓库的操作

##**很重要很重要**

### push更新代码不成功，反而把本地代码弄丢

提交代码到远程分支，然后本地代码消失了，找回本地代码的操作：

1、执行命令：

> git reflog	

![](E:\issue_md\image\Snipaste_2021-12-20_18-15-11.jpg)

2、用reset (Suppose the old commit was HEAD@{5} in the ref log)

> git reset --hard HEAD@{9}
> 亲测有效！解决了～解决了～



## git的使用--上传到GitHub仓库的方法

### 一.仓库在GitHub上的，本地无仓库的(文件夹)

1.安装git工具

https://git-for-windows.github.io/

2.注册github账号

https://github.com/

3.登录GitHub，进入首页，点击New

![](issue.assets/Snipaste_2021-12-15_15-46-44-16480059672561.jpg)

4.创建仓库

![](issue.assets/Snipaste_2021-12-15_15-49-32.jpg)

5.创建成功后可以看HTTPS地址和SSH地址

6.在要上传的项目目录里打开Git Bash Here

7.把GitHub上面的仓库克隆到本地

命令：git clone [url] 备注：[url] 是项目地址

8.然后本地文件夹会多出一个文件夹，文件夹名称即为GitHub上的地址

9.把要上传的项目文件全部移到新多出来的文件夹里

10.接着进入新的文件夹里或者cd进去，打开git bash here ，

命令：

1.git add .     备注：后面的小点‘.’代表所有文件都加进git的本地仓库里，也可以指定文件。

2.git commit -m "提交的描述"

3.git push -u origin master  （注：此操作目的是把本地仓库push到github上面，此步骤需要你输入帐号和密码，从2021.8.14号开始不支持密码验证了，改成token校验）

### 二.本地已有项目仓库的(文件夹)，需要上传到GitHub仓库的

1. 需要先创建一个本地的版本库，假设文件夹起名为pros（其实也就是一个文件夹）直接右击新建文件夹，也可以右击打开Git bash命令行窗口通过命令来创建；

2. 进入文件夹，通过命令 git init 把这个文件夹变成Git可管理的仓库 ，这时会多出一个 .git的文件夹，里面的config文件可以查看仓库地址；

3. 将项目粘贴到这个本地Git仓库pros里面,然后通过git add把项目添加到仓库（或git add .把该目录下的所有文件添加到仓库，注意点是用空格隔开的）。在这个过程中你其实可以一直使用git status来查看你当前的状态;

   注意如果是从其他仓库转到自己的仓库的：需要先这样

   ```
    git rm -r --cached .
     git config core.autocrlf false
   
     git add .
   ```

   

4. 用git commit -m "注释内容" 把项目提交到仓库;

5. 由于本地Git仓库和Github仓库之间的传输是通过SSH加密的，所以连接时需要设置一下：创建SSH KEY。先看一下你C盘用户目录下有没有.ssh目录，有的话看下里面有没有id_rsa和id_rsa.pub这两个文件，有就跳到下一步，没有就通过下面命令创建。

   ```
   $ ssh-keygen -t rsa -C ``"youremail@example.com"` `注意ssh-keygen之间没有空格
   ```

   然后回车，询问保存key的位置，默认是在括号里的路径下，你可以修改，也可以不做修改

   可能提示要输入密码，为了不必要麻烦，还是不要设置密码，因为容易忘记，不输入密码，回车；确认密码不输入，回车

   这时你就会在用户下的.ssh目录里找到id_rsa和id_rsa.pub这两个文件

6.登录Github,找到右上角的图标，打开点进里面的Settings，再选中里面的SSH and GPG KEYS，点击右上角的New SSH key，然后Title里面随便填，再把刚才id_rsa.pub里面的内容复制到Title下面的Key内容框里面，最后点击Add SSH key，这样就完成了SSH Key的加密。具体步骤也可看下面：

![](E:\issue_md\image\Snipaste_2021-12-15_16-13-32.jpg)

![](E:\issue_md\image\Snipaste_2021-12-15_16-14-02.jpg)

![](E:\issue_md\image\Snipaste_2021-12-15_16-14-25.jpg)

![](E:\issue_md\image\Snipaste_2021-12-15_16-16-14.jpg)



7. 在Github上创建好Git仓库之后我们就可以和本地仓库进行关联了，根据创建好的Git仓库页面的提示，可以在本地pros仓库的命令行输入：注意origin后面加的是你Github上创建好的仓库的地址。

   ```
   git remote add origin [url]
   ```

​        

8. 关联好之后我们就可以把本地库的所有内容推送到远程仓库（也就是Github）上了，通过：

   git push -u origin master
   
   在这里可能需要输入账号密码，密码现在改成（token）

由于新建的远程仓库是空的，所以要加上-u这个参数，等远程仓库里面有了内容之后，下次再从本地库上传内容的时候只需下面这样就可以了：
$ git push origin master





## 关于git的权限校验的问题

一、 如何生成自己的token
1、在个人设置页面，找到Setting（参考）

2、选择开发者设置Developer setting

3、选择个人访问令牌Personal access tokens，然后选中生成令牌Generate new token

4、设置token的有效期，访问权限等

选择要授予此令牌token的范围或权限。

要使用token从命令行访问仓库，请选择repo。
要使用token从命令行删除仓库，请选择delete_repo
其他根据需要进行勾选

5、生成令牌Generate token

如下是生成的token

注意：

记得把你的token保存下来，因为你再次刷新网页的时候，你已经没有办法看到它了，所以我还没有彻底搞清楚这个token的使用，后续还会继续探索！

6、之后用自己生成的token登录，把上面生成的token粘贴到输入密码的位置，然后成功push代码！

也可以 把token直接添加远程仓库链接中，这样就可以避免同一个仓库每次提交代码都要输入token了：

git remote set-url origin https://<your_token>@github.com/<USERNAME>/<REPO>.git

<your_token>：换成你自己得到的token
<USERNAME>：是你自己github的用户名
<REPO>：是你的仓库名称
例如：

git remote set-url origin https://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@github.com/shliang0603/Yolov4_DeepSocial.git/

二、 常见问题
有些问题我也没有遇到过，大家共同探讨吧，我会在评论区把大家遇到的问题做个汇总！

1、如果 push 等操作没有出现输入密码选项，请先输入如下命令，之后就可以看到输入密码选项了

git config --system --unset credential.helper
————————————————
原文链接：https://blog.csdn.net/weixin_41010198/article/details/119698015



### 2.git的命令

## GIT基本操作

下面是一些日常操作

### 建立本地仓库

git init 创建本地仓库： git init [project-name]

git remote add origin git@github.com:UserName/yourProjectName.git  把本地仓库和远程仓库关联起来， 如果不执行这个命令的话，每次 push 的时候都需要指定远程服务器的地址

### 

git clone https://github.com/zhoulujun/yourProjectName.git

### **提交本地修改到远程仓库中：**

git add -- 将改动添加到本地仓库中  

- git add [file1] [file2] ... || git add [dir] 添加指定文件||目录到暂存区
- git add -A || git add .添加当前目录的所有文件到暂存区
- git add -p 添加每个变化前，都会要求确认，对于同一个文件的多处变化，可以实现分次提交

git rm xxx    -- 从本地仓库中删除指定文件

- git rm -r xxx  -- 从本地仓库中删除指定文件夹
- git rm --cached [file]
- git mv [file-original] [file-renamed] 改名文件，并且将这个改名放入暂存区

git commit -m "注释"   -- 把本机缓存中的内容提交到本机的 HEAD 里面

- git commit -a 提交工作区自上次commit之后的变化，直接到仓库区
- git commit -v 提交时显示所有diff信息
- git commit --amend -m [message] 使用一次新的commit，替代上一次提交，如果代码没有任何新变化，则用来改写上一次commit的提交信息
- git commit --amend [file1] [file2] ... 重做上一次commit，并包括指定文件的新变化

git push origin master -- 把本地的 commit(提交) push 到远程服务器上， origin 也就是之前 git remote add origin 那个命令里面的 origin，origin 替代了服务器仓库地址：git@github.com:zhoulujun/yourProjectName.git 

- git push remoteBranchName tagName提交指定tag
- git push remoteBranchName --tags 提交所有tag

### git转态查看

git status 查看状态

git branch 查看本地所有分支

- git branch -r查看远程所有分支
- git branch -a查看本地和远程所有分支

git tag 列出所有tag

git show tagName 查看tag信息

git log --stat 显示commit历史，以及每次commit发生变更的文件

### 分支操作

git checkout branchName 切换到指定分支，并更新工作区

git merge branchName 合并指定分支到当前分支

git branch newBranchName 新建一个分支，但依然停留在当前分支

git branch --track branch remote-branch 新建一个分支，与指定的远程分支建立追踪关系

git branch -D branchName //删除目标分支

git checkout -b branchName 新建并切换至新分支

git branch -d -r branchName 删除远程分支，其中

git branch -m oldbranchname newbranchname 重命名分支 使用-M则表示强制重命名

**重命名远程分支**

- git branch -m old_name new_name 重命名分支
- git checkout -b new_branch_name from_branch_name 本地建立 branch 並立即 checkout 切換過去
- git push origin –delete old_name

也可以如此操作

- git branch -m old_branch new_branch # Rename branch locally
- git push origin :old_branch # Delete the old branch
- git push --set-upstream origin new_branch 或者git push -u origin new_branch # Push the new branch, set local branch to track the new remote

## git分支与主干合并操作

### 在主干上合并分支||主干合并分支

git merge branch --squash //提交合并后的代码

git commit -m ‘合并备注’

git push //将代码推送到远程仓库

### 分支同步主干代码||在分支上合并主干

git merge master --squash //提交合并后的代码

git commit -m ‘合并备注’ //将代码推送到远程仓库

git push //将代码推送到远程仓库

## git强制覆盖本地代码

与git远程仓库保持一致

git fetch --all

git reset --hard origin/master

git pull

git强制覆盖本地命令（单条执行）：

git fetch --all && git reset --hard origin/master && git pull

## git修改远程仓库地址

方法有三种：

1.修改命令

git remote origin set-url [url]

2.先删后加

git remote rm origin

git remote add origin [url]

3.直接修改config文件

.git文件夹，找到config，编辑，把就的项目地址替换成新的。

## git 配置

git config --list     查看配置列表

git config --global user.name "xxx"  -- 配置用户名，上传本地 repository 到服务器上的时候，在 Github 上会显示这里配置的上传者信息

git config --global user.email "xxx"  -- 配置邮箱

**配置 sshkey** ： 上传代码时使用这个 sshkey 来确认是否有上传权限

  \1. 创建本地 ssh ： ssh-keygen -t rsa -C "Github 的注册邮箱"

  \2. 在 Github 中添加这个 sshkey ： 

​    复制  C:\Documents and Settings\Administrator\.ssh\id_rsa.pub 文件中的内容；

​    登录 Github --> Account Setting  --> SSH-KEY --> Add SSH-KEY --> 粘贴id_rsa.pub中的内容；

  \3. 验证： ssh -T git@github.com

​    出现 Hi xxx! You've successfully authenticated, but GitHub does not provide shell access. 说明配置成功，可以连接上 Github



**使用 .gitignore 文件忽略指定的内容**：

  \1. 在本地仓库根目录创建 .gitignore 文件。Win7 下不能直接创建，可以创建 ".gitignore." 文件，后面的标点自动被忽略；

  \2. 过滤文件和文件夹： [Tt]emp/ 过滤 Temp\temp 文件夹； *.suo 过滤 .suo 文件；

  \3. 不过滤文件和文件夹： !*.c

##git 的使用报错

###1.

```
> git pull --tags origin master
From https://gitlab.hundsun.com/aiInsVideo/avs-web
 * branch            master     -> FETCH_HEAD
fatal: refusing to merge unrelated histories
```

问题描述：

当本地分支与远程分支没有共同祖先时，会出现 `fatal: refusing to merge unrelated histories` 的问题。

解决：git pull --rebase origin master

###2.

> ```
> git push origin master:master
> remote: GitLab: You are not allowed to push code to protected branches on this project.        
> To https://gitlab.hundsun.com/aiInsVideo/avs-web.git
>  ! [remote rejected] master -> master (pre-receive hook declined)
> error: failed to push some refs to 'https://gitlab.hundsun.com/aiInsVideo/avs-web.git'
> ```
>
> 问题描述：
>
> 没有权限上传到相应分支

###3.如果一个分支没有master上的内容 可以选择将master分支合并到该分支上

没有在当前分支：用 命令：git branch 查看分支

```
$ git branch

* (no branch, rebasing master)
  feature_20211220
  master
```

本次出现这个错误是因为本地提交了`commit`但是未`push`成功，所以使用`git pull --rebase`，由于远程仓库和本地的`commit`有冲突，Git无法自动解决冲突时，会切换到一个匿名分支，然后使用`git branch`发现报错“no branch, rebasing master”。

解决办法：
 在当前匿名分支下，解决完冲突，然后使用命令`git rebase --continue`，可以将代码合并到之前操作时的分支（我当时是在master分支所以后面都说master分支），执行完`git rebase --continue`后就自动回到了master分支，但是之前提交的`commit`没有在本地仓库区(Repository)了，回到了本地暂存区(Index / Stage)，这时候需要重新`commit`，之后再执行`git push origin master`就可以将变更推到远程仓库了。

今天使用 git pull和git push 命令，分别报错：

You are not currently on a branch, so I cannot use any
'branch.<branchname>.merge' in your configuration file.
Please specify which remote branch you want to use on the command
line and try again (e.g. 'git pull <repository> <refspec>').
See git-pull(1) for details.

fatal: You are not currently on a branch.
To push the history leading to the current (detached HEAD)
state now, use

    git push origin HEAD:<name-of-remote-branch>

这是什么意思呢？
说我当前不是在分支上，因此不能 pull 或者 push

然后利用git branch查看一下，发现：

git branch
* (HEAD detached from bdcfe3d8)
* master
* issue68

我当前所处的位置是在HEAD detached from bdcfe3d8上

所以进行如下操作

git branch temp bdcfe3d8
git checkout master
git merge temp

这三行命令的意思是：

依据快照bdcfe3d8 创建 temp 分支
切换到 master 分支
将 temp 分支合并到 master分支
再看一下所有的分支

git branch
* master
* issue68
* temp

这时候就可以进行 git pull 和 git push 了
记得删除 temp 分支哦

git branch -d temp



###4.提交代码到远程仓库时的报错： fatal: unable to access 'https://github.com/lerojon/FrontendTools.git/': OpenSSL SSL_read: SSL_ERROR_SYSCALL, errno 10054 

第一种方法：

第一条：这条会报错，继续下一条命令

```
git config http.sslVerify "false"
```

第二条：

```
git config --global http.sslVerify "false"
```

再次克隆会报错，那就是原先执行clone时的那份文件没删除，删除，然后重新执行git clone命令

第二种方法：

- git_bash 执行 `git config --global --unset http.proxy` 命令或`git config --global --unset https.proxy`

### 5.改变项目的仓库地址(The file will have its original line endings in your working directory)

```
此时需要执行如下代码：

  git rm -r --cached .
  git config core.autocrlf false

  git add .

. 代表当前目录
```



#*vue使用import来引入组件的注意事项



Vue使用import ... from ...来导入组件，库，变量等。而from后的来源可以是js，vue，json。这个是在webpack.base.conf.js中设置的：

```json
module.exports = {
      resolve: {
        extensions: ['.js', '.vue', '.json'],
        alias: {
          '@': resolve('src')
        }
      }
    ...
    }
```

 

这里的extensions指定了from后可导入的文件类型。

而上面定义的这3类可导入文件，js和vue是可以省略后缀的：

import test from './test.vue'  等同于： import test from './test'

同理：

import test from './test.js' 等同于：import test from './test'

json不可以省略后缀


那么，若test.vue，test.js同时存在于同一个文件夹下，则import的导入优先级是：js>vue

 from后的来源除了文件，还可以是文件夹：import test from './components'

该情况下的逻辑是：

  if(package.json存在 && package.main字段存在 && package.main指定的js存在) {
    取package.main指定的js作为from的来源，即使该js可能格式或内容错误
  } else if(index.js存在){
    取index.js作为from的来源
  } else {
    取index.vue作为from的来源
  }

因此**若from的来源是文件夹，那么在package.json存在且设置正确的情况下，会默认加载package.json；若不满足，则加载index.js；若不满足，则加载index.vue**。

注意加载文件夹的形式，与上面省略后缀的形式是完全相同的。所以**一个省略后缀的from来源，有可能是.vue，.js，或者文件夹**。

例：查看Vue-Element-Admin的源码，其中有个Layout.vue：

里面调用import导入了3个组件：

import { Navbar, Sidebar, AppMain } from './components'。 这里，from的路径'./components'就是个文件夹。

于是，按照前面的规则，首先查看文件夹下是否有package.json：

并没有package.json。

package.json不存在，那么查找index.js。index.js是存在的，于是加载。

打开index.js：

  export { default as Navbar } from './Navbar'

  export { default as Sidebar } from './Sidebar'

  export { default as AppMain } from './AppMain'

可以看到3个export，都没有后缀，所以其类型vue，js和文件夹都是有可能的。

同一级目录下，存在AppMain.vue和Navbar.vue，没有同名js，所以可以判断出这两个都是加载的vue文件，即：

  export { default as Navbar } from './Navbar.vue'

  export { default as AppMain } from './AppMain.vue'

而Sidebar只有一个文件夹，所以是加载的文件夹。打开Sidebar文件夹：

优先找package.json。不存在。然后找index.js，不存在。最后找index.vue，存在。

于是：

export { default as Sidebar } from './Sidebar'  相当于：export { default as Sidebar } from './Sidebar/index.vue'

这样，Layout.vue就通过加载一个文件夹，获得了3个vue组件。

#*npm报错

**如果使用了nvm，npm的时候报错很有可能是node的版本不对**



/AppData/Local/npm-cache/_logs

1.删除node_modules文件

2.npm cache clean --force

3.npm install

<h3>网上搜索的解决方法</h3>

出现的问题：

    npm ERR! path D:\CIM_vue\package.json
    npm ERR! code ENOENT
    npm ERR! errno -4058
    npm ERR! syscall open
    npm ERR! enoent ENOENT: no such file or directory, open 'D:\CIM_vue\package.json'
    npm ERR! enoent This is related to npm not being able to find a file.
    npm ERR! enoent
    npm ERR! A complete log of this run can be found in:
    npm ERR!    
    ..\Roaming\npm-cache\_logs\2019-09-16T01_41_51_803Z-debug.log

解决方案一：

首先初始化，再安装相应的文件

 1.  npm init -f //强迫初始化文件
 2.  npm install bluebird --save

解决方案二：

npm run dev 时报错 ，package.json找不到

也有可能是因为是没进入到文件目录里，进到文件的目录中再去npm run dev 就不会报错了！
cmd 黑窗口 cd进入项目 npm run dev 或者 打开本地项目所在文件夹，再地址栏上输入cmd 回车直接进入当前项目下。

解决方案三：

我们使用命令 npm install xxx安装包时，默认是从 npm
的的镜像源服务器进行下载的，由于该服务器是放在国外，很容易就导致安装失败。因此 我们需要修改镜像源地址。 全局安装nrm 镜源管理器
nrm里面存放了多个镜像服务器

npm install  nrm    -g
1
先清除缓存，再重新安装

npm cache clean --force
1
重新安装

npm install
1
解决方案四：

全局更新 npm

npm i npm -g 就ok了
————————————————

原文链接：https://blog.csdn.net/o_o814222198/article/details/100877846

-----------------issue

#*node-moudle 插件报错

在babel.config.js删除相应报错插件即可

#*vscode 编译报错的问题

ERROR  Failed to compile with 1 errors

    <br>This relative module was not found:




![](E:\issue_md\image\Snipaste_2021-11-18_09-01-09.jpg)





#*组件的报错

vue错误提示：Invalid default value for prop "queryRoleList": Props with type Object/Array must use a factory function to return the default value.

然后在报错的文件会自动生成引入

import func from '../../../vue-temp/vue-editor-bridge'

终端报错提示：This relative module was not found:

* ../../../vue-temp/vue-editor-bridge in ./node_modules/babel-loader/lib!./node_modules/vue-loader/lib/selector.js?type=script&index=0!./src/components/universalityComs/dialogForm.vue

解决报错：删除 import func from '../../../vue-temp/vue-editor-bridge'即可

并且props的默认值是数组的改成函数返回数组



#*element input框限制输入格式为数字

月份数，薪资、电话号码等的 input 框需要限制只能输入数字类型内容

1.实现：监听键盘输入，使用正则过滤掉其他字符

```
οninput="value=value.replace(/^\.+|[^\d.]/g,'')
```



```
<el-input   
    v-model.trim="emp_work_experience.dimission_salary" 
    placeholder="请输入薪资"   
    oninput="value=value.replace(/^\.+|[^\d.]/g,'')">
</el-input>
```

2.遇到坑：然后遇到了一个问题，当输入其他字符再输入数字的时候，输入框中显示有值，但实际去打印 v-model绑定的变量的时候就获取不到新输入值。即使用了一个函数限制输入框只能输入数字，输入其他将会被置空，在输入1时是正确的，之后我们输入一个非数字，这个非数字并被置空之后，再输入新的数字。v-model的值和value的值出现了不同，v-model无法获取到新输入的数值。

详细原理解析：（参考大佬的）

https://blog.csdn.net/qq_41635167/article/details/857369363.

3.解决：在输入框失去焦点的时候，把value值赋值给v-model绑定变量，使两者保持一致

3.解决：在输入框失去焦点的时候，把value值赋值给v-model绑定变量，使两者保持一致

```
<el-input   
    v-model.trim="emp_work_experience.dimission_salary" 
    placeholder="请输入薪资"   
    oninput="value=value.replace(/^\.+|[^\d.]/g,'')"
    @blur="salaryChange">
</el-input>
```

 

js:
//月薪改变

```
function salaryChange(e){
     this.emp_work_experience.dimission_salary = e.target.value
}
```

#*单点登录





#*[vue的watch监听函数](https://www.cnblogs.com/whx123/p/12122732.html)

在vue中，使用watch来响应数据的变化。watch的用法大致有三种。下面代码是watch的一种简单的用法：

```
1.
<input type="text" v-model="cityName"/> new Vue({
   el: '#root',
   data: {
     cityName: 'shanghai'
   },   methods:{     Namechange:function(){        .....     }
   },
   watch: {
     cityName(newName, oldName) {        console.log(newName)
        console.log(oldName)
     }
   } 
 }) 也可以直接写一个监听处理函数，当每次监听到 cityName 值发生改变时，执行函数。也可以在所监听的数据后面直接加字符串形式的方法名： watch:{   citiName:'Namechange' }
```

 **2.immediate（立即处理 进入页面就触发）** **和 handler :**

​    这样使用watch时有一个特点，就是当值第一次绑定的时候，不会执行监听函数，只有值发生改变才会执行。如果我们需要在最初绑定值的时候也执行函数，则就需要用到immediate属性。

​    比如当父组件向子组件动态传值时，子组件props首次获取到父组件传来的默认值时，也需要执行函数，此时就需要将immediate设为true。

​    new Vue({

```
     el: '#root',
     data: {
        cityName: ''
     },
     watch: {
        cityName: {
    　　   handler(newName, oldName) {
      　　    // ...
    　　   },
    　　 immediate: true        }
     } 
  })
```

  监听的数据后面写成对象形式，包含handler方法和immediate，之前我们写的函数其实就是在写这个handler方法；

  immediate表示在watch中首次绑定的时候，是否执行handler，值为true则表示在watch中声明的时候，就立即执行handler方法，值为false，则和一般使用watch一样，在数据发生变化的时候才执行handler。

 **3.deep : 深度监听**

  **当需要监听一个对象的改变时，普通的watch方法无法监听到对象内部属性的改变，只有data中的数据才能够监听到变化，此时就需要deep属性对对象进行深度监听。**

```
   <input type="text" v-model="cityName.name"/>
    new Vue({
      el: '#root',
      data: {
        cityName: {id: 1, name: 'shanghai'}
      },
      watch: {
        cityName: {
          handler(newName, oldName) {
           // ...
       },
        deep: true,
        immediate: true
      }
    })   设置deep: true 则可以监听到cityName.name的变化，此时会给cityName的所有属性都加上这个监听器，当对象属性较多时，每个属性值的变化都会执行handler。如果只需要监听对象中的一个属性值，则可以做以下优化：使用字符串的形式监听对象属性      
    watch: {
       'cityName.name': {
           handler(newName, oldName) {
          // ...
        },
        deep: true,
        immediate: true
       }
    }
```

​     这样只会给对象的某个特定的属性加监听器。数组（一维、多维）的变化不需要通过深度监听，对象数组中对象的属性变化则需要deep深度监听。

 

 

 Watch 与 computed的区别：

​    Watch：watch用于观察和监听页面上的vue实例，当你需要在数据变化响应时，执行异步操作，或高性能消耗的操作，那么watch为最佳选择

   computed ：可以关联多个实时计算的对象，当这些对象中的其中一个改变时都会触发这个属性具有缓存能力，所以只有当数据再次改变时才会重新渲染，否则就会直接拿取缓存中的数据。

# *uniapp项目出现的问题

## 1，编译问题

![](E:\issue_md\image\Snipaste_2021-12-14_15-39-41.jpg)

uniapp项目点击运行一直卡在 “开始编译...” 这一步，网上说的卸载hbx和用管理员运行均不可以。后来改用命令行‘npm run serve’ 运行直接在![](E:\issue_md\image\Snipaste_2021-12-14_15-43-02.jpg)

这里就中断了， 然后按这个在网上搜问题，原来是nodejs内存溢出的原因，修改node内存限制，重启后就好了；

查询后了解到是Node中通过JavaScript使用内存时只能使用部分内存（64位系统：1.4 GB，32位系统：0.7 GB），如果前端项目比较大，Webpack编译时就会占用很多的系统资源，一旦超出了[V8引擎](https://www.jianshu.com/p/4757158528e7)对Node默认的内存限制大小时，就会产生内存溢出的错误。
 处理方式是：在package.json中script下添加

![](E:\issue_md\image\Snipaste_2021-12-14_15-47-24.jpg)

接着执行 `npm install cross-env --save--dev`(目前这里只能使用npm)
 以及 `npm install increase-memory-limit --save--dev`
 如果安装失败则需要先删除掉项目的node_modules包
 配置并安装成功后执行`npm run fix-memory-limit`这句，成功则会出现一下界面

![](E:\issue_md\image\Snipaste_2021-12-14_15-48-07.jpg)

引用：https://www.jianshu.com/p/9c60b283bb49



## 2.window下 NODE_ENV 环境变量的设置

方法：

**使用插件cross-env**

```
npm install cross-env
```

在package.json中加入 ```"start": "cross-env NODE_ENV=development node your-app-name.js"``

在cmd再

```
npm start
```

之后在node文件中，看一看相关的应用到判断环境变量再执行的代码



```
if (process.env.NODE_ENV === 'development') {
  
}
```


作者：liyuanzhe-cn
链接：https://juejin.cn/post/6844903838604869646



# *请求接口url报错相关

##接口地址错误的问题

![](E:\issue_md\image\Snipaste_2021-12-17_15-15-57.jpg)

![](E:\issue_md\image\Snipaste_2021-12-17_15-17-10.jpg)

![](E:\issue_md\image\Snipaste_2021-12-17_15-18-49.jpg)

![](E:\issue_md\image\Snipaste_2021-12-17_15-19-08.jpg)

怀疑是编译器的问题，代码都没有问题

# *VSCode 编译器

## 1.输入元素 提示带abc 的 而不是一个扳手图标的问题

快捷键：Alt + W 设置

## 2.格式化配置不生效的问题

选择默认格式化插件Vetur即可

![](E:\issue_md\image\Snipaste_2021-12-29_15-17-56.jpg)

![](E:\issue_md\image\Snipaste_2021-12-29_15-18-19.jpg)

# *element组件的问题

## vue+element el-select 选项无法选择的问题

出现这个问题就是绑定了对象（需求如此），render函数没有自动更新，数据刷新了，但是视图没有刷新，而this.$ste和this.$forceUpdate就是重新render。

解决办法：

1.通过this.$set()解决

Change(item){

​    ~~**this.$set(this.form.customs.businessType)**~~

​    console.log(item);

   },

###注意,修改this.$set()的使用方法

> 对this.$set()方法进行了多次尝试,发现存在bug
>
> 正确的写法应该是:
>
> Change(item){    this.$set(,,item)    console.log(item);   }, 
>
> 向this.$set() 里传入3个参数, 第一个是包裹字段的**父级对象**, 第二个是**目标字段**, 第三个是将要**赋值给目标字段的数据**

2.通过 this.$forceUpdate()解决

Change(item){

​    this.$forceUpdate()；

​    console.log(item);

   },

作者：风雨兼程620
链接：https://www.jianshu.com/p/bbbea54697ea
来源：简书

# *关于接口请求URL的问题

## 1.如果请求的基础路径没有带http://那么在浏览器的开发者模式中的Network 看到下面的url

![](E:\issue_md\image\Snipaste_2022-01-24_16-40-32.jpg)

```
Request URL: 

http://localhost:8090/172.27.28.196:19090/setting/product/queryAll
```

#*[window.open新打开窗口与新开标签页](https://www.cnblogs.com/wonyun/p/5284163.html)

最近在使用window.open时忽略了一个细节问题：window.open新打开一个窗口，但是有时却是新打开一个窗口有时打开一个新标签页。虽然对一般的需求来说，这个两种情况都无所谓，但是对于那种有强烈区分的需求来说还是要注意的。那么怎么会出现这种不同的打开情况呢，这要从window.open方法的用法和不同浏览器来区分。

------

###  1、window.open的用法容易忽视的细节

 window.open方法有三个参数：　　

```
window.open(url, [name], [configuration])
```

其中：

- url， 为要新打开页面的url
- name，为新打开窗口的名字，可以通过此名字获取该窗口对象
- configuration，为新打开窗口的一些配置项，比如是否有菜单栏、滚动条、长高等等信息

例如，新打开一个没有菜单栏、标题栏、工具栏，但是有滚动条、状态栏、地址栏且可伸缩窗口的方法调用如下：

```
window.open("index.html","newWindow","menubar=0,scrollbars=1, resizable=1,status=1,titlebar=0,toolbar=0,location=1");
```

以上只是简要描述了window.open的方法，但是这个方法容易忽略的地方就是：**新打开窗口名字可以是自定义的值，此外还可以是以下几个值，与超链接a的target属性值相同**

| **窗口name值** | **描述**                      |
| -------------- | ----------------------------- |
| _blank         | 默认的，在新窗口打开链接的url |
| _self          | 在当前窗口打开链接url         |
| _parent        | 在父窗口打开链接url           |
| _top           | 在顶级窗口打开url             |
| framename      | 在指定的框架中打开链接url     |

### 2、window.open打开新窗口还是打开新标签页

 调用window.open是打开新窗口，还是打开新标签页，其实没有什么要紧关系，但是有些需求在这方面有很强的意愿时，那就得区分一下了。具体的打开什么还是根据具体情况来定的，以下结论是经过本人测试得出的，若有不正确的地方，请大家批评指正。

1、window.open(url)或者window.open(url, name),其中name为_blank

- 标准浏览器、IE9+是新标签打开链接url
- ie6-8是新窗口打开链接url

2、window.open(url, name)，其中name为非_blank的其他4个值

　　此时会会在指定窗口或者frame打开链接url

3、window.open(url, name, configration)

　　**只要配置了configration，所有浏览器都是新窗口打开链接url**

 

### 3、使用window.open方法打开的窗口可能被拦截的替代方案

 现在有些浏览器为了安全起见，可能会阻止window.open打开的链接url，不管是以标签还是以窗口打开。这时可能需要用户进行浏览器设置允许弹新页，让用户设置浏览器是极不可取的做法，尤其像电商类网站，那么有其他替代方案呢？

答案当然是有的，**利用超链接打开的url是不会被拦截的可以实现这一点**。具体做法是结合事件手动触发机制。下面是  [HTML：模拟链接被按下，在新标签页打开页面，不使用window.open(可能被拦截)](http://www.cnblogs.com/0banana0/p/3566347.html) 这篇博客给的一个简单的实例，这篇文章给出的事件分发机制是针对标准浏览器的：

```
html>
<head>
    <meta http-equiv="Content-type" content="text/html; charset=utf-8">
    <title>Title</title>

    <script src="jquery.js"></script>
    <script type="text/javascript">
    $(function() {
        $("#btn").click(function() {
            //var a = $('a')[0];
            var a = $("<a href='http://www.apple.com' target='_blank'>Apple</a>").get(0);
            
            var e = document.createEvent('MouseEvents');
            e.initEvent( 'click', true, true );
            a.dispatchEvent(e);
        });
    });
    
    </script>
</head>

<body>
    <input type="button" value="Go to Apple" id="btn">
</body>
</html>
```

#*webpack打包问题

###1.关于静态文件路径的问题

可根据实际情况自行设定

*如果你计划在子路径下部署你的站点，你需要设置这个参数，

*例如GitHub页面。如果您计划将站点部署到https://foo.github.io/bar/，

*那么assetblicpath应该设置为“/bar/”。

*大多数情况下请使用“/”!!

```
build: {
    // Template for index.html
    index: path.resolve(__dirname, '../dist/index.html'),

    // Paths
    assetsRoot: path.resolve(__dirname, '../dist'),
    assetsSubDirectory: 'static',
    assetsPublicPath: '/',  //打包出来的静态js css html 的路径地址是 http://...... /static/js、css、html/这样的
    assetsPublicPath: './',  //打包出来的静态js css html 的路径地址是 http://......  ./static/js、css、html/这样的
    assetsPublicPath: '/abc',  //打包出来的静态js css html 的路径地址是 1.期望的地址http://......  /abc/static/js、css、html/...这样的
    2.事实打包放服务器上的地址： http://......  /abcstatic/js、css、html/...   添加的路径与static没有斜杆分割
    assetsPublicPath: '/abc/',  //打包出来的静态js css html 的路径地址是 http://......  /abc/static/js、css、html/...这样的
   
```

注意：![](E:\issue_md\image\Snipaste_2022-03-17_10-52-33.jpg)

这两个路径不正常的时候会在打包的时候报错，无法打包

# *命名规则

```
项目命名
      全小写-隔开  my-project-name

    文件命名:小写开头、驼峰命名
      apiUtil.html
      apiUtil.css
      apiUtil.js

    目录命名: 全小写用-分割

    css命名规范
    *小写加-分割
      1)1.位置属性(position, top, right, z-index, display, float等)
        2.大小(width, height, padding, margin)
        3.文字系列(font, line-height, letter-spacing, color- text-align等)
        4.背景(background, border等)
        5.其他(animation, transition等)
      2)属性用简写
      3)去除小数点前面0     .8rem
      4)命名全小写
        命名用-隔开  main-title
        新增前缀  is-withdraw
      2)连字符命名 main-title

    js命名规范
      *变量:小驼峰          maxCount
      *常量:全大写_隔开     MAX_COUNT
      *方法:
        小驼峰、
        前缀应当为动词(get/set/is/has/can/load)
        getData()
      类:大驼峰，首字母大写     Person
      私有属性:前缀为_         _name

    图片业务（可选） +（mod_）图片功能类别（必选）+ 图片模块名称（可选） + 图片精度（可选）
      eg:wx_btn_goodList@2x.png
```

总结：

文件夹、项目名称、文件：用小写字母加-分隔

组件：用驼峰法

变量、方法：小驼峰

常量：全大写_隔开

# *nvm与nrm的安装

安装前的注意事项：

**如果之前安装过node请先卸载之前的node后重启**

- Windows设置 --> 应用--> 找到Node-->点击卸载
- 重启电脑（或者从任务管理器中杀死所有Node相关的进程）
- 寻找以下文件夹并删除他们。根据您安装的版本，这些文件可能存在也可能不存在：
- C:\Program Files (x86)\Nodejs
- C:\Program Files\Nodejs
- C:\Users{User}\AppData\Roaming\npm（或%appdata%\npm）
- C:\Users{User}\AppData\Roaming\npm-cache（或%appdata%\npm-cache）
- 检查%PATH%环境变量，确保没有引用Nodejs和npm的存在
- 重启（重启大法解决90%问题）
- nvm安装位置，看自己决定，但是**安装路径不能有空格**



## 一、NVM

`Nvm` 可以切换 `node` 与 `npm` 版本，在开发不同项目时，可能会用到不同的 `node` 与 `npm` 版本，所以使用 `nvm` 可以方便的在不同 `node` 与 `npm` 版本之间进行切换。

### 写在前面

- 在安装 Nvm 之前，先将之前安装的 node 进行卸载。否则可能会出现无法切换 node 版本的问题
- 将之前安装的全局插件删除掉，否则可能会导致 nvm 命令不起作用。文件目录如下

```
C:\Users\Administrator\AppData\Roaming\npm
C:\Users\Administrator\AppData\Roaming\npm-cache
复制代码
```

### nvm 的安装

下载 nvm 插件，安装地址： [Github： Download nvm-windows （nvm-setup.zip）](https://link.juejin.cn?target=https%3A%2F%2Fgithub.com%2Fcoreybutler%2Fnvm-windows%2Freleases)。

下载完成，解压文件之后，双击进行安装：

- 1. 设置 

     ```
     nvm
     ```

      安装目录，这里的路径可以根据自己的需要进行填写，不要包含中文名

     ![第一步](https://p1-jj.byteimg.com/tos-cn-i-t2oaga2asx/gold-user-assets/2019/3/19/169937e724d33e5d~tplv-t2oaga2asx-zoom-in-crop-mark:1304:0:0:0.awebp)

- 1. 设置 

     ```
     nodejs
     ```

      各版本安装目录。这个目录是 

     ```
     nvm install node版本
     ```

      时存放 

     ```
     nodejs
     ```

      的目录

     ![第二步](https://p1-jj.byteimg.com/tos-cn-i-t2oaga2asx/gold-user-assets/2019/3/19/169937ebba82ce77~tplv-t2oaga2asx-zoom-in-crop-mark:1304:0:0:0.awebp)

- 1. 安装完成，在命令行输入：`nvm version`，查看到对应的版本号，说明 nvm 安装成功了。

### nvm 常用命令

- `nvm install latest`：   安装最新的 `nodejs` 版本
- `nvm install 11.12.0`：  安装对应的 `nodejs` 版本
- `nvm uninstall 11.12.0`：卸载对应的 `nodejs` 版本
- `nvm list available`：   列出所有可用的 `nodejs` 版本
- `nvm list`：             查看 `nvm` 列出已经安装的 `nodejs` 版本
- `nvm use 11.12.0`：      使用对应的 `nodejs` 版本
- 更多命令在命令行输入 `nvm` 即可查看

### 常见问题

- 提示 nvm 不是内部或外部命令的问题

  - 将之前 npm 安装的全局包删除掉。文件目录如下：

  ```
  C:\Users\Administrator\AppData\Roaming\npm
  C:\Users\Administrator\AppData\Roaming\npm-cache
  复制代码
  ```

- nvm 切换 node 版本无效的问题

  - 卸载原来安装的 node 版本与全局安装的包

- nvm 下载速度慢的问题

  - 在 nvm 安装目录下找到 `settings.txt` 文件，添加下面两行代码：

  ```
  root: D:\DevTools\NVM\nvm
  path: D:\DevTools\NVM\nodejs
  + node_mirror: https://npm.taobao.org/mirrors/node/
  + npm_mirror: https://npm.taobao.org/mirrors/npm/
  复制代码
  ```

------

## 二、NRM

在使用 npm 的过程中，可能插件安装速度比较慢，我们可能会使用淘宝源对插件进行下载安装。或者在公司内部，有一些私有的插件，需要使用公司的源才可以下载。这种情况，我们就需要设置不同的源来进行下载。每次手动设置相对比较麻烦。而 nrm 可以很好的解决这个问题。

### nrm 的安装

```
# 全局安装 nrm
$ npm install nrm -g
复制代码
```

安装完成后，输入命令 `nrm ls`，可以看到默认已经有了 6 个源（带 * 号的为当前使用的源）

```
* npm ---- https://registry.npmjs.org/
  cnpm --- http://r.cnpmjs.org/
  taobao - https://registry.npm.taobao.org/
  nj ----- https://registry.nodejitsu.com/
  npmMirror  https://skimdb.npmjs.com/registry/
  edunpm - http://registry.enpmjs.org/
复制代码
```

输入 `nrm use taobao`，即切换 registry 到 taobao，即可使用淘宝的源进行插件的安装下载了。

### nrm 常用命令

- `nrm ls`              ：查看所有配置好的源以及对应名称
- `nrm add company http://npm.xxx.cn`：添加源，`company` 是名称，可以自行命名，后面是源的 `url` 地址
- `nrm del company`     ：删除源，根据名称 `company` 可以删除对应的源
- `nrm test [registry]` ：测试源的速度，不加对应的 `registry` 名称，测试所有源的速度，添加对应的名称，比如 `company`，就是测试 `company` 对应的源的速度
- `nrm use company`     ：切换源，即可使用 `company` 对应名称的源
- 更多命令在命令行输入 `nrm` 即可查看

FAQ：工具 - nrm ls 不带星（*）并且 nrm current 没有任何输出

执行以下命令，通过源码安装 `nrm`

```
$ npm install Pana/nrm -g 
```

验证：

```
$ nrm ls
* npm ---------- https://registry.npmjs.org/
  yarn --------- https://registry.yarnpkg.com/
  tencent ------ https://mirrors.cloud.tencent.com/npm/
  cnpm --------- https://r.cnpmjs.org/
  taobao ------- https://registry.npmmirror.com/
  npmMirror ---- https://skimdb.npmjs.com/registry/

$ nrm current
You are using npm registry.
```

------



## 三、额外知识点

- 安装 cnpm：`npm install -g cnpm --registry=https://registry.npm.taobao.org`
- 设置 npm 全局包的安装路径（如果不想自己控制路径就不需要做下面这些操作）：
  - 执行命令：`npm config set prefix "D:\DevTools\Nvm\npm-global"`
  - 设置环境变量：将 Path 中： `C:\\Users\\Administrator\\AppData\\Roaming\\npm` 修改为 `D:\\DevTools\\Nvm\\npm-global`
- 查看已经安装的全局包：`npm ls -g --depth=0`
- 手动设置 npm 源
  - `npm config get registry`                                 ： 查看 npm 当前源
  - `npm config set registry https://registry.npm.taobao.org/`：设置 npm 源为淘宝
  - `npm install --registry=https://registry.npm.taobao.org`  ：使用特定源安装所有依赖的包
  - `npm install express --registry=https://registry.npm.taobao.org`：使用特定源安装 express 包

------

## 四、参考链接

- [Windows 下安装 nvm 管理 nodejs 版本](https://link.juejin.cn?target=https%3A%2F%2Fsegmentfault.com%2Fa%2F1190000007612011)
- [npm源管理器nrm使用教程](https://link.juejin.cn?target=https%3A%2F%2Fsegmentfault.com%2Fa%2F1190000017419993)


作者：暖生
链接：https://juejin.cn/post/6844903799530733582
来源：稀土掘金
著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。
