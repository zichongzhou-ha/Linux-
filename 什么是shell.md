## 什么是shell
1.感性认识
- 张三通过媒婆与如花相亲，但是如花通过媒婆向如花表示拒绝。
- 在这个过程中，张三：用户，媒婆：shell，如花：操作系统

- shell的意义：人不善于打交道，所以得通过shell，同时，也变相保护了如花(操作系统)

2.shell是抽象的概念
- Shell 是外壳的统称--媒婆
例如 bash 就是centos7的外壳具体名称--王婆

3.shell的作用
- 执行命令，通过派生子进程的方式执行用户的指令，但shell本身并不执行命令，
- 让用户能与操作系统进行交互，同时也保护了操作系统。
- 为啥说保护了操作系统，因为当我们执行错误的指令时，shell会进行识别验证。
- shell饰演了命令行解释器，但又不仅仅是命令行解释器。

4.linux下的命令行解释程序和windows下的图形化界面是兄弟关系
- 其实，windows下的图形化界面本质也是一种外壳程序，但不是说它的底层是linux内核，而是说，它也扮演着用户与操作系统中间的关系

5.我们一直说的linux，指的是linux内核(操作系统)以及shell外壳程序，所谓的安卓，其实就是基于linux内核，再来编写一套适合手机的shell图形化的外壳程序而鸿蒙内核也是包含了linux内核，但对于shell外壳进行了一定的修改
