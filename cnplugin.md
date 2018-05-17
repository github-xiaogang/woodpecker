---
layout: subpage
title: 扩展插件
---

### Woodpecker提供了Mac和App之间的通信渠道，并提供了简单的通信Api，开发者可以轻松定制自己的插件工具。




## 创建插件:

 1. 创建service，实现它的动作列表.

 2. 注册创建的service

 3. 在Mac客户端使用service



下面我们实现一个名为“EchoService”的service来演示具体步骤。


 - [Demo项目](https://github.com/github-xiaogang/woodpecker-demo)

### 1. 创建Service

在Woodpecker中ADHService类代表service对象, 我们创建ADHService的子类EchoService。

```
@interface EchoService : ADHService

@end

```

每一个service有名称(name)和它的动作列表(actionList)
我们EchoService名称设为“adh.EchoService"，并定义一个动作"echo"。

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
在App接收到service名为"adh.EchoService"，动作为”echo"的请求时，下面的方法将会被调用
request参数可以包含一个NSDictionary类型的body和NSData类型的payload
处理结束后你需要调用request的finish方法来响应请求
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

### 2. 注册创建的Service

在使用EchoService之前，你需要先在App注册它

```
- (void)viewDidLoad {
    [super viewDidLoad];

    [[ADHOrganizer organizer] registerService:[EchoService service]];
}
````

### 3. 在Mac客户端使用创建的Service

有两种方法使用Service：

 1. 通过Mac客户端的I/O工具来调用App的service

 2. 在Mac端创建一个web插件，然后在插件中调用service，创建的插件会在Mac客户端的工具栏中显示

下面详细介绍两种方式

#### 3.1 在Mac客户端的I/O工具调用Service

![io1](/assets/img/io1.png)

![io2](/assets/img/io2.png)

你可以填写4个字段：

	Service: 将要调用的service名称，这里我们选择"adh.EchoService"。
	
	Action: 将要调用的动作名称，这里我们选择"echo"。

	Body: 你可以给请求添加一个NSDictionary类型的参数(这里需要填写字典的json字符串) , 在接收方，你可以通过request.body来获取该值，这里我们不填任何内容。

	Payload: 你可以给请求添加一个NSData类型的参数(这里请选择一个文件), 在接收方，你可以通过request.payload获取该值, 这里我们不选择文件。


#### 3.2 创建Mac端web插件使用Service

一个web插件实际上是一个在Plugin目录的bundle包（插件目录可以在客户端的Plugin -> Home找到）。
插件bundle至少应该包含两个文件：

	index.html （插件入口文件)
	icon.png (插件的图标，将在工具栏显示)

在web插件内，你可以通过调用"adhCallClientApi"方法来调用App的service，（在Plugin/adh.bundle/adh.js中定义）

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
在web插件开完后，点击菜单栏的“Plugin -> Reload”来加载插件，加载后插件将在工具栏中显示。（编写时可参考插件目录的Web Console.bundle）


















