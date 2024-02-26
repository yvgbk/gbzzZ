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


### [NekoRay](https://github.com/MatsuriDayo/nekoray)（Linux、Windows）
[点击下载](https://github.com/MatsuriDayo/nekoray/releases/tag/3.26)

> [!CAUTION]
> 首次打开时，请选择使用 sing-box 核心。或者设置里切换核心为 sing-box


1. 复制下面内容到剪切板
2. 打开 NekoRay
3. Ctrl + V 或者鼠标右键从剪切贴板添加

```
nekoray://hysteria2#eyJfdiI6MCwiYWRkciI6IjEwNy4xNzIuOTguOCIsImFsbG93SW5zZWN1cmUiOmZhbHNlLCJjb25uZWN0aW9uUmVjZWl2ZVdpbmRvdyI6MCwiZGlzYWJsZU10dURpc2NvdmVyeSI6ZmFsc2UsImRpc2FibGVTbmkiOmZhbHNlLCJkb3dubG9hZE1icHMiOjEwMCwiZm9yY2VFeHRlcm5hbCI6ZmFsc2UsImhvcEludGVydmFsIjoxMCwibmFtZSI6IvCfh7rwn4e4576O5Zu9X0h5c3RlcmlhMl9IVFRQLzMiLCJwYXNzd29yZCI6ImNnNnVGMno5TkFHa2tqIiwicG9ydCI6NDQzLCJzbmkiOiJwLjAwNDQ1Ni54eXoiLCJzdHJlYW1SZWNlaXZlV2luZG93IjowLCJ1cGxvYWRNYnBzIjoxMDB9
nekoray://hysteria2#eyJfdiI6MCwiYWRkciI6IjEwNy4xNzIuOTguOCIsImFsbG93SW5zZWN1cmUiOmZhbHNlLCJjb25uZWN0aW9uUmVjZWl2ZVdpbmRvdyI6MCwiZGlzYWJsZU10dURpc2NvdmVyeSI6ZmFsc2UsImRpc2FibGVTbmkiOmZhbHNlLCJkb3dubG9hZE1icHMiOjEwMCwiZm9yY2VFeHRlcm5hbCI6ZmFsc2UsImhvcEludGVydmFsIjoxMCwibmFtZSI6IvCfh7rwn4e4576O5Zu9X0h5c3RlcmlhMl9IVFRQLzNfY2Ytd2FycC1vdXQiLCJwYXNzd29yZCI6IndnY2c2dUYyejlOQUdra2oiLCJwb3J0Ijo1MDAxLCJzbmkiOiJwLjAwNDQ1Ni54eXoiLCJzdHJlYW1SZWNlaXZlV2luZG93IjowLCJ1cGxvYWRNYnBzIjoxMDB9
nekoray://hysteria2#eyJfdiI6MCwiYWRkciI6IjEwNy4xNzIuOTguOCIsImFsbG93SW5zZWN1cmUiOmZhbHNlLCJjb25uZWN0aW9uUmVjZWl2ZVdpbmRvdyI6MCwiZGlzYWJsZU10dURpc2NvdmVyeSI6ZmFsc2UsImRpc2FibGVTbmkiOmZhbHNlLCJkb3dubG9hZE1icHMiOjEwMCwiZm9yY2VFeHRlcm5hbCI6ZmFsc2UsImhvcEludGVydmFsIjoxMCwibmFtZSI6IvCfh7rwn4e4576O5Zu9X0h5c3RlcmlhMl9vYmZzOnVkcCIsIm9iZnNQYXNzd29yZCI6ImR1RzFqYl8xdTR5OU82ciIsInBhc3N3b3JkIjoiMmNnNnVGMno5TkFHa2tqIiwicG9ydCI6NTAwMCwic25pIjoicC4wMDQ0NTYueHl6Iiwic3RyZWFtUmVjZWl2ZVdpbmRvdyI6MCwidXBsb2FkTWJwcyI6MTAwfQ==
nekoray://hysteria2#eyJfdiI6MCwiYWRkciI6ImtyLXNlb3VsLW9yYWNsZS1iMDU2NmUuaXAxLnNob3AiLCJhbGxvd0luc2VjdXJlIjpmYWxzZSwiY29ubmVjdGlvblJlY2VpdmVXaW5kb3ciOjAsImRpc2FibGVNdHVEaXNjb3ZlcnkiOmZhbHNlLCJkaXNhYmxlU25pIjpmYWxzZSwiZG93bmxvYWRNYnBzIjoxMDAsImZvcmNlRXh0ZXJuYWwiOmZhbHNlLCJob3BJbnRlcnZhbCI6MTAsIm5hbWUiOiLwn4ew8J-Ht-mfqeWbvV9IeXN0ZXJpYTJfSFRUUC8zIiwicGFzc3dvcmQiOiJyN0JnRjlOME0xcWtraiIsInBvcnQiOjQ3MzUyLCJzbmkiOiJwLjAwNDQ1Ni54eXoiLCJzdHJlYW1SZWNlaXZlV2luZG93IjowLCJ1cGxvYWRNYnBzIjoxMDB9
nekoray://hysteria2#eyJfdiI6MCwiYWRkciI6ImtyLXNlb3VsLW9yYWNsZS1iMDU2NmUuaXAxLnNob3AiLCJhbGxvd0luc2VjdXJlIjpmYWxzZSwiY29ubmVjdGlvblJlY2VpdmVXaW5kb3ciOjAsImRpc2FibGVNdHVEaXNjb3ZlcnkiOmZhbHNlLCJkaXNhYmxlU25pIjpmYWxzZSwiZG93bmxvYWRNYnBzIjoxMDAsImZvcmNlRXh0ZXJuYWwiOmZhbHNlLCJob3BJbnRlcnZhbCI6MTAsIm5hbWUiOiLwn4ew8J-Ht-mfqeWbvV9IeXN0ZXJpYTJfb2Jmczp1ZHAiLCJvYmZzUGFzc3dvcmQiOiJvYmZzcjdCZ0Y5TjBNMXFra2oiLCJwYXNzd29yZCI6IjJyN0JnRjlOME0xcWtraiIsInBvcnQiOjQ3MzUzLCJzbmkiOiJwLjAwNDQ1Ni54eXoiLCJzdHJlYW1SZWNlaXZlV2luZG93IjowLCJ1cGxvYWRNYnBzIjoxMDB9
nekoray://hysteria2#eyJfdiI6MCwiYWRkciI6ImtyLXNlb3VsLW9yYWNsZS1iMDU2NmUuaXAxLnNob3AiLCJhbGxvd0luc2VjdXJlIjpmYWxzZSwiY29ubmVjdGlvblJlY2VpdmVXaW5kb3ciOjAsImRpc2FibGVNdHVEaXNjb3ZlcnkiOmZhbHNlLCJkaXNhYmxlU25pIjpmYWxzZSwiZG93bmxvYWRNYnBzIjoxMDAsImZvcmNlRXh0ZXJuYWwiOmZhbHNlLCJob3BJbnRlcnZhbCI6MTAsIm5hbWUiOiLwn4ew8J-Ht-mfqeWbvV9IeXN0ZXJpYTJfSFRUUC8zX2NmLXdhcnAtb3V0IiwicGFzc3dvcmQiOiJ3Z3I3QmdGOU4wTTFxa2tqIiwicG9ydCI6NDczNTQsInNuaSI6InAuMDA0NDU2Lnh5eiIsInN0cmVhbVJlY2VpdmVXaW5kb3ciOjAsInVwbG9hZE1icHMiOjEwMH0=
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
