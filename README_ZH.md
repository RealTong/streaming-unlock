<h1 align="center">Welcome to streaming-unlock 👋</h1>
<p>
  <img alt="Version" src="https://img.shields.io/badge/version-1.0.0-blue.svg?cacheSeconds=2592000" />
  <a href="https://twitter.com/RealTong_run" target="_blank">
    <img alt="Twitter: RealTong" src="https://img.shields.io/twitter/follow/RealTong.svg?style=social" />
  </a>
</p>

> 如何使用这个项目?
[English](README.md) | 中文文档


## 🌟 功能

- [x] 使用AdguardHome解锁流媒体区域限制
- [x] 使用WebUI管理AdguardHome
- [x] 通过Web面板授权IP
- [x] 自定义更换上游DNS
- [x] Docker部署

## 安装
* 克隆代码`git clone https://github.com/RealTong/streaming-unlock.git && cd streaming-unlock`
* 运行代码`docker compose up -d`
* 访问`http://example:3000`，设置AdguardHome
* 在您的代理软件或者终端设备上设置DNS为部署本项目的服务器IP

## 配置
可以自己在webui中配置，也可以通过修改`adguardhome/conf/AdGuardHome.yaml`文件来配置(需要重启容器才能生效)

要使解锁生效则需要在AdguardHome中添加重写规则，例如这样写就可以解锁netflix(需要将示例中的1.1.1.1改为服务器的IP)

![DNSRewrite](dnsrewrite.png?raw=true)


## 🤝 为项目添砖加瓦
欢迎提出 Contributions, issues 与 feature requests!

## 感谢

### 如果这个项目对你产生了一点的帮助，请为这个项目点上一颗 ⭐️
<hr/>

### 感谢 JetBrains 免费的开源授权

<a href="https://www.jetbrains.com/" target="_blank">
<img src="jetbrains.png" height="200"/></a>