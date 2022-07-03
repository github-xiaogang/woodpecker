---
layout: subpage
title: Woodpecker连接
---


**集成了Woodpecker framework的App在启动时，会查找同一网络环境内的Woodpecker客户端，并尝试自动连接。**<br/>
**您可以通过设置，让App只连接特定的电脑：**

 -  **电脑名称（推荐）** ，例如设置为 “李雷的Mac”，或者“李雷” (如果包含空格，需要添加双引号"")
 -  **IP地址**，例如 192.168.1.101:9999
<br/>
**设置方法：**

在Xcode项目的**Target > Edit Scheme > Run > Arguments**

![][1]

设置如下参数：

 -  **ADHHostName**  电脑名 如“李雷”（**可以在Woodpecker菜单 Help - Client Info找到**）
 -  **ADHHostAddress**  ip和端口，如“192.168.1.101:9999”    
 -  **ADHAutoConnectEnabled**  是否自动连接，默认YES，自动连接
 -  **ADHUIGestureEnabled**  是否支持手势，默认YES，双指长按展示链接页面
<br/>

> **注意：**<br/>
1. 设置参数时前面需要添加 “-”，参数名和值之间添加空格，例如： “-ADHHostName 李雷”<br/>
2. 该设置仅在Debug Scheme下有效，其他Scheme比如AdHoc或InHouse，请参见下面设置<br/>
3. 确保Debug Scheme底部的Shared选项未勾选（默认Debug Scheme未选中），避免影响合作同事的设置

<br/>
**如果您需要在非Debug模式使用Woodpecker，并希望设置连接参数，请在应用启动时设置如下：**


Objective C
```

- (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions {
    //主机名
    [[NSUserDefaults standardUserDefaults] setObject:@"李雷" forKey:@"ADHHostName"];
    //主机地址
    [[NSUserDefaults standardUserDefaults] setObject:@"192.168.1.101:9999" forKey:@"ADHHostAddress"];
    //启动时是否自动连接
    [[NSUserDefaults standardUserDefaults] setObject:[NSNumber numberWithBool:YES] forKey:@"ADHAutoConnectEnabled"];
}
```
Swift


```

func application(_ application: UIApplication, didFinishLaunchingWithOptions launchOptions: [UIApplicationLaunchOptionsKey: Any]?) -> Bool {
    //主机名
    UserDefaults.standard.set("李雷", forKey: "ADHHostName")
    //主机地址
    UserDefaults.standard.set("192.168.1.101:9999", forKey: "ADHHostAddress")
    //启动时是否自动连接
    UserDefaults.standard.set(NSNumber(value:true), forKey: "ADHAutoConnectEnabled")
}   
```
<br/>

**可能遇到的问题:**
```
Mac端状态一直是waiting connect，连接不上
```
1. 确认您的App和Wooodpecker客户端在同一网络环境
2. 确认您的App集成的Framework为最新版本

如果还有问题，<a href="/cncontact.html">请点击这里</a>

<br/>
<br/>


  [1]: /assets/img/schemecn.png


