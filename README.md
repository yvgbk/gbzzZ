## 有一种鸟儿是永远也关不住的，因为它的每片羽翼都沾满了自由的光辉！


## Hysteria2 优势以及我为什么选择它
+ Brutal 拥塞控制：在丢包时并不会降低速度，而是通过计算的丢包率来提升速度进行补偿。
+ UDP：延迟更低耗时更短
+ 0RTT：延迟更低耗时更短
+ HTTP/3：伪装成标准的 HTTP/3 流量
+ 对于没有适当身份验证凭据的第三方（无论是中间人还是主动探测者），Hysteria 代理服务器的行为就像标准 HTTP/3 Web 服务器一样
---------
## 服务端介绍
+ 服务端无审计，不会主动限制访问任何服务
+ 服务端已正确配置受信任的、有效的 TLS 证书
+ 服务端已配置 ```sniff_override_destination``` 即使你发送被 DNS 污染的 ip 到服务端，仍可以嗅探出域名并正常使用
+ 服务端已使用加密 DNS（DOT） ```tls://1.1.1.1 ```
+ 服务端已启用 WEB 伪装
+ 服务端已配置解锁 Netflix、Diseny+、Chatgpt 等等（使用 Cloudflare Warp）（即将到来）
_______
*服务端使用的 sing-box 1.8.5，作者手动搭建*
```json
{
  "type": "hysteria2",
  "tag": "hy2-out",
  "server": "kr-seoul-oracle-b0566e.ip1.shop",
  "server_port": 36302,
  "up_mbps": 300,
  "down_mbps": 300,
  "password": "c1g6VH1a8zlgj",
  "tls": {
  "enabled": true,
  "server_name": "p.004456.xyz",
  "alpn": [
    "h3"
  ]
 }
}
```
+ 类型：
```
hysteria2
```
+ 服务器地址：
```
kr-seoul-oracle-b0566e.ip1.shop
```
+ 服务器端口：
```
36302
```
+ 最大上行宽带：
```
300Mbps
```
> [!WARNING]
> 300Mbps 是服务端设置的最大速率，你应该填写你本地网络的实际速率。如果为空，将使用 BBR 拥塞控制算法而不是 Hysteria CC

+ 最大下行宽带：
```
300Mbps
```
> [!WARNING]
> 300Mbps 是服务端设置的最大速率，你应该填写你本地网络的实际速率。如果为空，将使用 BBR 拥塞控制算法而不是 Hysteria CC

+ 认证密码：
```
c1g6VH1a8zlgj
```
+ 服务器名称指示：
```
p.004456.xyz
```
+ 应用层协议协商：
```
h3
```





## 自由的鸟儿会善用那锐利的鸟喙，再坚固的铁窗也锁不住它！
