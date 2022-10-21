## 问题

有些情况下，我们需要获取屏幕的状态栏高度，很多人使用类似下面的宏：

```c
#define StatusBar_HEIGHT     (DEVICE_IS_FULL_DISPLAY ? 44.: 20.)
```

然而从iOS 14开始，全面屏iPhone的状态栏高度不一定是44了，比如下面就是这些设备在iOS 14.1上的状态栏高度。

| 设备                                | 状态栏高度 |
| ----------------------------------- | ---------- |
| iPhone XR/11                        | 48         |
| iPhone X/11 Pro/ 11 Pro Max/12 mini | 44         |
| iPhone 12/12 Pro/Pro Max            | 47         |

## 解决办法

根据不同系统，通过相应方法获取状态栏高度。

```objc
+ (CGFloat)statusBarHeight {
    if (@available(iOS 13.0, *)) {
        return [UIApplication sharedApplication].windows.firstObject.windowScene.statusBarManager.statusBarFrame.size.height;
    }
    return [UIApplication sharedApplication].statusBarFrame.size.height;
}
```

