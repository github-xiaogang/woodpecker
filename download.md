---
layout: subpage
title: Woodpecker Usage
---


<h3 class="index-h3">Thanks for using Woodpecker！</h3>

To use Woodpecker, you need import WoodPeckeriOS.framework to your project.


**CocoaPods:**

```
pod 'WoodPeckeriOS'
```

**Manual Setup:**

1. Download <a href="/assets/framework/WoodPeckeriOS.framework.zip">WoodPeckeriOS.framework</a>
2. Import WoodPeckeriOS.framework to your Project.


Once you have imported WoodPeckeriOS.framework to your project, please start Woodpecker App, WoodPeckeriOS.framework will automatically startup and connect to mac client. 

You can start with Demo App <a href="https://github.com/github-xiaogang/woodpecker-demo">Download</a>


```
Woodpecker using bonjour service to find mac client`s IP and port, then it connect to mac client using socket automatically.
If you want manually setup the IP or need stop the automatic connection, just long press you app using two finger to show the connection page,
you can search mac client or manually setup the IP and port.
```