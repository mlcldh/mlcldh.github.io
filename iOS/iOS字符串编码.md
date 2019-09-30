# iOS字符串编码

## URL编码

api接口文档，iOS7及以上可用：

```objective-c
- (nullable NSString *)stringByAddingPercentEncodingWithAllowedCharacters:(NSCharacterSet *)allowedCharacters API_AVAILABLE(macos(10.9), ios(7.0), watchos(2.0), tvos(9.0));
```

```objective-c
@property (class, readonly, copy) NSCharacterSet *URLQueryAllowedCharacterSet API_AVAILABLE(macos(10.9), ios(7.0), watchos(2.0), tvos(9.0));
```

例子：

```objective-c
NSString *string = @"汉字666";
NSString *encodeString = [string stringByAddingPercentEncodingWithAllowedCharacters:[NSCharacterSet URLQueryAllowedCharacterSet]];
```

## URL解码

api接口文档，iOS7及以上可用：

```objective-c
@property (nullable, readonly, copy) NSString *stringByRemovingPercentEncoding API_AVAILABLE(macos(10.9), ios(7.0), watchos(2.0), tvos(9.0));
```

例子：

```objective-c
NSString *decodeString = encodeString.stringByRemovingPercentEncoding;
```

## 总结

很多文章都说上面的这些URL编解码api在iOS 9.0以上使用，其实他们看到9.0就以为iOS 9.0以上才能使用，其实苹果文档里写的是tvos(9.0)🤣，而ios是7.0。所以，看文档要仔细哦😃，以官方文档为准。

