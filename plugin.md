---
layout: subpage
title: Plugin
---

### WoodPecker provides a communication channel between mac client and app, and defines a friendly Api for developer, so we can custom a plugin tool very easily.




## Create a plugin:

 1. Create a service, and implements it`s action list.

 2. Register the service.

 3. Use the service at mac client.



Now We`ll implement a service called "EchoService" to show these processes in detail. 


 - [Demo Code](https://github.com/github-xiaogang/woodpecker-demo)

### 1. Create a service

ADHService class represent a service in woodpecker, so we create a subclass of ADHService named "EchoService".

```
@interface EchoService : ADHService

@end

```

A service has a name, and has a list of action.
here we named it "adh.EchoService", and define an action named "echo".

```
@implementation EchoService

+ (NSString *)serviceName
{
    return @"adh.EchoService";
}

+ (NSDictionary *)<NSString *,NSString *>actionList
{
    return @{
            	@"echo" : @selector(onRequestEcho:), 
            };
}

/*
this handler will be called on receiving a request whose service named "adh.EchoService", action named "echo". 
request parameter could carry a dictionary body and a binary payload.
and you must call [request finish] or other finsh method to response the request.
*/
- (void)onRequestEcho: (ADHRequest *)request
{
    NSDictioanry * body = request.body;
    NSData * payload = request.payload;
    /**
        your code
    */
    [request finish];
}

@end
```

### 2. Register service

before use EchoService, you should register it.

```
- (void)viewDidLoad {
    [super viewDidLoad];

    [[ADHOrganizer organizer] registerService:[EchoService service]];
}
````

### 3. Use service at mac client

There are two way to use a service:

 1. Call service using the mac client`s I/O.

 2. Create a mac web plugin, and call the service in the wap page, the web plugin will appear at the toolbar

I`ll show you in detail.

#### 3.1 Using the mac client`s I/O

![io1](/assets/img/io1.png)

![io2](/assets/img/io2.png)

There are four form you should provide:

	Service: which service you want call, here we choose "adh.EchoService".
	
	Action: which action you want call, here we choose "echo".

	Body: you can pass a dictionary object(here the dictionary should be a json text) to the request, and you you could fetch it using request.body later, here we fill nothing.

	Payload: you can pass a data payload(here should be a file) to the request, and you could fetch it using request.payload later, here we choose nothing.


#### 3.2 Create a mac web client plugin

A web plugin is a bundle stored at the Plugin directory (could be find at the Plugin -> Home menu). 
A plugin bundle should at least has two files:

	index.html （the plugin`s index page)
	icon.png (the icon will show at tool bar)

in the web page you could call App`s service using the method "adhCallClientApi" (defined in Plugin/adh.bundle/adh.js).

``` html
<!-- in html -->
<head>
  <script type="text/javascript" src="../adh.bundle/adhjs.js"></script>
</head>

<body>
  <script type="text/javascript">
    function callService(){
      //call Echoservice
      adhCallClientApi('adh.EchoService','echo','','',function (data,payload){
			
      });
    }
  </script>
</body>
```


``` javascript
//in adh.bundle/adh.js

/**
call app service` action

@p service: service name
@p action: action name
@p data: object that could be jsonfy
@p payload: binary data

on response the callback function will be called, the callback could contains a object and a payload depends on your service implentation
*/

function adhCallClientApi(service,action,data,payload,callback)
{
	
}

```
Once you finish your web plugin, you could refresh the plugin list using "Plugin -> Reload" menu, your plugin will show in the tool bar.


















