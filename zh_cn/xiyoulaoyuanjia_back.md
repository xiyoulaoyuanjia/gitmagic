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