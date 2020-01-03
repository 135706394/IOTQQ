IOTQQ --为跨平台而生

**运行在Mac平台**

![MAC](https://camo.githubusercontent.com/77144e212578e053a1ad14f888d4d53191c578fa/68747470733a2f2f73322e617831782e636f6d2f323031392f30392f30342f6e5a376744782e706e67)

**运行在树莓派3B+ 1G RAM**

![树莓派](https://camo.githubusercontent.com/25a25bbf4f6221caa03a879fac4b1813f7715937/68747470733a2f2f67636861742e717069632e636e2f67636861747069635f6e65772f313730303438373437382f3936303833393438302d323533343333353035332d46363334353639354131333435304344383834363033444433313141363143372f303f7675696e3d353334373036333530267465726d3d32353526706963747970653d30)

**运行在电视盒子 N1**
![电视盒子](https://camo.githubusercontent.com/fa9594a6577f447bd97f33ac40ca2a824fe5dd6b/68747470733a2f2f73322e617831782e636f6d2f323031392f31302f30332f75304e7765502e706e67)
![电视盒子](https://camo.githubusercontent.com/32c5b864b035a04b094bf77de272b1fa6336434e/68747470733a2f2f73322e617831782e636f6d2f323031392f31302f30332f75304e4946552e706e67)

**运行在路由器HIWI-FI**

![路由器](https://camo.githubusercontent.com/139a303674c16c57c98e94fc729cd17094127214/68747470733a2f2f73322e617831782e636f6d2f323031392f31302f30332f75304e76544b2e6d642e706e67)

### ⚠️使用协议⚠️
- **IOTQQ 不得用于包括且不限于~~赌博、色情、云盘、政治~~ 等网络违法违规服务，违者必究**
- **用户不得使用 IOTQQ 来进行批量业务，如：批量加群，加好友等。**
- **用户在使用本软件过程中，应遵守当地法律法规与深圳市腾讯计算机系统有限公司用户协议中相关行为规范，且用户不能使用本软件进行以下行为，包括但不限于：广告传播、黑产、黄、赌、毒、PC蛋蛋、北京赛车、黑色产业、灰色产业、算账下注、群发、批量加群等任何违法犯罪或与犯罪相关，用户使用本软件进行相关违法犯罪的行为，均应由用户自行承担，IOTQQ不对用户的任何言行与行为承担任何责任**
- **免责声明：IOTQQ软件是一款基于QQ协议的AI机器人软件，主要用于活跃QQ群气氛、管理群、群内娱乐活动等，协议版权归属于深圳市腾讯计算机系统有限公司所有， 如有侵权请联系邮箱(1700487478@qq.com)，将会对软件下架并删除相关内容。**

### 🆕树莓派运行展示🆕
- **[芝麻开门 VNC](http://110.42.4.109:43288/vnc.html) 密码12345678**

------------

|  IOTQQ功能 | Free  ⬆️              |
| ------------- | ------------------------------ |
| `好友消息 收发语音文字图文XML/JSON`| ✅     |
| `群组消息 收发语音文字图文XML/JSON`   |  ✅    |
| `私聊消息 收发语音文字图文XML/JSON`   |  ✅    |
| `Open RedBag`   | ✅    |
| `Send  RedBag`   |   ❌    |
| `QQ空间发图文`  |  ❌      |
| `群 邀请/踢人/加群`    |  ✅   |
| `好友 通过/拒绝/加人`    |  ✅     |
| `账号 登陆`    |   ❌ |
| `多账号 登陆`    |  ❌   |

**项目介绍**

*⚠️运行项目的必要条件 需要外网IP用来接收GitHub的WebHook通知 非外网用户可以借助转发工具来解决 如*
>frp

>ngrok

- **🆓**
- **🌞采用独特的插件机制 --Lua**
- **🌞提供WebSocket （SocketIO）**
- **🌞提供Web API**
- **🌞内置协程池 高效 稳定 迸发**
- **🌞完成了大部分核心接口 其他必要接口将后续更新 可在[issues](https://github.com/IOTQQ/IOTQQ/issues)中提出 bug or todo**
- **不断电稳定运行 0 崩 错误日志将会在log中体现**

#### 💗开启运行之旅

------------
```go
fmt.Println("Github Token 会用来创建通知仓库 如果不放心使用 请建立小号 初始化所有操作记得清空Bot-Notify 仓库")
```

**1⃣️下载对应平台版本的二进制包 [传送门](https://github.com/IOTQQ/IOTQQ/releases "1")**

**2⃣️申请GitHub Token 用于GitHubApi访问 默认限制每小时60次请求 有了Token可以5000/h
 申请流程登陆GitHub后->settings-> Developer settings->Developer settings->Generate New Token
 开启全部Token权限!全部☑️**
 
**3⃣️填写配置文件CoreConf.conf  首先配置Token 后启动程序**


      #默认使用本地配置文件 暂时不支持集群模式
      EnabledEtcd = false
      #自定义监听服务端口
      Port = "0.0.0.0:8888"
        [Etcd]
          Nodes = ["", "", ""]
        [GithubConf]
          #必填 GitHub申请回来的Token
          Token = ""
          #初始化软件自动生成 请勿填写
          FullName = ""
          #初始化软件自动生成 请勿填写
          IssuesNum = 1
          #必填域名端口替换成外网的http://IP:PORT/v1/Github/WebHook
          WebHookUrl = ""
          #初始化软件自动生成 请勿填写
          BitFlag = 0
          #初始化软件自动生成 请勿填写
          BitCtrl = 0
          #初始化软件自动生成 请勿填写
          CommentID = 0 
          #初始化软件自动生成 请勿填写
          WebHookId = 0


    

**4⃣️运行程序 执行命令 `./IOTQQ` 默认开启8888端口作为WebSokcet/WebApi的服务端口**

`服务器用户  如:服务器外网IP 为123.123.123.123 且防火墙允许8888端口 这时访问一下URL http://123.123.123.123:8888/v1/Github/WebHook 如果返回为OK 则此时的URL 为WebHookUrl 将其填写到 CoreConf.conf 的字段WebHookUrl后保存`

`转发用户 公益的FRP有很多 配置好转发规则 将本地的服务端口8888映射出去 如映射到外网的9909端口 这时访问一下 http://公益FRP域名:9909/v1/Github/WebHook 如果返回为OK 则此时的URL 为WebHookUrl 将其填写到 CoreConf.conf 的字段WebHookUrl后保存`

`您的服务器信息均会不暴露 No DDos,No Attack 仅作为GitHub WebHook通知`

`UsersConf目录为本地用户缓存数据 登录设备信息等 便于复用 切勿随意创建 默认启动程序会自动登录`

`仓库中Plugins与二进制压缩包里Plugins 文件不同 可手动合并`

**5⃣️一切准备就绪 当你外网服务器IP:PORT 或(内网用户)经过转发OK时 在打开浏览器访问WebHookUrl 浏览器返回OK则可以进行下一步 不通请检查防火墙 or 转发配置**

------------


#### ❤️初始化服务

- **服务运行成功后访问URL http://IP:PORT/v1/Github/InstallService 初始化成功后控制台会提示 `Auth初始化完成` 若未提示 重复上述操作 初始化完成后就可以 🌊了**

![](https://camo.githubusercontent.com/006aa8615ba21f0cd3b0a1b53758966a0462c4f9/687474703a2f2f67636861742e717069632e636e2f67636861747069635f6e65772f313730303438373437382f3936303833393438302d323533343333353035332d41453433374137393535453130444234384336333239463638434535463232412f303f7675696e3d353334373036333530267465726d3d32353526706963747970653d30)

![](https://camo.githubusercontent.com/de70ec04c277a71980e26e3746214708adc9a00a/68747470733a2f2f67636861742e717069632e636e2f67636861747069635f6e65772f313730303438373437382f3936303833393438302d323533343333353035332d37333445333142303633444538423539433641354538413145463546373834382f303f7675696e3d353334373036333530267465726d3d32353526706963747970653d30)

- **若没有提示`Auth初始化完成`请检查你的防火墙或GitHub账号是否禁用(需解封) 也可以联系我排除问题**
- **获取登陆二维码 访问Url http://IP:PORT/v1/Login/GetQRcode 扫码登陆即可**

------------


### 🆒Lua相关API

###### WebPlugin APi
- 请勿修改 WebPlugins目录下的任意文件名以及文件内容的函数名 否则部分WebAP接口会失效

[详细介绍请移步](https://github.com/IOTQQ/IOTQQ/blob/master/%E5%BC%80%E5%8F%91%E6%8C%87%E5%8D%97%E4%B9%8BWebApi%E7%AF%87.md)

 
###### Plugin APi

- 插件命名不受限制 xxx.lua 但是必须实现以下函数 

```lua
--收到好友/私聊消息触发该函数
--CurrentQQ 响应消息的QQ
--data 消息数据 
function ReceiveFriendMsg(CurrentQQ, data)
    return 1 --1 继续处理后续插件 2 不在处理后续插件
end
--收到群消息触发该函数
function ReceiveGroupMsg(CurrentQQ, data)
    return 1
end
--收到所有相关事件的集合 如群成员进群退群管理升降消息撤回、好友撤回删除等事件
function ReceiveEvents(CurrentQQ, data, extData)
    return 1
end

```
[详细介绍请移步](https://github.com/IOTQQ/IOTQQ/blob/master/%E5%BC%80%E5%8F%91%E6%8C%87%E5%8D%97%E4%B9%8BLuaApi%E7%AF%87.md)

- 相关APi用法请查阅Plugins目录下的相关文件调用例程 这里不再赘述

------------

###### WebSocket APi 

- **实现的功能比较少只做了几个 配合WebAPI 实现 webQQ 易如反掌**

- ** 给出部分js代码**

```javascript
<script>
    var User = localStorage.getItem('User');
     var socket = io("127.0.0.1:8888", {
      transports: ['websocket']
    });

    socket.on('connect',
    function() {
        //从缓存或从cookies 读取历史登陆的QQ号
        //链接成功后获取用户缓存 获取成功后直接同步消息 失败直接获取二维码
        //同一浏览器会置换当前的websocket id
    
      if (User == null){

      //获取二维码
      socket.emit('GetQrcode', '1234', (data) =>{
      console.log(data); // data will be 'woot'
      var JsonPkg = JSON.parse(data);
      $('#qrcode').attr("src", 'data:image/png;base64,' + JsonPkg.Data.BQrpic);

       });

      }else{

        socket.emit('GetWebConn', User, (data) =>{
        console.log(data);

        $('#qrcode').attr("src", 'http://q1.qlogo.cn/g?b=qq&nk=' + User + '&s=640');
      });

      }
     
    })
    socket.on('OnCheckLoginQrcode',
    function(data) {
      //48未扫描 53已扫码 17 49 过期了
      // if (data.Data.ScanStatus ==17 || data.Data.ScanStatus == 49){
      // }
        console.log(data);
    });

    socket.on('OnLoginSuccess',
    function(data) {

      // 移除所有
      localStorage.clear();
      console.log(data);

      $('#qrcode').attr("src", 'http://q1.qlogo.cn/g?b=qq&nk=' + data.Uin + '&s=640');
      localStorage.setItem('User', data.Uin);
      localStorage.setItem('Nick', data.Nick);
    });
    //统一事件管理如好友进群事件 好友请求事件 退群等事件集合
    socket.on('OnEvents', function (data) {
      console.log("收到相关事件");
      console.log(JSON.stringify(data));

    });
    //收到好友消息的回调事件
    socket.on('OnFriendMsgs', function (data) {
      console.log("收到好友消息");
      console.log(data);
      console.log(JSON.stringify(data))
    });
    //收到群消息的回调事件
    socket.on('OnGroupMsgs', function (data) {
      console.log("收到群消息");
      console.log(data);
      console.log(JSON.stringify(data))
    });
</script> 
```
###### Web APi


- **请导入仓库中的WebAPI.json到Chrome的Restlet Client - REST API Testing插件中**


- ![WEBAPI](https://camo.githubusercontent.com/7f14b2ca2de14d40fc2d127392eea3fa04c78788/68747470733a2f2f692e6c6f6c692e6e65742f323031392f30392f30322f634e596a48676d52366f6244324c462e706e67)


- **插件下载地址[Restlet Client](https://chrome.google.com/webstore/detail/aejoelaoggembcahagimdiliamlcdmfm "1")**

### Tips

- **😄登陆成功后在手机端回复电脑 systeminfo可查看相关收发包等信息**
- **😄访问URL :http://IP:PORT/v1/ClusterInfo 可以查询相关信息**
- **😄集群模式暂未开放**
- **😄多账号登陆需授权**

#### ❤️以下文章或项目排名不分先后 🙏感谢贡献 ❤️

### 相关文章
- **😄 [IOTQQ从1开始](https://blog.fbicloud.com/articles/2019/09/29/1569767839256.html)**
- **😄 [精简机器人插件](http://118.25.41.32/CB/index.php/archives/128/)**
- **😄 [实现一个“人工智能”QQ机器人！](https://segmentfault.com/a/1190000021259760)**
- **😄 [实现一个“人工智能”QQ机器人！续](https://segmentfault.com/a/1190000021350469)**
- **😄 [使用Python制作IOTQQ插件](https://mcenjoy.cn/152/)**
- **😄 [IOTQQ WebApi接口文档](https://www.showdoc.cc/IOTQQ)**

### 相关项目
- **😄 [IOTQQ机器人插件模板Python](https://github.com/mcoo/iotqq-plugins-demo)**
- **😄 [QQ群反垃圾机器人](https://github.com/rockswang/qqcensorbot)**
- **😄 [IOTQQ机器人框架开发的web版机器人框架](https://github.com/CB-ym/IOTQQ_web)**


### 感谢 
 - **gopher-lua [https://github.com/yuin/gopher-lua](https://github.com/yuin/gopher-lua)**
 - **gluahttp [https://github.com/cjoudrey/gluahttp](https://github.com/cjoudrey/gluahttp)**
 - **TarsGo [https://github.com/TarsCloud/TarsGo](https://github.com/TarsCloud/TarsGo)**
 - **BeegoLog [https://github.com/beego](https://github.com/beego)**
 
 ### 交流裙
 - ![](https://camo.githubusercontent.com/b20e53a08261eacaaad0783f78870d40e7fb5228/687474703a2f2f67636861742e717069632e636e2f67636861747069635f6e65772f3533343730363335302f3936303833393438302d323533343333353035332d46324130394442463642383032343746434330373645413535454330333635332f303f7675696e3d31373030343837343738267465726d3d32353526706963747970653d30)
