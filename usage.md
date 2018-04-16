---
layout: subpage
title: WoodPecker Usage
---


<h3 class="index-h3">Thanks for using WoodPecker！</h3>

**WoodPecker Supports both real device and simulator iOS8.0+, Objective C and Swift.**

To use WoodPecker, you need import WoodPeckeriOS.framework to your project, WoodPeckeriOS.framework will automatically startup and connect to mac client. 
(If you are work the real iOS device, please ensure mac and your device are in the same network.)

**CocoaPods:**

```
pod 'WoodPeckeriOS'
```
only in `Debug` configuration [read more](https://guides.cocoapods.org/syntax/podfile.html#pod)
```
pod 'WoodPeckeriOS', :configurations => ['Debug']
```
If app couldn't connect to Mac, please use 'pod update WoodPeckeriOS' to fetch the latest framework
<br/>

**Carthage:**

```
binary "https://raw.githubusercontent.com/github-xiaogang/woodpeckeriOS/master/WoodPeckeriOS-Carthage.json"
```
<br/>

**Manual Setup:**

1. Download <a href="/assets/framework/WoodPeckeriOS.framework.zip">WoodPeckeriOS.framework</a>
2. Import WoodPeckeriOS.framework to your Project.

If you see error like this:

```
dyld: Library not loaded: @rpath/WoodPeckeriOS.framework/WoodPeckeriOS

Reason: image not found
```

Please drag WoodPeckeriOS.framework to `Build Phases -> Embed Framworks`.

<img src="/assets/img/embedframework.png"/>
<br/>
<br/>

You can start with <a href="https://github.com/github-xiaogang/woodpecker-demo">Demo App</a>

<a href="/connection.html">Has problem with connection ?</a>