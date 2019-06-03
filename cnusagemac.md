---
layout: subpage
title: Woodpecker MacOS使用
---


<h3 class="index-h3">感谢使用 Woodpecker！</h3>

**Woodpecker支持在真机和模拟器iOS8.0和MacOS10.11及以上使用，Objective-C and Swift.**

您只需要将WoodpeckerMacOS.framework导入您的项目，WoodpeckerMacOS.framework 会自动启动，并尝试连接Woodpecker客户端
（使用真机时，请确认您的应用和Woodpecker在同一网络内）


**1. CocoaPods:**

```
pod 'WoodpeckerMacOS', :configurations => ['Debug']
```
如果需要更新，请使用`pod update WoodpeckerMacOS`
<br/>
<br/>

**2. Carthage:**

```
binary "https://raw.githubusercontent.com/appwoodpecker/woodpecker-ios/master/WoodpeckerMacOS-Carthage.json"
```
<br/>

**3. 手动集成:**

1. 下载 <a href="/assets/framework/WoodpeckerMacOS.framework.zip">WoodpeckerMacOS.framework</a>
2. 导入 WoodpeckerMacOS.framework 到您的项目

<br/>


**可能遇到的问题:**
> **dnssd_clientstub ConnectToServer: connect()-> No of tries: 1**
> **dnssd_clientstub ConnectToServer: connect() failed path:/var/run/mDNSResponder Socket:3 Err:-1 Errno:1 Operation not permitted**

<br/>
请参考下图开启应用的双向网络权限，如果您不使用沙盒模式，在开启权限后再点击沙盒开关即可，另外在发布时根据需要关闭此权限

<img src="/assets/img/macnetwork.png"/>
<br/>
<br/>


> **dyld: Library not loaded: @rpath/WoodpeckerMacOS.framework/WoodpeckerMacOS
Reason: image not found**

<br/>
请参考下图将WoodpeckerMacOS.framework拖拽到`Build Phases -> Embed Framworks`中。

<img src="/assets/img/embedframeworkmac.png"/>
<br/>
<br/>
> **Mac端状态一直是waiting connect，连接不上**

1. 确认App和Mac在同一wifi下
2. 请确认App集成的WoodpeckerMacOS.framework版本为最新版
3. 尝试手动连接Woodpecker客户端，使用Ctrl+Command，然后双击窗口任意位置弹出连接界面，搜索找到后连接即可
4. 如果仍然有问题，<a href="/cncontact.html">请点击这里</a>

<br/>
> **经常连接到其他人电脑**

你可以设置只连接特定的电脑，<a href="/cnconnection.html">查看更多设置</a>

<br/>
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









