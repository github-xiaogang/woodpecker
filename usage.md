---
layout: subpage
title: WoodPecker Usage
---


<h3 class="index-h3">Thanks for using WoodPecker！</h3>

To use WoodPecker, you need import WoodPeckeriOS.framework to your project, WoodPeckeriOS.framework will automatically startup and connect to mac client. 

**CocoaPods:**

```
pod 'WoodPeckeriOS', '~> 1.0.0'
```

**Manual Setup:**

1. Download <a href="/assets/framework/WoodPeckeriOS.framework.zip">WoodPeckeriOS.framework</a>
2. Import WoodPeckeriOS.framework to your Project.


You can start with <a href="https://github.com/github-xiaogang/woodpecker-demo">Demo App</a>


```
WoodPecker using bonjour service to find mac client`s IP and port, then it connect to mac client using socket automatically.
If you want manually setup the IP or need stop the automatic connection, just long press you app using two finger to show the connection page,
you can search mac client or manually setup the IP and port (woodpecker use socket port 9999).
```