## git的简单介绍
- 简单来说，git就是版本控制器，
- 感性认识：对于一份实验报告，进行了多次的修改，产生的不同版本都提交到上面进行简单管理，需要时就去拿自己需要的那个版本
- 但是，单纯用这样一个工具来存储这么多的数据，极其不方便，于是github和gitee应运而生。
- 自建网站->我的版本控制器,因此可以不用在客户端，就在浏览器上就可以直接操作，github是国外的，gitee是国内的。

---
**通过linux来使用git**

1. 首先，通过git clone http:(github或gitee账号的仓库的地址)
2. 成功后在你当前目录下会有.gitignore/  ,.git
- .gitignore 凡是在这个文件内部的后缀，对应的文件，不会被上传到gitee上
- 所谓的git仓库，本质就是一个目录,git里面的内容，push到远端本质就是将你的.git里面的内容同步到gitee上
- 我们在.git在的目录在执行git add . 就会将当前目录下改变的文件上传到.git目录
- 然后执行git commit -m '***'对这个文件的修改进行解释阐述
- 再执行 git push 将.git与远端仓库进行同步，从而将我们写的或修改的文件上传到远端仓库。
- 不过，如果你在远端就进行修改的话，得执行git pull意味将远端的内容拉来.git，再执行git push同步远端内容
- 常用的git指令：git add/git clone/git commit/git push/git pull/git log/git rm/git mv/git status/
