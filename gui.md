### Clash Meta（Android、Windows、Mac OS）
[点击下载](https://wiki.metacubex.one/startup/client/)
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

### [sing-box](https://github.com/SagerNet/sing-box)（全平台）
[点击下载](https://github.com/SagerNet/sing-box/releases/tag/v1.8.6)
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

### [NekoBox](https://github.com/MatsuriDayo/NekoBoxForAndroid)（Android） 
[点击下载](https://github.com/MatsuriDayo/NekoBoxForAndroid/releases/tag/1.2.9)
~~1. 复制下面内容到剪切板
2. 打开 NekoBox
3. 点击右上角 + 号
4. 从剪切板导入~~
```
请按照配置手动输入添加！
```


### [NekoRay](https://github.com/MatsuriDayo/nekoray)（Linux、Windows）
[点击下载](https://github.com/MatsuriDayo/nekoray/releases/tag/3.26)

> [!CAUTION]
> 首次打开时，请选择使用 sing-box 核心。或者设置里切换核心为 sing-box


~~1. 复制下面内容到剪切板
2. 打开 NekoRay
3. Ctrl + V 或者鼠标右键从剪贴板添加~~

```
请按照配置手动输入添加！
```
### [Hysteria 2](https://github.com/apernet/hysteria) 官方
[点击下载](https://github.com/apernet/hysteria/releases/tag/app%2Fv2.2.4)

创建配置文件
假设你已经将可执行文件下载到了一个目录中，名字是 hysteria-linux-amd64-avx。在同目录下创建一个 config.yaml 文件，将以下内容复制粘贴进去

```yaml
server: your.domain.net:443 

auth: Se7RAuFZ8Lzg 

bandwidth: 
  up: 100 mbps #Hysteria 内置了两套拥塞控制算法（BBR 与 Brutal），使用哪个由是否提供了带宽值决定。 如果希望使用 BBR 而不是 Brutal，可以删除整个 bandwidth 部分。
  down: 100 mbps

obfs:
  type: salamander
  salamander:
    password: cry_me_a_r1ver

tls:
  sni: another.example.com 
  insecure: false 

socks5:
  listen: 127.0.0.1:1080 

http:
  listen: 127.0.0.1:8080
```

____
### Loon、Shadowrocket、Stash、Surge
我没有 ios 设备，欢迎[贡献](https://github.com/yvgbk/gbzzZ/issues)它们的专用分享链接或配置
