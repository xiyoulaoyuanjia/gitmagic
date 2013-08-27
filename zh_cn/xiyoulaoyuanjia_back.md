**从本地开始git项目 并 同步到 github 中**

>*  git init    

_这里开始一个项目了_

>* 在这里可以 进行 add commit 等一系列的本地化工作，当项目写的差不多时可以考虑同步到 github中(参看下面) 

>*  git remote add origin git@github.com:username/repository

_注意这里最好取 ssh 方式连接。。http 每次输入密码确实挺累的_

>*  git push origin master  

_这里需要注意谁前谁后的问题_

**fork 后 保持 与源代码同步**

>* 1. 在 github 中点fork 后 会在自己的 respositories中复制一份代码
>* 2.  克隆一份代码到本地：git clone git@github.com 
>* 3. 则此时 自己远程的代码名称origin 本地为 master  给 原始 代码起一个别名为  upstream 
    git remote add upstream git://github.com
>* 4. 则 同步远程代码命令为   git fetch stream 

**Create a new branch with git and manage branches**

[Create a new branch with git and manage branches](https://github.com/Kunena/Kunena-2.0/wiki/Create-a-new-branch-with-git-and-manage-branches)

**创建一个完全干净(不会默认把现存的文件加入到新建立的分支里面)的分支方法**

>* 例如github page 中的应用 gh-pages 分支

>*  

    git checkout --orphan branchname
    git rm -rf .


**只git 代码仓库的某一个分支**

    git clone -b <branch> <remote_repo>

>* 例如:

    git clone -b mirror git@github.com:xiyoulaoyuanjia/sAoccec.git ossec-mirror


**fatal: Not a valid object name: 'master'.**

如果git init 之后直接 git branche 则会出现上面的问题。此时应该commit一次 则可正常


**如何将本地git仓库中所有的分支push到远程中**

考虑可以使用 

    git push -u origin_bitbucket --all 
命令,注意上述命令中 origin_bitbucket  是使用 git remote add 添加的远程分支.
关于 push的 -u 命令参数.注意这里 git push -u 参数的使用.  默认的上游仓库(upstream repository)。
每个项目至少有一个它追踪(track)的上游(upstream)仓库，通常情况 origin 就是用来表示它。
你可以用 ”｀git branch -r`“ 命令查看上游仓库(upstream repository)里所有的分支，
再用 origin/name-of-upstream-branch 的名字来抓取(fetch)远程追踪分支里的内容。
换句话说 可以简单理解为 upstream 是一个指针,指向默认得remote地址.




**github中错误的提交了一次,导致本地push发生错误**
```
error: failed to push some refs to 'https://github.com/lizherui/spider_python.git'
To prevent you from losing history, non-fast-forward updates were rejected
Merge the remote changes (e.g. 'git pull') before pushing again.  See the
'Note about fast-forwards' section of 'git push --help' for details.
```

后来查看了 --force 命令 

```
Usually, the command refuses to update a remote ref that is not an ancestor of the local ref used to overwrite it. This flag disables the check. This
           can cause the remote repository to lose commits; use it with care.

```






