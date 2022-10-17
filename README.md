# cpas
让一台内网服务器变成一台公网服务器。
Make a server in private network like a server in public network.

## 用在哪里？(Where to use?)
* 在外访问家或公司内的HTTP或HTTPS服务器
* SSH远程连接家或公司的Linux主机
* RDP远程连接家或公司Windows主机
* 所有基于TCP协议的服务器

## cpas是什么含义？(What does cpas mean?)
cpas是指Client、Proxy、Agent、Server。
cpas means Client, Proxy, Agent and Server.

## 工作原理？(How does it works?)
```
Client      Proxy      Agent      Server
   |          |          |          |
   |          |<--Token--|          |
   |--Data1-->|          |          |
   |          |--Data1-->|          |
   |          |          |--Data1-->|
   |          |          |          |
   |          |          |<--Data2--|
   |          |<--Data2--|          |
   |<--Data2--|          |          |
   |---Data3->|          |          |
   |          |--Data3-->|          |
   |          |          |--Data3-->|   
   |          |          |          |
```
