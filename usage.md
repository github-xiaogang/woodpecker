---
layout: subpage
title: Woodpecker Usage
---


<h3 class="index-h3">Thanks for using Woodpecker！</h3>

**Woodpecker Supports both physical device and simulator iOS8.0+, Objective C and Swift.**

To use Woodpecker, you need import WoodPeckeriOS.framework to your project, WoodPeckeriOS.framework will automatically launch and connect to mac client. 
(If you are work physical device, please ensure mac and your device are in the same network.)

**1. CocoaPods:**

```
pod 'WoodPeckeriOS', '>= 1.0.3'
```
only in `Debug` configuration [read more](https://guides.cocoapods.org/syntax/podfile.html#pod)
```
pod 'WoodPeckeriOS', '>= 1.0.3', :configurations => ['Debug']
```
Use 'pod update WoodPeckeriOS' to update the latest version.
<br/>
<br/>

**2. Carthage:**

```
binary "https://raw.githubusercontent.com/github-xiaogang/woodpeckeriOS/master/WoodPeckeriOS-Carthage.json"
```
<br/>

**3. Manual Setup:**

1. Download <a href="/assets/framework/WoodPeckeriOS.framework.zip">WoodPeckeriOS.framework</a>
2. Import WoodPeckeriOS.framework to your Project.

<br/>

**If you have the following problems:**

> **dyld: Library not loaded: @rpath/WoodPeckeriOS.framework/WoodPeckeriOS
Reason: image not found**

<br/>
Please drag WoodPeckeriOS.framework to `Build Phases -> Embed Framworks`.

<img src="/assets/img/embedframework.png"/>
<br/>
> **Mac client is always "waiting connect"**

1. please ensure mac and app are in the same wifi
2. please ensure WoodPeckeriOS.framework was the latest version

<br/>
> **I often connect to other's mac.**

 You could make some options to specify which client you'd like to connect, <a href="/connection.html">see advanced usage</a>.

<br/>
You can start with <a href="https://github.com/github-xiaogang/woodpecker-demo">Demo App</a>
<br/>
<br/>
<br/>



