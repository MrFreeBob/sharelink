1.使用 yum 安装 MySQL：
====
    yum install mysql-server -y

安装完成后，启动 MySQL 服务：
    service mysqld restart

此实验使用 mysql 默认账户名和密码，您也可以设置自己的 MySQL 账户名和密码：
，参考下面的内容：

    /usr/bin/mysqladmin -u root password 'XS713eqK'

将 MySQL 设置为开机自动启动：
    chkconfig mysqld on

2.安装 Apache 组件
====
    yum install httpd -y

安装之后，启动 httpd 进程
    service httpd start

把 httpd 也设置成开机自动启动：
    chkconfig httpd on

3.安装 PHP
====

#### 使用 yum 安装 PHP：
    yum install php php-fpm php-mysql -y

#### 安装之后，启动 PHP-FPM 进程：
    service php-fpm start

#### 启动之后，可以使用下面的命令查看 PHP-FPM 进程监听哪个端口 ：
    netstat -nlpt | grep php-fpm

#### 把 PHP-FPM 也设置成开机自动启动：
    chkconfig php-fpm on


4.安装 Discuz
====

CentOS 6 没有Discuz 的 yum 源，所以我们需要下载一个Discuz 压缩包：

    wget http://download.comsenz.com/DiscuzX/3.2/Discuz_X3.2_SC_UTF8.zip

下载完成后，解压这个压缩包

    unzip Discuz_X3.2_SC_UTF8.zip

5.配置 Discuz
====

由于PHP默认访问 /var/www/html/ 文件夹，所以我们需要把upload文件夹里的文件都复制到 /var/www/html/ 文件夹

    cp -r upload/* /var/www/html/

给 /var/www/html 目录及其子目录赋予权限

    chmod -R 777 /var/www/html

**重启 Apache**

    service httpd restart
    
    mysql> CREATE USER 'username'@'host' IDENTIFIED BY 'password';
