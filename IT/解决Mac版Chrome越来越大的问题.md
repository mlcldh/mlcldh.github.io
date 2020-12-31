# 解决Mac版Chrome越来越大的问题

## 原因

Mac版Chrome用过一段时间后，它的体积成倍地增长。

这个是因为版本更新引起的，Chrome浏览器一直以来，更新后，老版本的文件夹是不会删除的，所以体积越来越大。

在Mac里，也是可以删除旧版本的。

## 解决办法

首先右击Chrome - 选项 - 在访达中显示，找到Google Chrome，然后右键，选“显示包内容”，在路径/Contents/Frameworks/Google\ Chrome\ Framework.framework/Versions下面会发现很多的文件夹，看一下自己的Chrome浏览器的版本，把其它的文件夹都删掉。

现在我的Chrome版本是87.0.4280.88，不同版本的Versions文件夹位置可能会不一样。

