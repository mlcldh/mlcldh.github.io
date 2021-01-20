1. 暂时性：SET character_set_server=utf8 即可，一次性。

更改的话可以用以下命令：

```
alter database cdadb character set utf8;
alter table customer character set utf8;
还可以改到字段, 不过太麻烦了, 一般情况下都不会用到, 因为创建的时候多半都会设好
```

2. 永久性：需要更改配置文件

(1)打开以下文件夹

/usr/local/mysql-5.7.24-macos10.14-x86_64/support-files/

(2)新建my.cnf。可以建文本文件后直接改扩展名为cnf。用Xcode或subline打开为佳。内容如下： 

```
[mysqld]
character-set-server=utf8
[client]
default-character-set=utf8
[mysql]
default-character-set=utf8
```

(3)复制 my.cnf 到 /private/etc/

```
sudo cp /usr/local/mysql-5.7.24-macos10.14-x86_64/support-files/my.cnf /private/etc/my.cnf
```

注意：其实 /etc 是 /private/etc 的一个替身，复制到两者皆可。

(4)重启 mysql 服务器，进入mysql

```
mysql>SHOW VARIABLES LIKE '%CHAR%';
```

可以发现编码值都改为utf8。

此时重新建库建表，导入数据即可正常显示中文。

