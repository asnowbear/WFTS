
### 列出全部文件 - ls

### 列出全部文件，带隐藏 - ls a

### 删除文件 rm -rf .git

### 修改host

sudo vi /etc/hosts

i: 允许编辑
esc：退出编辑
：wq 保存并退出


Mac中host设置方法
开发时，一般数据测试都是在测试环境，这是就需要设置host指向测试数据库；下面我记录三个方法，也是网上看到的，在此做下笔记。

1.通过 vi 编辑host

方法如下：

   （a）打开终端，输入如下命令：

           sudo vi /etc/hosts

   （b）输入密码（登陆电脑的密码）

   （c）在终端会显示一些数据，关于host介绍；如果最后一行显示为more时，按回车键，就可以看到一些编辑命令；

     分别有：open  edit  recover  delete  quit；

     这里输入 E，进入编辑；进入编辑界面后，输入  i   进行插入；完成插入后按ESC键，再输入  :wq  进行保存；