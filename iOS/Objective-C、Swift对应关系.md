## 基础类型

| Objective-C  | Swift      |
| ------------ | ---------- |
| Int          | NSInteger  |
| Int32        |            |
|              |            |
| NSString     | String     |
| NSDictionary | Dictionary |

## 方法选择器selector

```objective-c
[editButton addTarget:self action:@selector(editButtonAction:) forControlEvents:(UIControlEventTouchUpInside)];
```



```swift
editButton.addTarget(self, action: #selector(editButtonAction(aButton:)), for: .touchUpInside)

@objc func editButtonAction(aButton: UIButton) {
        
    }
```

## GCD

#### 获取主线程

```objective-c
dispatch_get_main_queue()
```

```swift
DispatchQueue.main
```



#### 异步切换到主线程

```objective-c
dispatch_async(dispatch_get_main_queue(), ^{
        //do what you want
    });
```

```swift
DispatchQueue.main.async { [weak self] in
            //do what you want
        }
```



## 约束布局第三方库

Objective-C一般使用[Masonry](https://github.com/SnapKit/Masonry)，Swift使用[SnapKit](https://github.com/SnapKit/SnapKit)。

### 安全区域

```objective-c
[boxView mas_makeConstraints:^(MASConstraintMaker *make) {
        if (@available(iOS 11.0, *)) {
            make.left.equalTo(self.view.mas_safeAreaLayoutGuideLeft);
            make.right.equalTo(self.view.mas_safeAreaLayoutGuideRight);
            make.top.equalTo(self.view.mas_safeAreaLayoutGuideTop);
            make.bottom.equalTo(self.view.mas_safeAreaLayoutGuideBottom);
        } else {
            make.left.right.equalTo(self.view);
            make.top.equalTo(self.mas_topLayoutGuideBottom);
            make.bottom.equalTo(self.mas_bottomLayoutGuideTop);
        }
    }];
```

```swift
boxView.snp_makeConstraints { (make) in
            if #available(iOS 11, *) {
                make.left.equalTo(view.safeAreaLayoutGuide.snp.left)
                make.right.equalTo(view.safeAreaLayoutGuide.snp.right)
                make.top.equalTo(view.safeAreaLayoutGuide.snp.top)
                make.bottom.equalTo(view.safeAreaLayoutGuide.snp.bottom)
            } else {
                make.left.right.equalToSuperview()
            }
        }
```

