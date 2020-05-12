### 1.1.进入谷歌云实例面板
浏览器登入 

### 1.2.切换到root角色
sudo -i 

### 1.3.修改SSH配置文件/etc/ssh/sshd_config
    vi /etc/ssh/sshd_config

修改PermitRootLogin和PasswordAuthentication为yes

###  Authentication:
    PermitRootLogin yes //默认为no，需要开启root用户访问改为yes

### Change to no to disable tunnelled clear text passwords
    PasswordAuthentication yes //默认为no，改为yes开启密码登陆

### 1.4.给root用户设置密码
    passwd root

### 1.5.重启SSH服务使修改生效
    /etc/init.d/ssh restart

### 1.6.登录
在xshell中，直接使用root账号密码登录。


### 清理本地DNS缓存

    ipconfig /flushdns
    
### 超便宜域名
[Namesilo](https://www.namesilo.com/ )
