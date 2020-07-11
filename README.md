# **Hello-world**

**Git与GitHub**

**Git：**

大部分都会用版本控制软件，包括Git和Svn

Git是一个分布式版本控制系统，让程序员团队能够协作开发项目，Git帮助大家管理为项目所做的工作，避免一个人

所做的修改影响其他人所做的修改。你在项目中实现一个新功能的时候，Git将跟踪你对每个文件所做的修改。确定代码可行后，你将提交所做的修改，而Git将记录项目最新的状态，如果你饭了错，想撤销所做的修改，可以轻松的返回以前的任何可行状态



**GitHub：**

是用于版本控制和协作的代码托管平台，她可以让你和其他人在任何地方协同工作。GitHub可以托管各种Git版本库，并提供一个Web界面。GitHub上的项目都存储在仓库中，后者包含与项目相关联的一切：代码，项目参与者的信息，问题和bug报告等。



Github是代码托管平台，是协作的工具；而Git是版本控制工具。Git不需要联网，在本机就可以使用。当然，Git和GitHub双剑合璧，是最顺畅的。

**总结：**

从主分支Master中分出分支Feature，然后再合并merge在一起达成代码迭代更新的过程；

——————————————————————

Repository仓库的意思，即你的项目，

你想在GitHub上开源一个项目，那就必须要新建一个Repository，如果你开源的项目多了，你就拥有了多个Repositories

Issue是问题的意思，你开源一个项目，别人发现你的项目中有bug，或者那些地方 做得不好，他可以给你提个Issue，修复后就可以close



Star是星，给项目点赞的意思，但在GitHub上的点赞比微博知乎点赞难得多



Fork，分叉，别人使用该项目时，这个时候他的Github主页就多了一个项目，也就是说新增了一个分支，他可以随便修改项目，而不影响你自己的项目



Pull Request 发起请求，这个其实是基于Fork的，分支改了项目后可以申请合并到主干，主干review代码觉得可以合并就可以接受你的Pull Request，你的代码就可以优化原来的项目



Watch，你看了项目，那么以后项目更新都会第一时间收到通知



Gits如果只想单纯分享一些代码片段，那这时候Gits就派上用场了



**分支的概念：**

release分支：发布分支，从develop分支上检出。该分支用作发版前的测试，可进行简单的bug修复。如果bug修复比较复杂，可merge和develop分支后由其他分支进行bug修复。此分支测试完成后，需要同时merge到master和develop分支上



feature分支，即功能分支，从develop分支上检出，用作bug修复，bug修复完成需merge回develop分支，并将其删除。所以该分支属于临时性分支。



fix分支：补丁分支，由develop分支检出，用作bug修复，bug修复完成需merge回develop分支，并将其删除，所以该分支属于临时性分支



hotfix分支：热补丁分支。和fix分支的区别在于，该分支由master分支检出，进行线上版本的bug修复，修复完成后merge回master，并merge到develop分支上，merge完成后也可以将其删除，也属于临时性分支



Git安装后打开Git Bas，设置用户名和邮箱

```git
$ git config --global user.name "Honker"
$ git config --global user.email "your-email" 
```

`vi ~/.gitconfig`可查看设置的用户名和邮箱

```Git
[filter "lfs"]
        smudge = git-lfs smudge -- %f
        process = git-lfs filter-process
        required = true
        clean = git-lfs clean -- %f
[user]
        name = Tracyzxc7
        email = ttzcc7@163.com
```



**备注：**提交开源代码时，这里设置的姓名和邮箱会被公开，所以需要注意隐私安全的问题



GitHub网址如下：

网址：https://github.com/，需要注册账号才能使用

GitHub上连接已有仓库时的认证，是通过使用了SSH的公开秘钥认证方式进行的。公开的秘钥认证所需的SSH Key，并将其添加至GitHub

打开Git Bash运行以下命令

```
ssh-keygen -t rsa -C "your-email"
```

![image-20200711172712827](C:\Users\xiaocui.zheng\AppData\Roaming\Typora\typora-user-images\image-20200711172712827.png)



**备注：id_rsa 文件是私有密钥，id_rsa.pub是公开密钥****

****

**在GitHub中添加公开密钥，以后就可以用私有密钥进行认证了。**

为GitHub添加公钥

打开Settings-右上角账户下面找到Settings，点击进来找到SSH and GPG keys，点击Add SSH Key ，会出现Title和Key两个输入框。在Title里可以自己写一个合适的密钥名称，在Key部分黏贴id_rsa.pub文件里全部内容。



id_rsa.pub文件里的内容可在Bash命令行查看

```
cat ~/.ssh/id_rsa.pub
```

![image-20200711164334258](C:\Users\xiaocui.zheng\AppData\Roaming\Typora\typora-user-images\image-20200711164334258.png)

添加成功后会收到一封邮件；

****

完成以上步骤后，可以用私钥与GitHub进行通信，操作命令如下：

```
ssh -T git@github.com
```

![image-20200711172639702](C:\Users\xiaocui.zheng\AppData\Roaming\Typora\typora-user-images\image-20200711172639702.png)