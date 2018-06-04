---
layout: subpage
title: Woodpecker使用
---


<h3 class="index-h3">感谢使用 Woodpecker！</h3>

**Woodpecker支持在真机和模拟器iOS8.0及以上使用，Objective-C and Swift.**

您只需要将WoodPeckeriOS.framework导入您的项目，WoodPeckeriOS.framework 会自动启动，并尝试连接Mac客户端
（使用真机时，请确认Mac和手机在同一网络内）


**1. CocoaPods:**

```
pod 'WoodPeckeriOS', >= 1.0.3
```
仅在Debug配置时导入 [参见说明](https://guides.cocoapods.org/syntax/podfile.html#pod)
```
pod 'WoodPeckeriOS', >= 1.0.3 :configurations => ['Debug']
```
如果需要更新，请使用`pod update WoodPeckeriOS`
<br/>
<br/>

**2. Carthage:**

```
binary "https://raw.githubusercontent.com/github-xiaogang/woodpeckeriOS/master/WoodPeckeriOS-Carthage.json"
```
<br/>

**3. 手动集成:**

1. 下载 <a href="/assets/framework/WoodPeckeriOS.framework.zip">WoodPeckeriOS.framework</a>
2. 导入 WoodPeckeriOS.framework 到您的项目
<br/>

集成可能遇到的问题:

```
1. dyld: Library not loaded: @rpath/WoodPeckeriOS.framework/WoodPeckeriOS

Reason: image not found
```

请参考下图将WoodPeckeriOS.framework拖拽到`Build Phases -> Embed Framworks`中。

<img src="/assets/img/embedframework.png"/>

```
2. Mac端状态一直是waiting connect，连接不上
```
1. 确认App和Mac在同一wifi下
2. 请确认App集成的WoodPeckeriOS.framework版本为最新版
3. <a href="/cnconnection.html">仍然有问题?</a>

<br/>

您可以下载 <a href="https://github.com/github-xiaogang/woodpecker-demo">Demo</a> 立即体验。

<br/>







