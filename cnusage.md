---
layout: subpage
title: WoodPecker使用
---


<h3 class="index-h3">感谢使用 WoodPecker！</h3>

您只需要将WoodPeckeriOS.framework导入您的项目，WoodPeckeriOS.framework 会自动启动，并尝试连接Mac客户端


**CocoaPods:**

```
pod 'WoodPeckeriOS', '~> 1.0.0'
```

**手动集成:**

1. 下载 <a href="/assets/framework/WoodPeckeriOS.framework.zip">WoodPeckeriOS.framework</a>
2. 导入 WoodPeckeriOS.framework 到您的项目


您可以下载 <a href="https://github.com/github-xiaogang/woodpecker-demo">Demo</a>


```
WoodPecker使用Bonjour服务来查找Mac客户端的IP和端口号，然后通过socket连接。当然你也可以手动设置Mac端IP，或者关闭自动自动连接行为（使用双指长按屏幕任意位置打开设置界面）
WoodPecker Mac端目前使用固定端口9999
```