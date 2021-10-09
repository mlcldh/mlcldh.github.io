### 局部消除警告的方法

```objective-c
#pragma clang diagnostic push
#pragma clang diagnostic ignored "警告名称"
// 要消息的代码块
// 被夹在这中间的代码针对于此警告都会无视并且不显示出来
#pragma clang diagnostic pop
```

### 关闭cocoPods第三方库警告

如果想关闭第一个cocoPods引入的第三方库引起的警告，可以找到Pod对应的target在编译参数中添加 -w。注意，是小写-w， 大写-W,则是显示所有警告。

### 通过Xcode取得警告名称的方法

1. 在某一个警告处，右键, reveal in log
2. [-W]开头的值

### 常用的警告名称

使用未声明的方法选择器

```objective-c
#pragma clang diagnostic ignored "-Wundeclared-selector"
```

使用弃用api声明

```
#pragma clang diagnostic ignored "-Wdeprecated-declarations"
```

弃用api实现

```objective-c
#pragma clang diagnostic ignored "-Wdeprecated-implementations"
```

弃用

```objective-c
#pragma clang diagnostic ignored "-Wdeprecated"
```

空

```objective-c
#pragma clang diagnostic ignored "-Wnonnull"
```

循环引用

```objective-c
#pragma clang diagnostic ignored "-Warc-retain-cycles"
```



```objective-c
#pragma clang diagnostic warning "-Wimplicit-retain-self"
```

内存泄漏

```
#pragma clang diagnostic ignored "-Warc-performSelector-leaks"
```

不完整的实现

```objective-c
#pragma clang diagnostic ignored "-Wincomplete-implementation"
```

函数未使用

```objective-c
#pragma clang diagnostic ignored "-Wunused-function"
```



```objective-c
#pragma clang diagnostic ignored "-Wunguarded-availability-new"
```



```objective-c
#pragma clang diagnostic ignored "-Wunguarded-availability"
```



```objective-c
#pragma clang diagnostic ignored "-Wglobal-constructors"
```



```objective-c
#pragma ide diagnostic ignored "UnavailableInDeploymentTarget"
```



```objective-c
#pragma clang diagnostic ignored "-Wstrict-prototypes"
```



```objective-c
#pragma clang diagnostic ignored "-Wobjc-protocol-method-implementation"
```

未使用的变量

```objective-c
#pragma clang diagnostic ignored "-Wunused-variable"
```

通过 `#warning`主动添加的警告

```objective-c
#pragma clang diagnostic ignored "-W#warnings"
```

字符串格式化警告

```objective-c
#pragma clang diagnostic ignored "-Wformat"
```

不兼容指针类型

```objective-c
#pragma clang diagnostic ignored "-Wincompatible-pointer-types"
```

