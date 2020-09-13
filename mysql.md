# 第一种

**1.找到my.ini 文件**

my.ini 文件为 MySQl 设置文件， 如果你是默认的安装地址，文件在
C:\ProgramData\MySQL\MySQL Server 5.7 下
但是ProgramData 常规状态下是隐藏的

**2.设置权限认证跳过**

也就是在 [mysqld] 下 加上 skip-grant-tables

**3.重启 mysql 服务**

这里可以直接在命令行中连续输入 或者在服务里找到mysql 服务重启,重启后， 以 mysql -uroot -p 登陆会发现我们可以不需要密码就可以登陆

**4.重新设置密码**

首先先选择 mysql 数据库,然后更新 password

**5.在 my.ini 文件中去掉 加上的 skip-grant-tables**

**6.重启 mysql 服务**

**7.以新密码登陆**

# 第二种

1.首先将MySQL的服务关闭，两种方法：1，打开命令行输入net stop mysql或者net stop mysql5命令即可关闭MySQL服务。2，由于本人电脑不知为何不能这样关闭所以只能采用第二种方法，在运行窗口中输入services.msc打开服务窗口，找到mysql然后关闭

2.打开MySQL安装路径，进入到bin目录中复制路径。

3、打开命令行，输入cd E:\phpStudy\PHPTutorial\MySQL\bin回车

4，输入mysqld --skip-grant-tables然后回车，此时这个命令行就不能输入东西了，类似于卡了的状态，这时先不用管这个命令行，再打开一个新的命令行

5.打开新的命令行，输入mysql回车
 
6.输入show databases;   可以看到所有数据库说明成功登陆。
 
7、其中mysql库就是保存用户名的地方。输入 use mysql;   选择mysql数据库。
  
8.其中mysql库就是保存用户名的地方。输入 use mysql;   选择mysql数据库。

9.show tables查看所有表，会发现有个user表，这里存放的就是用户名，密码，权限等等账户信息。

10.输入select user,host,password from user;   来查看账户信息

11、更改root密码，输入update user set password=password('123456') where user='root' and host='localhost';

12.再次查看账户信息，select user,host,password from user;   可以看到密码已被修改。
