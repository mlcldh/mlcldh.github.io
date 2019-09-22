# 解决IJK在子线程执行UI的问题

[ijkplayer 地址](https://github.com/bilibili/ijkplayer)

[iOS 解决Main Thread Checker: UI API called on a background thread: -[UIApplication applicationState]](https://www.jianshu.com/p/d0516dca5286)

Xcode 9以后增加了新特性“主线程检测器(Main Thread Checker)”，这样在运行IJK时，就会报IJKSDLGLView里面，子线程获取“UIApplication的applicationState”、layer。

有些人的做法是关闭检测器，但这并没有从根本上解决问题，就应该将这些操作改成使用主线程进行操作，下面是我的做法，直接修改IJKSDLGLView的源码。

首先，增加个只在主线程操作的方法，这个方法里面就是先判断当前是否在主线程，如果是就直接执行，否则同步切换到主队列进行执行。

```objective-c
static void IJKHanleInMainThread(dispatch_block_t mainThreadblock) {
    if ([NSThread currentThread] == [NSThread mainThread]){
        mainThreadblock();
    } else {
        dispatch_sync(dispatch_get_main_queue(), ^{
            mainThreadblock();
        });
    }
}
```

其次将方法- (BOOL)isApplicationActive里面改成这样：

```objective-c
__block UIApplicationState appState = 0;
            IJKHanleInMainThread(^{
                appState = [UIApplication sharedApplication].applicationState;
            });
```

将方法- (void)displayInternal: (SDL_VoutOverlay *) overlay里面改成这样

```objective-c
IJKHanleInMainThread(^{
        [[self eaglLayer] setContentsScale:_scaleFactor];
    });
```

```objective-c
IJKHanleInMainThread(^{
            [_context renderbufferStorage:GL_RENDERBUFFER fromDrawable:(CAEAGLLayer*)self.layer];
        });
```

最后执行IJK的demo，发现子线程操作UI的那些警告就没有了。这样重新编译生成静态库。

