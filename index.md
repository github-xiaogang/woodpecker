---
layout: default
---

## WoodPecker build a communication channel between Mac and your App, then using powerful, extendable toolset to let your App just under your control






### SandBox:

**Has never been easier to read, view, modify sandbox file**

### Network:

**All network request, all in your sight**
```
supports http(s) network, doesn`t supports view response body in UIWebView or WKWebView
```

### I/O:
	
**A channel between mac and your app, you can transfer data, call service in you app, or log message to mac client**

### Web Console

**A simple web console, you can send javascript to debug webview inside app, it was actually a woodpecker plugin**




### Usage：

1. Import WoodPeckeriOS.framework to your Xcode Project.  the framework locates at mac client`s "Help-> App Support" menu.
2. Startup your Woodpecker mac client.
3. WoodPeckeriOS.framework will automatically startup and try to connect to mac client. 

WoodPecker using bonjour service to find mac client`s IP and port, then it connect to mac client using socket automatically.
If you want manually setup the IP or need stop the automatic connection, just long press you app using two finger to show the connection page,
you can search mac client or manually setup the IP and port (woodpecker use socket port 9999).


### Plugin support

**Woodpecker provide a communication channel between mac client and app, and defines the way they talk to each other, according the rule, we can custom a plugin very easily**
[create a plugin](/developer.html)











