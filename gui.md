### Clash Meta（Android、Windows、Mac OS）
```yaml
proxies:
- name: "hysteria2"
  type: hysteria2
  server: server.com
  port: 443
  #  up和down均不写或为0则使用BBR流控
   up: "100 Mbps" # 若不写单位，默认为 Mbps
   down: "100 Mbps" # 若不写单位，默认为 Mbps
  password: yourpassword
   obfs: salamander # 默认为空，如果填写则开启obfs，目前仅支持salamander
   obfs-password: yourpassword
   sni: server.com
   skip-cert-verify: false
   alpn:
     - h3
```

### [sing-box](https://github.com/SagerNet/sing-box)（全平台）[点我下载](https://github.com/SagerNet/sing-box/releases/tag/v1.8.6)
```json
{
  "type": "hysteria2",
  "tag": "hy2-out",
  "server": "", // 服务器地址
  "server_port": 1234, //服务器端口
  "up_mbps": 100, //最大上行速率，填写你本地网络实际速率
  "down_mbps": 100, //最大下行速率，填写你本地网络实际速率
  "obfs": {
    "type": "salamander",
    "password": "" // QUIC 流量混淆密码
  },
  "password": "", //认证密码
  "tls": {
  "enabled": true,
  "server_name": "", //服务器名称指示
  "alpn": [
    "h3"
  ]
 }
}
```

### [NekoBox](https://github.com/MatsuriDayo/NekoBoxForAndroid)（Android） [点我下载](https://github.com/MatsuriDayo/NekoBoxForAndroid/releases/tag/1.2.9)
1. 复制下面内容到剪切板
2. 打开 NekoBox
3. 点击右上角 + 号
4. 从剪切板导入
```
sn://hysteria?eNpjZ2BgyC7SLU7NL83RzS9KTM5J1U0yMDUzS9XLLDDUK87I_2DBwsDAxAABReZO6W6Wfga-hoXZ2a9AIo0FegYGJiamZnoVlb8aU4AiKWBhBhjgAmITc2PTTYxAxoy3C_a83b4BTG5_OX_l09l74z0qi0tSizITjeI9QkIC9I0bGwGgsi1n
sn://hysteria?eNpjZ2BgyC7SLU7NL83RzS9KTM5J1U0yMDUzS9XLLDDUK87I_2DBwsDAxAABRkXmTululn4GvoaF2dmvQEL5SWnFqKIFegYGJiamZnoVlb8aU4BKQJihkQEGuIDYxNzYdDMjkDHr7YI9b7dvAJPbX85f-XT23niPyuKS1KLMRKN4kOFWpSkFjY0AhEw1Tg
sn://hysteria?eNpjZ2BgyC7SLU7NL83RzS9KTM5J1U0yMDUzS9XLLDDUK87I_2DBwsDAxAAB5elF5k7pbpZ-Br6GhdnZr0BijQV6BgYmJqZmehWVvxpTgCIpYGEGGOACYhNzY9MtjEDGkrcL9rzdvgFMbn85f-XT2XvjPSqLS1KLMhON4j1CQgL0jeOT03TLE4sKdPNLSxobAVmaMuc
sn://hysteria?eNpjZ2BgMDQw1zM0N9KztNDbYcHCwMDEAAHJ6WalbkZVln6O7tnZr0AijQV6BgYmJqZmehWVvxpTgCIpYGEGGOACYhOTzYxAasbbBXvebt8FJnc839f3dPbeeI_K4pLUosxEo3iPkJAAfePGRgAv1iTt
sn://hysteria?eNpjZ2BgMDQw1zM0N9KztNDbYcHCwMDEAAFGyelmpW5GVZZ-ju7Z2a9AQiml7oZZSfGGpSaVlv5mnwr0DAxMTEzN9CoqfzWmgORBihoZYIALiE0NDDYwAulZbxfsebt9F5jc8Xxf39PZe-M9KotLUosyE43i85PSiq1KUwoaGwHyYSvU
sn://hysteria?eNpjZ2BgMDQw1zM0N9KztNDbYcHCwMDEAAHl6cnpZqVuRlWWfo7u2dmvQGKNBXoGBiYmpmZ6FZW_GlOAIilgYQYY4AJiUwODjYxAesnbBXvebt8FJnc839f3dPbeeI_K4pLUosxEo3iPkJAAfeP45DTd8sSiAt380pLGRgCJcSqW
```


### [NekoRay](https://github.com/MatsuriDayo/nekoray)（Linux、Windows）[点我下载](https://github.com/MatsuriDayo/nekoray/releases/tag/3.26)

### Hysteria 2 官方版
```yaml
server: your.domain.net:443 # (1)!

auth: Se7RAuFZ8Lzg # (2)!

bandwidth: # (3)!
  up: 100 mbps
  down: 100 mbps

obfs:
  type: salamander
  salamander:
    password: cry_me_a_r1ver

tls:
  sni: another.example.com 
  insecure: false 

socks5:
  listen: 127.0.0.1:1080 # (4)!

http:
  listen: 127.0.0.1:8080 # (5)!
```
