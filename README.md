## 有一种鸟儿是永远也关不住的，因为它的每片羽翼都沾满了自由的光辉！

### 即将到来
- [ ] 变更/优化 服务端 Cloudflare Warp 的解锁配置
+ 原：无论什么全部都会走 Cloudflare Warp
+ 变更后：需要解锁的服务走 Cloudflare Warp，不需要解锁的不走

- [ ] 去广告
+ 仅能去掉一些基于域名的简单广告，不要抱有太多的幻想，很弱的

客户端的使用，请[看这里](https://github.com/yvgbk/gbzzZ/blob/main/gui.md)


### Hysteria 2 的优势
+ Brutal 拥塞控制算法：在丢包时并不会降低速度，而是通过计算的丢包率来提升速度进行补偿
+ UDP：延迟更低 耗时更短
+ 0RTT：延迟更低 耗时更短
+ HTTP/3：伪装成标准的 HTTP/3 流量
+ 对于没有适当身份验证凭据的第三方（无论是中间人还是主动探测者），Hysteria 代理服务器的行为就像标准 HTTP/3 Web 服务器一样
---------
+ 服务端使用 [sing-box](https://github.com/SagerNet/sing-box) 搭建
> ```sing-box``` v1.8.7，作者手动搭建
+ 服务端无审计，不会限制访问任何服务
> 当然，如果你故意搞事，就可能有了
+ 服务端已正确配置受信任的、有效的 TLS 证书
+ 服务端已允许 UDP 转发
> 如需转发 UDP，需要在客户端也开启 UDP 转发。一些服务需要用 UDP：Google Voice、游戏、大部分通话服务 等等
+ 服务端已配置 Google 永不送中
> 使用 Cloudflare Warp 来永不送中。精准分流，将所有 Google 的（旗下）域名和 ip 全部转发到 Cloudflare Warp
+ 服务端已启用```sniff_override_destination```
> 即使你发送被 DNS 污染的 ip 到服务端，仍可以探测出域名正常使用
+ 服务端已使用加密 DNS over TLS
> 使用 Cloudflare DNS ```tls://1.1.1.1```
+ 服务端已启用 Web 伪装
+ 服务端已配置解锁```Netflix、Disney+、ChatGPT、Reddit、XDA Forums```等等
> 使用 Cloudflare Warp 解锁
_______


*客户端 sing-box json 配置：*

+ 🇰🇷韩国-首尔
```json
{
  "type": "hysteria2",
  "tag": "hy2-out",
  "server": "kr-seoul-oracle-b0566e.ip1.shop",
  "server_port": 47352,
  "up_mbps": 100,
  "down_mbps": 100,
  "password": "r7BgF9N0M1qkkj",
  "tls": {
    "enabled": true,
    "server_name": "p.004456.xyz",
    "alpn": [
      "h3"
    ]
  }
}
```



+ 🇺🇸美国-圣克拉拉
```json
{
  "type": "hysteria2",
  "tag": "hy2-out",
  "server": "107.172.98.8",
  "server_port": 443,
  "up_mbps": 100,
  "down_mbps": 100,
  "password": "cg6uF2z9NAGkkj",
  "tls": {
    "enabled": true,
    "server_name": "p.004456.xyz",
    "alpn": [
      "h3"
    ]
  }
}
```
**type**
> 类型

**server**
> 服务器地址

**server_port**
> 服务器端口

**up_mbps**
> 最大上行宽带（Mbps）

> [!WARNING]
> ```up_mbps,down_mbps``` 你应该填写你本地网络的实际速率。如果为空，将使用 BBR 拥塞控制算法而不是 Brutal

> [!TIP]
> 如果你使用 Brutal 拥塞控制算法的速度不太理想，可以尝试切换到 BBR

**down_mbps**
> 最大下行宽带（Mbps）


**password**
> 认证密码

**tls.enabled**
> 启用 TLS

**server_name**
> 服务器名称指示

**alpn**
> 应用层协议协商

_____
### 如果你当地的运营商针对性屏蔽了 QUIC 或 HTTP/3 流量（但允许其他 UDP 流量），可以尝试这个配置，这个配置将数据包混淆成没有特征的 UDP 包
> [!NOTE]
> 默认 Hysteria 协议伪装为 HTTP/3。使用混淆将使服务器与标准的 QUIC 连接不兼容，失去 HTTP/3 伪装的能力。

*客户端 sing-box json 配置：*

+ 🇰🇷韩国-首尔
```json
{
  "type": "hysteria2",
  "tag": "hy2-out",
  "server": "kr-seoul-oracle-b0566e.ip1.shop",
  "server_port": 47353,
  "up_mbps": 100,
  "down_mbps": 100,
  "obfs": {
    "type": "salamander",
    "password": "obfsr7BgF9N0M1qkkj"
  },
  "password": "2r7BgF9N0M1qkkj",
  "tls": {
    "enabled": true,
    "server_name": "p.004456.xyz",
    "alpn": [
      "h3"
    ]
  }
}
```


+ 🇺🇸美国-圣克拉拉
```json
{
  "type": "hysteria2",
  "tag": "hy2-out",
  "server": "107.172.98.8",
  "server_port": 5000,
  "up_mbps": 100,
  "down_mbps": 100,
  "obfs": {
    "type": "salamander",
    "password": "duG1jb_1u4y9O6r"
  },
  "password": "2cg6uF2z9NAGkkj",
  "tls": {
    "enabled": true,
    "server_name": "p.004456.xyz",
    "alpn": [
      "h3"
    ]
  }
}
```

**obfs.type**
> QUIC 流量混淆器类型


**obfs.password**
> QUIC 流量混淆器密码

_____
### 如果你需要解锁 Netflix、ChatGPT、Reddit、Disney+、XDA Forums 等等一些服务，可以使用这个配置
> [!NOTE]
> 服务端使用 Cloudflare Warp 来解锁，使用 Cloudflare Warp 会减速，并且有一些 网站/服务/公司 会屏蔽 Cloudflare Warp 的 ip，如果你不需要解锁它们，请不要使用这个配置

*客户端 sing-box json 配置：*

+ 🇰🇷韩国-首尔
```json
{
  "type": "hysteria2",
  "tag": "hy2-out",
  "server": "kr-seoul-oracle-b0566e.ip1.shop",
  "server_port": 47354,
  "up_mbps": 100,
  "down_mbps": 100,
  "password": "wgr7BgF9N0M1qkkj",
  "tls": {
    "enabled": true,
    "server_name": "p.004456.xyz",
    "alpn": [
      "h3"
    ]
  }
}
```



+ 🇺🇸美国-圣克拉拉
```json
{
  "type": "hysteria2",
  "tag": "hy2-out",
  "server": "107.172.98.8",
  "server_port": 5001,
  "up_mbps": 100,
  "down_mbps": 100,
  "password": "wgcg6uF2z9NAGkkj",
  "tls": {
    "enabled": true,
    "server_name": "p.004456.xyz",
    "alpn": [
      "h3"
    ]
  }
}
```

#### 检测是否使用了 Cloudflare Warp

[点击检测](https://cloudflare.com/cdn-cgi/trace)

你会看到以下内容：
```txt
fl=123123123
h=cloudflare.com
ip=104.28.157.115
ts=123123123
visit_scheme=https
uag=Mozilla/5.0 (Linux; Android 10; K) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/122.0.0.0 Mobile Safari/537.36
colo=SJC
sliver=none
http=http/3
loc=US
tls=TLSv1.3
sni=plaintext
warp=on
gateway=off
rbi=off
kex=X25519
```

其中

```warp=on``` 使用了 Cloudflare Warp

```warp=off``` 没使用 Cloudflare Warp
___
## 自由的鸟儿会善用那锐利的鸟喙，再坚固的铁窗也锁不住它！
