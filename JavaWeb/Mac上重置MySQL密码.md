1. ## 关闭mysql服务器

```mysql
sudo /usr/local/mysql/support-files/mysql.server stop
```

也可以在系统偏好里有个MySQL里关闭。

2. 更改安全级别

```mysql
$ cd /usr/local/mysql/bin
$ sudo ./mysqld_safe --skip-grant-tables
```

3. 新建Terminal窗口改root密码

```
$ cd /usr/local/mysql/bin
 
$ ./mysql -u root
 
$mysql> FLUSH PRIVILEGES;
 
//8.0之前的版本
$mysql> set password for 'root'@'localhost' = password('新的密码');
//8.0+版本
$mysql> ALTER USER 'root'@'localhost' IDENTIFIED by '你的新密码';
 
$mysql> EXIT
```

