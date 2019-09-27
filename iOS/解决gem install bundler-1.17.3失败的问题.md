终端执行gem install bundler:1.17.3会失败，前面加上sudo也不行，报/usr/bin没有写入权限

```shell
Fetching bundler-1.17.3.gem
ERROR:  While executing gem ... (Gem::FilePermissionError)
    You don't have write permissions for the /usr/bin directory.
```

解决方法和CocoaPods类似，如下：

```shell
gem install bundler:1.17.3 -n /usr/local/bin
```

