# GatewayWorker（Workerman） - webSocket服务端

## Linux系统快速开始（从一个精简的聊天demo开始）
1、[下载demo](https://www.workerman.net/download/GatewayWorker.zip)

2、命令行运行 unzip GatewayWorker.zip 解压缩GatewayWorker.zip

3、命令行运行 cd GatewayWorker 进入GatewayWorker目录

4、命令行运行 php start.php start 启动GatewayWorker

5、新开几个命令行窗口运行 telnet 127.0.0.1 8282，输入任意字符即可聊天（非本机测试请将127.0.0.1替换成实际ip）。

> 注意
> 如果telnet超时请设置服务器安全组将8282端口开放。
> 如果需要测试websocket协议，需要将start_gateway.php中tcp改成websocket

## 端口
- websocket端口：9502（默认8282）
- register端口：1238

## 启动
```
php start.php start
```

测试
======
使用telnet命令测试（不要使用windows自带的telnet）
```shell
 telnet 127.0.0.1 9502
Trying 127.0.0.1...
Connected to 127.0.0.1.
Escape character is '^]'.
Hello 3
3 login
haha
3 said haha
```

## 使用域名
https://manual.workerman.net/doc/zh-cn/faq/secure-websocket-server.html

```
    location /ws {
        proxy_pass http://docker-php-fpm:9502;
        proxy_http_version 1.1;
        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header Connection "Upgrade";
        proxy_cache_bypass $http_upgrade;
        proxy_set_header X-Real-IP $remote_addr;
    }
```

## 参考
http://www.workerman.net/gatewaydoc/

https://github.com/walkor/GatewayWorker
