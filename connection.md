---
layout: subpage
title: Woodpecker Connection
---


**App that installed Woodpecker will search Mac client in the same network, and connect to them automatically.**<br/>
**You could make some options to specify which client you'd like to connect.**

 -  **Host Name** (Recommended), such as "David's MacBook" or "David" (Don't forget the quotation marks when contains whitespace character)
 -  **Host Address**, such as 192.168.1.101:9999
<br/>


**How to set：**

Open your Xcode project, and navigate to **Target > Edit Scheme > Run > Arguments**

![][1]

You could set the following parameters：

 -  **ADHHostName**,  your hostname, such as "David" (**You can find it at Woodpecker's Help - Client Info Menu**)
 -  **ADHHostAddress**,  your host address，such as "192.168.1.101:9999"    
 -  **ADHAutoConnectEnabled**,  whether automatically connect during the app launch，default YES
 -  **ADHShowOnConnectionFailed**,  whether show the setting page when connection failed, default YES (You could show the page manually by two finger long pressing the screen)
<br/>

> **Tips：**<br/>
1. Don't forget the “-” before parameter name, and  the space character between name and value ，such as "-ADHHostName David".<br/>
2. It only works in the Debug Scheme，other schemes such as 'AdHoc' or 'InHouse', please see the document in the below.<br/>
3. You should make sure the 'Shared" option is not checked, or it will affects your team members` setting.

<br/>
**If you need to use Woodpecker not only in debug mode, and need to set the options, please do the following during app launch:**

Objective C
```
#import "WoodPeckeriOS/WoodPeckeriOS.h"

- (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions {
    //host name
    [[NSUserDefaults standardUserDefaults] setObject:@"David" forKey:kADHHostName];
    //host address
    [[NSUserDefaults standardUserDefaults] setObject:@"192.168.1.101:9999" forKey:kADHHostAddress];
    //enable auto connect
    [[NSUserDefaults standardUserDefaults] setObject:[NSNumber numberWithBool:YES] forKey:kADHAutoConnectEnabled];
    //not show setting page when failed
    [[NSUserDefaults standardUserDefaults] setObject:[NSNumber numberWithBool:NO] forKey:kADHShowOnConnectionFailed];
}
```

Swift

```
import WoodPeckeriOS

func application(_ application: UIApplication, didFinishLaunchingWithOptions launchOptions: [UIApplicationLaunchOptionsKey: Any]?) -> Bool {
    //host name
    UserDefaults.standard.set("David", forKey: kADHHostName)
    //host address
    UserDefaults.standard.set("192.168.1.101:9999", forKey: kADHHostAddress)
    //enable auto connect
    UserDefaults.standard.set(NSNumber(value:true), forKey: kADHAutoConnectEnabled)
    //not show setting page when failed
    UserDefaults.standard.set(NSNumber(value:false), forKey: kADHShowOnConnectionFailed)
}
```
<br/>
**If you have the following problems during connection:**

> Mac client's status is always "waiting connect"

1. please ensure mac and app are in the same wifi.
2. please ensure WoodPeckeriOS.framework was the latest version.


If it still doesn't work, <a href="/contact.html">click here</a>.

<br/>
<br/>

  [1]: /assets/img/scheme.png

