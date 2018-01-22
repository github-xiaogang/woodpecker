---
layout: default
title: woodpecker
projectname: WoodPecker
---

## WoodPecker build a communication channel between mac and your app, with powerful, extendable toolset let your app just under your control

<div class="demovideo">
  <iframe src="https://www.youtube.com/embed/aaEdo6kETl0?rel=0" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
</div>



<div class="index-section">
	<img src="/assets/img/tool_sandbox.png"/> <span>SandBox</span>
</div>

**Has never been easier to read, view, modify sandbox file**

<div class="index-section">
	<img src="/assets/img/tool_network.png"/> <span>Network</span>
</div>

**All network request, all in your sight**
```
supports http(s) network, doesn`t supports view response body in UIWebView or WKWebView
```

<div class="index-section">
	<img src="/assets/img/tool_io.png"/> <span>I/O</span>
</div>
	
**A channel between mac and your app, you can transfer data, call service in you app, or log message to mac client**

<div class="index-section">
	<img src="/assets/img/tool_webconsole.png"/> <span>Web Console</span>
</div>

**A simple web console, you can send javascript to debug webview inside app, it was actually a woodpecker plugin**

<h3 class="index-h3">Usage</h3>

1. Download WoodPeckeriOS.framework [Download](/download.html).
2. Import WoodPeckeriOS.framework to your Xcode Project.
3. Startup your Woodpecker mac client.
4. WoodPeckeriOS.framework will automatically startup and try to connect to mac client. 


support Device and Simulator iOS8.0 and above, Objective C and Swift.

you can start with [demo](/download.html).


```
WoodPecker using bonjour service to find mac client`s IP and port, then it connect to mac client using socket automatically.
If you want manually setup the IP or need stop the automatic connection, just long press you app using two finger to show the connection page,
you can search mac client or manually setup the IP and port (woodpecker use socket port 9999).
```

<h3 class="index-h3">Plugin support</h3>

**Woodpecker provide a communication channel between mac client and app, and defines the way they talk to each other, according the rule, we can custom a plugin very easily.**
[create a plugin](/plugin.html)
<br/>
<br/>



<h3 class="index-h3">Thanks</h3>

<a href="https://github.com/Flipboard/FLEX">FLEX</a>,
<a href="https://github.com/mugginsoft/Fragaria">Fragaria</a>, 
<a href="https://github.com/enormego/egodatabase">EGODatabase</a>, 
<a href="https://github.com/robbiehanson/CocoaAsyncSocket">CocoaAsyncSocket</a>,
<a href="https://github.com/marcuswestin/WebViewJavascriptBridge">WebViewJavascriptBridge</a>, 

 
  





