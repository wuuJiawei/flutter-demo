# 支付宝

> https://juejin.im/post/6844903957391736845

### Install dependencies

```
  sy_flutter_alipay:
    git:
        url: https://github.com/lishuhao/sy_flutter_alipay

```

### UrlScheme(IOS)

1. One way

![demo](https://user-gold-cdn.xitu.io/2019/10/4/16d9744ff499f893?imageView2/0/w/1280/h/960/format/webp/ignore-error/1)

2. Another way

You can also update `ios/Runner/info.plist`

```
<key>CFBundleURLTypes</key>
<array>
    <dict>
        <key>CFBundleTypeRole</key>
        <string>Editor</string>
        <key>CFBundleURLSchemes</key>
        <array>
            <string>这个就是要设置自己的urlScheme</string>
        </array>
    </dict>
</array>
```
```
<key>NSAppTransportSecurity</key>
<dict>
	<key>NSAllowsArbitraryLoads</key>
	<true/>
</dict>
```

### Use

```
import 'package:sy_flutter_alipay/sy_flutter_alipay.dart';
```
```
var result = await SyFlutterAlipay.pay(
    payInfo, // 来自后端的支付信息
    urlScheme: '你的ios urlScheme', //前面配置的urlScheme
    isSandbox: true //是否是沙箱环境，只对android有效
);
print(result);
```

### Tip

1. DON'T USE THE SIMULATOR!PLEASE USE A REAL PHONE!