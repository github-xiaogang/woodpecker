---
layout: subpage
title: Woodpecker使用
---


<h3 class="index-h3">感谢使用 Woodpecker！</h3>

**Woodpecker支持在真机和模拟器iOS9.0, macOS10.11 及以上使用，Objective-C and Swift.**

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


**4. 越狱插件:**

1. 请添加<a href="https://todayios-cydia.github.io/cydia/"> TSCydia </a>cydia源，选择TSWoodPeckeriOSLoader，支持iOS 12.0+
2. 如果您使用iOS14+系统调试，需要先确认App中的Info.plist包含下面本地网络访问权限相关key
- 在`Privacy - Local Network Usage Description`添加本地网络使用描述
- 在`Bonjour services`列表添加 `_adhp._tcp`
3. 感谢插件作者<a href="https://github.com/todayios-cydia"> manajay </a>，源中他同时提供了iOS调试工具Lookin和Flex的越狱插件


<br>


**可能遇到的问题:**

> **iOS 14设备不能正常使用**

<br/>
iOS 14系统增加了本地网络访问权限开关，请确认您App拥有此权限，如果您使用最新的Xcode 12+构建，请在Info.plist增加下面两项

1. 在`Privacy - Local Network Usage Description`添加本地网络使用描述
2. 在`Bonjour services`列表添加 `_adhp._tcp`

<img src="/assets/img/localnetwork.png"/>

**另外：如果上线时不需要此权限，理论上也不需要单独去删除（只要App没用调用Bonjour, multicast等local network api，是不会弹出权限弹框的）**

<br/>

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
<a href="https://t.me/appwoodpecker">
	<img src="/assets/img/logo_tele.png" width="16" heigh="16"/> telegram群
</a>
<a href="https://jq.qq.com/?_wv=1027&k=QXuhxDs0">
	<img src="/assets/img/logo_qq.png" width="16" heigh="16"/> QQ群(303015262)
</a>
开始讨论
<br/>
<br/>
<br/>









