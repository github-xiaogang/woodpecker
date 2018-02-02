---
layout: default
title: woodpecker
projectname: WoodPecker
---

## WoodPecker通过与App之间构建一条通信渠道，再通过强大可扩展的工具集，让您轻松掌控应用内部状况。



<div class="cndemovideo">
  <iframe src="http://player.youku.com/embed/XMzM0ODk3Mzc5Mg==" frameborder="0"></iframe>
</div>


<div class="index-section">
	<img src="/assets/img/tool_sandbox.png"/> <span>SandBox</span>
</div>

**获取，查看，编辑沙盒文件，从未如此简单**

<div class="index-section">
	<img src="/assets/img/tool_network.png"/> <span>Network</span>
</div>

**所有网络请求，尽在眼前**
```
支持http(s)，目前不支持查看WebView的响应数据body
```

<div class="index-section">
	<img src="/assets/img/tool_io.png"/> <span>I/O</span>
</div>
	
**通过Mac与App之间的通信渠道，你可以从App向Mac传递数据，或者在Mac端调用App的功能**

<div class="index-section">
	<img src="/assets/img/tool_webconsole.png"/> <span>Web Console</span>
</div>

**一个简单的Web调试器，可以在线让WebView运行javascript代码**

<h3 class="index-h3">使用方法</h3>

支持真机和模拟器iOS8.0及以上，Objective C and Swift.

**CocoaPods:**

```
pod 'WoodPeckeriOS', '~> 1.0.0'
```

**手动集成:**

1. 下载 [WoodPeckeriOS.framework](/download.html).
2. 将 WoodPeckeriOS.framework 导入您的项目.
3. 启动WoodPecker Mac客户端.
4. WoodPeckeriOS.framework 会自动启动，并尝试连接Mac客户端

您可以下载 [Demo](/download.html).


```
WoodPecker使用Bonjour服务来查找Mac客户端的IP和端口号，然后通过socket连接。当然你也可以手动设置Mac端IP，或者关闭自动自动连接行为（使用双指长按屏幕任意位置打开设置界面）
WoodPecker Mac端目前使用固定端口9999
```

<h3 class="index-h3">插件支持</h3>

**WoodPecker在Mac端和App端提供了一条通信渠道，并定义了一套简单通信规则，按照这套规则，开发者可以非常简单的创建自己的扩展功能**[创建插件](/plugin.html)
<br/>
<br/>



<h3 class="index-h3">致谢</h3>

<a href="https://github.com/Flipboard/FLEX">FLEX</a>,
<a href="https://github.com/mugginsoft/Fragaria">Fragaria</a>, 
<a href="https://github.com/enormego/egodatabase">EGODatabase</a>, 
<a href="https://github.com/robbiehanson/CocoaAsyncSocket">CocoaAsyncSocket</a>,
<a href="https://github.com/marcuswestin/WebViewJavascriptBridge">WebViewJavascriptBridge</a>, 

 
  





