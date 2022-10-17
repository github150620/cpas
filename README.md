# cpas
* 使一台内网服务器能够在公网被访问。(Make a server in LAN can be reached in Internet.)
* cpas是指Client、Proxy、Agent、Server。(cpas means Client, Proxy, Agent and Server.)

## 适用场景(Where to Use)
* SSH远程连接家或公司的Linux主机
* RDP远程连接家或公司Windows主机
* 在外访问家或公司内的HTTP或HTTPS服务器
* 在公网访问内网（TCP协议）服务器

## 需要准备什么？(What does cpas need?)
一台有公网IP的云服务器。(A cloud server has public IP.)

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

## 使用
### 云服务器上配置并运行proxy程序
```
# ./proxy -token abcdefgh12345678 -client :22 -agent :8022
```

### 内网主机上配置并运行agent程序
* agent与server可以运行在一起，也可以在不同主机上运行
```
# ./agent -token abcdefg12345678 -proxy x.x.x.x:8022 -server 192.168.1.100:22
```
