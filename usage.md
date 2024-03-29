---
layout: subpage
title: Woodpecker Usage
---


<h3 class="index-h3">Thanks for using Woodpecker！</h3>

**Woodpecker Supports both physical device and simulator iOS9.0+, Objective-C and Swift.**

To use Woodpecker, you need import a framework to your project, then it will start and connect to Woodpecker client automatically. If you are work with physical device, please ensure your app and Woodpecker are in the same network.<br/>

If you're developing a Mac app, please check <a href="/usagemac.html">Woodpecker for MacOS</a>

**1. CocoaPods:**

```
pod 'WoodPeckeriOS', :configurations => ['Debug']
```
Use `pod update WoodPeckeriOS` to update the latest version.
<br/>
<br/>

**2. Carthage:**

```
binary "https://raw.githubusercontent.com/appwoodpecker/woodpecker-ios/master/WoodPeckeriOS-Carthage.json"
```
<br/>

**3. Manual Setup:**

1. Download <a href="/assets/framework/WoodPeckeriOS.xcframework.zip">WoodPeckeriOS.xcframework</a>
2. Import WoodPeckeriOS.xcframework to your project.
3. If you like to use only in Debug configuration, please <a href="/manuallink.html">check this</a>

<br/>


**4. Jailbreak Setup:**

1. <a href="https://todayios-cydia.github.io/cydia/"> TSCydia </a>, select the TSWoodPeckeriOSLoader, it supports iOS 12.0+. Created by <a href="https://github.com/todayios-cydia">manajay</a>
2. <a href="https://tinxie1115.github.io/"> TinXie's Repository </a>, Created by <a href="https://s2339956.github.io/about/"> TinXie </a>


<br>

**If you have the following problems:**


> **Didn't work with iOS 14 devices**

<br/>
iOS 14 add a new privacy about local network usage, please ensure your app has the permission, and if you build with the Xcode 12+, please add these two items in Info.plist:

1. Add description in `Privacy - Local Network Usage Description`
2. Add `_adhp._tcp` in Bonjour services list

<img src="/assets/img/localnetwork.png"/>

**In practice, we don't need to remove these keys when build for AppStore, because the privacy alert won't appear until we call any local network api, such as bonjour service or multicast**

<br/>
> **dyld: Library not loaded: @rpath/WoodPeckeriOS.framework/WoodPeckeriOS
Reason: image not found**

<br/>
Please drag WoodPeckeriOS.xcframework to `Build Phases -> Embed Framworks`, then select Embed & Sign.

<img src="/assets/img/embedframework.png"/>
<br/>
> **Mac client is always "waiting connect"**

1. please ensure mac and app are in the same wifi.
2. please ensure WoodPeckeriOS.xcframework was the latest version.
3. connect to mac client manually, long press your iOS app's screen with two fingers, you'll see the connection page, try search and connect to your mac client.
4. If it still doesn't work, <a href="/contact.html">click here</a>.

<br/>
> **I often connect to other's mac.**

 You could make some options to specify which client you'd like to connect, <a href="/connection.html">see advanced usage</a>.

<br/>
You can start with <a href="https://github.com/appwoodpecker/woodpecker-ios"><img src="/assets/img/logo_github.png" width="16" heigh="16"/> demo app </a>or talk with others at 
<a href="https://t.me/appwoodpecker">
	<img src="/assets/img/logo_tele.png" width="16" heigh="16"/> telegram group
</a>
<br/>
<br/>
<br/>



