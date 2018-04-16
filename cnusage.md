---
layout: subpage
title: WoodPecker使用
---


<h3 class="index-h3">感谢使用 WoodPecker！</h3>

**支持真机和模拟器iOS8.0及以上，Objective-C and Swift.**

您只需要将WoodPeckeriOS.framework导入您的项目，WoodPeckeriOS.framework 会自动启动，并尝试连接Mac客户端
（使用真机时，请确认Mac和手机在同一网络内）


**CocoaPods:**

```
pod 'WoodPeckeriOS'
```
仅在Debug配置时导入 [参见说明](https://guides.cocoapods.org/syntax/podfile.html#pod)
```
pod 'WoodPeckeriOS', :configurations => ['Debug']
```
如果一直连接不上，请使用`pod update WoodPeckeriOS`使用最新版WoodPeckeriOS framework
<br/>

**Carthage:**

```
binary "https://raw.githubusercontent.com/github-xiaogang/woodpeckeriOS/master/WoodPeckeriOS-Carthage.json"
```
<br/>

**手动集成:**

1. 下载 <a href="/assets/framework/WoodPeckeriOS.framework.zip">WoodPeckeriOS.framework</a>
2. 导入 WoodPeckeriOS.framework 到您的项目

集成遇到问题:

```
dyld: Library not loaded: @rpath/WoodPeckeriOS.framework/WoodPeckeriOS

Reason: image not found
```

请参考下图将WoodPeckeriOS.framework拖拽到`Build Phases -> Embed Framworks`中。

<img src="/assets/img/embedframework.png"/>
<br/>
<br/>

您可以下载 <a href="https://github.com/github-xiaogang/woodpecker-demo">Demo</a> 立即体验。

<a href="/cnconnection.html">连接过程遇到问题 ?</a>