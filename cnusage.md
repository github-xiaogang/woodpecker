---
layout: subpage
title: Woodpecker使用
---


<h3 class="index-h3">感谢使用 Woodpecker！</h3>

<br/>
**Woodpecker**正在参加 **Swift Community Awards 2019** <a href="https://www.hackingwithswift.com/awards">投票</a>，您的支持对Woodpecker的持续开发特别重要，请帮忙在**Best developer tool**填写**Woodpecker**，感谢！
<br/>
<br/>
<br/>
**Woodpecker支持在真机和模拟器iOS8.0, macOS10.11 及以上使用，Objective-C and Swift.**

在开始前，您需要导入一个framework到您的项目，它会自己启动并连接Woodpecker客户端，如果您使用真机调试，请确认您的应用和Woodpecker在同一网络内。<br/><br/>
如果您正在开发Mac app，请访问<a href="/cnusagemac.html">Woodpecker for MacOS</a>


**1. CocoaPods:**

```
pod 'WoodPeckeriOS', :configurations => ['Debug']
```
如果需要更新，请使用`pod update WoodPeckeriOS`
<br/>
<br/>

**2. Carthage:**

```
binary "https://raw.githubusercontent.com/appwoodpecker/woodpecker-ios/master/WoodPeckeriOS-Carthage.json"
```
<br/>

**3. 手动集成:**

1. 下载 <a href="/assets/framework/WoodPeckeriOS.framework.zip">WoodPeckeriOS.framework</a>
2. 导入 WoodPeckeriOS.framework 到您的项目
3. 仅在Debug模式下使用，请使用<a href="/cnmanuallink.html">动态链接</a>方式

<br/>

**可能遇到的问题:**
> **dyld: Library not loaded: @rpath/WoodPeckeriOS.framework/WoodPeckeriOS
Reason: image not found**

<br/>
请参考下图将WoodPeckeriOS.framework拖拽到`Build Phases -> Embed Framworks`中。

<img src="/assets/img/embedframework.png"/>
<br/>
<br/>
> **Mac端状态一直是waiting connect，连接不上**

1. 确认App和Mac在同一wifi下
2. 请确认App集成的WoodPeckeriOS.framework版本为最新版
3. 尝试手动连接Mac客户端，双指长按iOS App界面任意位置弹出连接界面，点击底部搜索找到Mac，然后连接即可
4. 如果仍然有问题，<a href="/cncontact.html">请点击这里</a>

<br/>
> **经常连接到其他人电脑**

你可以设置只连接特定的电脑，<a href="/cnconnection.html">查看更多设置</a>

<br/>
> **Xcode 10 Archive 失败 (i386 bitcode 问题)**

1. 请使用仅支持真机的framework <a href="/assets/framework/WoodPeckeriOS_device.framework.zip">WoodPeckeriOS_device.framework</a>, 注意这个framework不支持模拟器设备，大多数情况下建议您使用上面的版本。

<br/>
您可以下载 
<a href="https://github.com/appwoodpecker/woodpecker-ios">
	<img src="/assets/img/logo_github.png" width="16" heigh="16"/> demo
</a> 立即体验，或者加入 
<a href="https://join.slack.com/t/woodpeckerapp/shared_invite/enQtNjMzMTY3MDczMDA4LTM4NTQ5OGRjMTIxZWMxMDdmZmVlNjQ4NjRhZmQ3YTE0NzFkMDBmNGE5NmE2MzRjMjYzZjk2Yzk5OGNjNDUwMTM">
	<img src="/assets/img/logo_slack.png" width="16" heigh="16"/> slack群
</a> 开始讨论
<br/>
<br/>
<br/>









