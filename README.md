<h1 align="center">Welcome to streaming-unlock 👋</h1>
<p>
  <img alt="Version" src="https://img.shields.io/badge/version-1.0.0-blue.svg?cacheSeconds=2592000" />
  <a href="https://twitter.com/RealTong_run" target="_blank">
    <img alt="Twitter: RealTong" src="https://img.shields.io/twitter/follow/RealTong.svg?style=social" />
  </a>
</p>

> How to use this project?
English | [中文文档](README_ZH.md)


## 🌟 Features

- [x] Unlock streaming zone restrictions with AdguardHome
- [x] Managing AdguardHome with WebUI
- [x] IP authorization via web panel
- [x] Customized replacement of upstream DNS
- [x] Docker Deployment

## Install
* Cloning Code `git clone https://github.com/RealTong/streaming-unlock.git && cd streaming-unlock`
* Run `docker compose up -d`
* Click `http://example:3000`，Setting up AdguardHome
* Set DNS on your proxy software or terminal device to the IP of the server where the project is deployed

## Configuration
You can configure it yourself in webui or by modifying the `adguardhome/conf/AdGuardHome.yaml` file (need to restart the container to take effect)

To make the unlocking work you need to add a rewrite rule to AdguardHome, e.g. write this to unlock netflix (you need to change 1.1.1.1 in the example to the IP of the server)

![DNSRewrite](image/dnsrewrite.png?raw=true)

## Q&A
> `docker compose up -d`An error occurred `Error response from daemon: Ports are not available: exposing port UDP 0.0.0.0:53 -> 0.0.0.0:0: listen udp 0.0.0.0:53: bind: Only one usage of each socket address (protocol/network address/port) is normally permitted.` (Port 53 is occupied) What to do

1. sudo systemctl stop systemd-resolved
2. sudo systemctl disable systemd-resolved
3. docker compose up -d
4. Refer to [Configuration](#Configuration), to configure
5. Then you will see that the unlock is working. The reason is that AdguardHome is acting as our DNS server and occupying port 53, but the DNS server of the host is still pointing to `127.0.0.53:53` of `systemd-resolved`, so we can change the DNS of the host and it will be fine.
6. `vim /etc/resolv.conf` Modify nameserver 127.0.0.53 to nameserver 127.0.0.1

## 🤝 Contributing
Contributions, issues and feature requests are welcome!

## Show your support

### Give a ⭐️ if this project helped you!
<hr/>

### Thanks to JetBrains for the free open source license

<a href="https://www.jetbrains.com/" target="_blank">
<img src="image/jetbrains.png" height="200"/></a>