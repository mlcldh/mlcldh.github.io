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

兼容iOS7以下的api：

```objective-c
- (nullable NSString *)stringByAddingPercentEscapesUsingEncoding:(NSStringEncoding)enc API_DEPRECATED("Use -stringByAddingPercentEncodingWithAllowedCharacters: instead, which always uses the recommended UTF-8 encoding, and which encodes for a specific URL component or subcomponent since each URL component or subcomponent has different rules for what characters are valid.", macos(10.0,10.11), ios(2.0,9.0), watchos(2.0,2.0), tvos(9.0,9.0));
```

例子：

```objective-c
NSString *string = @"汉字666";
NSString *encodeString = [string stringByAddingPercentEscapesUsingEncoding:NSUTF8StringEncoding];
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

兼容iOS7以下的api：

```objective-c
- (nullable NSString *)stringByReplacingPercentEscapesUsingEncoding:(NSStringEncoding)enc API_DEPRECATED("Use -stringByRemovingPercentEncoding instead, which always uses the recommended UTF-8 encoding.", macos(10.0,10.11), ios(2.0,9.0), watchos(2.0,2.0), tvos(9.0,9.0));
```

例子：

```objective-c
NSString *decodeString = [encodeString stringByReplacingPercentEscapesUsingEncoding:NSUTF8StringEncoding];
```

## 总结

很多文章都说上面的URL编解码新api在iOS 9.0以上使用，其实他们可能看到9.0就以为iOS 9.0以上才能使用，或者看到老api9.0以上不能用就反推新api再iOS 9.0以上才可用，其实苹果文档里写的新api是tvos(9.0)🤣，而ios是7.0。所以，看文档要仔细哦😃，以官方文档为准。

