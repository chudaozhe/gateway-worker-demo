# Linux系统快速开始（从一个精简的聊天demo开始）
1、[下载demo](https://www.workerman.net/download/GatewayWorker.zip)

2、命令行运行 unzip GatewayWorker.zip 解压缩GatewayWorker.zip

3、命令行运行 cd GatewayWorker 进入GatewayWorker目录

4、命令行运行 php start.php start 启动GatewayWorker

5、新开几个命令行窗口运行 telnet 127.0.0.1 8282，输入任意字符即可聊天（非本机测试请将127.0.0.1替换成实际ip）。

> 注意
> 如果telnet超时请设置服务器安全组将8282端口开放。
> 如果需要测试websocket协议，需要将start_gateway.php中tcp改成websocket

GatewayWorker windows 版本
=================

GatewayWorker基于[Workerman](https://github.com/walkor/Workerman)开发的一个项目框架，用于快速开发长连接应用，例如app推送服务端、即时IM服务端、游戏服务端、物联网、智能家居等等。

GatewayWorker使用经典的Gateway和Worker进程模型。Gateway进程负责维持客户端连接，并转发客户端的数据给Worker进程处理；Worker进程负责处理实际的业务逻辑，并将结果推送给对应的客户端。Gateway服务和Worker服务可以分开部署在不同的服务器上，实现分布式集群。

GatewayWorker提供非常方便的API，可以全局广播数据、可以向某个群体广播数据、也可以向某个特定客户端推送数据。配合Workerman的定时器，也可以定时推送数据。

GatewayWorker Linux 版本
======================
Linux 版本GatewayWorker 在这里 https://github.com/walkor/GatewayWorker

启动
=======
双击start_for_win.bat

Applications\YourApp测试方法
======
使用telnet命令测试（不要使用windows自带的telnet）
```shell
 telnet 127.0.0.1 8282
Trying 127.0.0.1...
Connected to 127.0.0.1.
Escape character is '^]'.
Hello 3
3 login
haha
3 said haha
```

手册
=======
http://www.workerman.net/gatewaydoc/

使用GatewayWorker-for-win开发的项目
=======
## [tadpole](http://kedou.workerman.net/)  
[Live demo](http://kedou.workerman.net/)  
[Source code](https://github.com/walkor/workerman)  
![workerman-todpole](http://www.workerman.net/img/workerman-todpole.png)   

## [chat room](http://chat.workerman.net/)  
[Live demo](http://chat.workerman.net/)  
[Source code](https://github.com/walkor/workerman-chat)  
![workerman-chat](http://www.workerman.net/img/workerman-chat.png)  
