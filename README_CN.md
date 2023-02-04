![logo](https://raw.githubusercontent.com/johnrosen1/trojan-gfw-script/master/logo.png)
# VPS Toolbox
## 此Bash Script将帮助你以极快的速度从零开始打造一台全能的代理+下載+監控一体化的伺服器.

### 使用方法
安裝依賴(Debian/Ubuntu)
```
apt-get update && apt-get install sudo whiptail curl locales -y && sudo -i
```
安裝依賴(Centos)
```
yum update -y && yum install sudo newt curl -y && sudo -i
```
運行腳本
```
sudo bash -c "$(curl -fsSL https://raw.githubusercontent.com/johnrosen1/trojan-gfw-script/master/vpstoolbox.sh)"
```
![menu](https://raw.githubusercontent.com/johnrosen1/trojan-gfw-script/master/mainmenu.png)
![choose](https://raw.githubusercontent.com/johnrosen1/trojan-gfw-script/master/1.png)

旧版本（包含V2ray和ss,此版本不再提供任何支援）
```
sudo bash -c "$(curl -fsSL https://raw.githubusercontent.com/johnrosen1/trojan-gfw-script/master/trojangui.sh)"
```

#### 運行前的要求:
1. 請 **使用root用戶運行**(sudo -i)
2. 請在运行本脚本前先 **[购买一个域名](https://www.namesilo.com/?rid=685fb47qi)** 并 **[完成A记录 dns解析](https://dnschecker.org/)**!
3. 請在你的控制面板上 **開放 Tcp 端口 [80](https://www.speedguide.net/port.php?port=80) 以及 [443](https://www.speedguide.net/port.php?port=443) 并关闭 Cloudflare CDN**
4. 請不要使用阿里內網DNS(更新極其緩慢) 推薦[1.1.1.1](https://1.1.1.1/) !
```
echo "nameserver 1.1.1.1" > '/etc/resolv.conf'
```
5. 請 **手动将Qbittorrent下载路径改为 /usr/share/nginx/qbt/ !**

6. 若使用自定义证书只需与密钥一起放置于/etc/trojan文件夹中即可，无需修改名称 。

#### [Telegram](https://telegram.org/) 頻道 以及 群組

### https://t.me/johnrosen1

### https://t.me/trojanscript

## 如果你覺得有用 , 請給star ★, 謝謝!
#### 脚本特性支援:

1. 安裝並配置 **[NGINX](https://www.nginx.com/)**
2. 申请并续签 [let's encrypt 证书](https://letsencrypt.org/) and **全自动在证书续签完成后reload Trojan-GFW**
3. OS 探測 **支援 [Debian](https://www.debian.org/) [Ubuntu](https://ubuntu.com/) Centos**
4. [domain resolve verification](https://en.wikipedia.org/wiki/Nslookup)
5. [iptables](https://en.wikipedia.org/wiki/Iptables)(包括 ipv6) 防火墙配置以及 [iptables-persistent](https://github.com/zertrin/iptables-persistent)
6. 生成 [客戶端配置文件](https://trojan-gfw.github.io/trojan/config) (包括 Trojan-GFW 和 V2ray )
8. [Nginx 效能優化](https://www.johnrosen1.com/nginx1/)
9. [Trojan-GFW ***trojan://***  分享链接 以及 二维码 生成](https://github.com/trojan-gfw/trojan-url)
10.  [https 301 redirect](https://en.wikipedia.org/wiki/HTTP_301) 不會影響證書的續簽
11. [HSTS header](https://securityheaders.com/)
12. ***隨機html偽裝模板選擇***
13. [***完整的 IPv6 支持***](https://en.wikipedia.org/wiki/IPv6)
14. ***[時間校準](https://www.freedesktop.org/software/systemd/man/timedatectl.html)***
15. ***失败自动重启*** 
16. [卸載 Aliyun Aegis](https://www.johnrosen1.com/ali-iso/)
17. 安裝並配置 **[Trojan-GFW](https://github.com/trojan-gfw/trojan) [Dnscrypt-proxy](https://www.dnscrypt.org/) [Qbittorrent](https://www.qbittorrent.org/) [Bittorrent-Tracker](https://github.com/webtorrent/bittorrent-tracker) [Aria2](https://github.com/aria2/aria2) [Filebrowser](https://github.com/filebrowser/filebrowser) [Netdata](https://github.com/netdata/netdata) [V2ray](https://www.v2ray.com/index.html) and [Shadowsocks](https://shadowsocks.org/en/index.html)([V2ray-plugin](https://github.com/shadowsocks/v2ray-plugin)) [TOR](https://famicoman.com/2018/01/03/configuring-and-monitoring-a-tor-middle-relay/)**
18. [V2ray ***vmess://*** 分享链接 生成](https://github.com/boypt/vmess2json) + Shadowsocks ss:// 分享链接 和 二维码 生成
19. [***vmess or ss + tls + websocket + nginx*** 配置](https://guide.v2fly.org/advanced/wss_and_web.html)
7.  [TCP Turbo](https://github.com/shadowsocks/shadowsocks/wiki/Optimizing-Shadowsocks) ( **[TCP-BBR](https://github.com/google/bbr)** 已包含)
20. ***[BBRPLUS](https://github.com/chiakge/Linux-NetSpeed)***
21. ***[TLS1.3 ONLY](https://wiki.openssl.org/index.php/TLS1.3)***
22. 手动 检查更新 包括 Trojan-gfw v2ray ss
23. 完全/部分 卸載

**如果你需要更多功能, 请 open a Github issue / 提交pull request.(Centos相关issue将被列为低优先级)**

### VPS 推薦 (无个人aff)

#### https://www.kamatera.com/ 1MONTH300 优惠码首月免费

#### 相關鏈接

Qbittorrent 相关: https://www.johnrosen1.com/qbt/

Trojan-GFW 相关: https://www.johnrosen1.com/trojan/

### 查錯指南

网络相关：

https://tools.ipip.net/ping.php

伺服器相关：

```
https://github.com/trojan-gfw/trojan-quickstart
sudo nginx -t
sudo systemctl status trojan
sudo systemctl status nginx
sudo systemctl status v2ray
sudo systemctl status tor
sudo systemctl status tor@default
sudo systemctl status dnsmasq
sudo systemctl status qbittorrent
sudo systemctl status tracker
sudo systemctl status aria2
sudo systemctl status filebrowser
sudo systemctl status netdata
journalctl -e -u trojan.service
cat /var/log/v2ray/error.log
cat /usr/local/etc/trojan/config.json
cat /etc/nginx/conf.d/trojan.conf
cat /etc/v2ray/config.json
cat /etc/aria.conf
crontab -l
sudo ~/.acme.sh/acme.sh --cron //仅当使用let's encrypt证书是有效
timedatectl
iptables -L -v
```
### 結果例子
```
trojan://trojanscript@www.johnrosen.top:443
```
![Trojan-GFW QR code](https://raw.githubusercontent.com/johnrosen1/trojan-gfw-script/master/trojanscript.png)


