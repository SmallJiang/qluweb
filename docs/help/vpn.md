<!-- markdownlint-disable MD033 -->

# 齐鲁工业大学 VPN 服务

为方便广大校（院）师生在外访问校内网络资源及各信息系统，网络信息中心开通了 校外 VPN 服务。通过使用 VPN，您可以在校外或没有校园网账号的情况下，轻松访问校内的网络信息资源。

---

## 在线使用 VPN

部分简易的服务，例如教务系统、校内邮箱可以通过 [工大 VPN 网站](https://vpn.qlu.eu.cn) 使用，无需下载客户端。
您只需要进入 VPN 网站后，通过一号通系统登陆，即可点击访问您所需的服务。

<img src="/img/vpn1.png" width=100% />

若想要访问的服务呈灰色，且页面顶端提示未安装客户端，则需要 [安装客户端](##使用客户端连接 VPN)

<img src="/img/vpn-require.png" width=100% />

---

## 使用客户端连接 VPN

部分复杂的或者未被添加进 VPN 服务列表内的网络资源，需要使用客户端连接 VPN 使用。

我校采用深信服的 EasyConnect 客户端，可以到 [客户端下载页面](https://vpn.qlu.edu.cn/resource/client/windows/aTrustInstaller.exe) 下载适合您设备的应用程序。

<img src="/img/vpn-download.png" width=100% />

下载完成后，打开下载好的客户端安装程序进行安装

<img src="/img/vpn-install.png" width=100% />

安装完成后，若浏览器中已登录[工大 VPN 网站](https://vpn.qlu.eu.cn)，
刷新该网站页面即可成功登录客户端

如浏览器中未登录工大 VPN 网站，可打开工大 VPN 客户端，

<center class="half">
<img src="/img/vpn-app.png" width=15% />
</center>

在首页地址框填入我校 VPN 服务地址：[vpn.qlu.edu.cn](https://vpn.qlu.edu.cn/)

<img src="/img/vpn2.png" width=100% />

然后点击使用一网通登陆 VPN 系统后即可连接校内网络资源

<img src="/img/vpn3.png" width=100% />

---

## 关于 EasyConnect 的兼容性问题

**本章节旨在帮助各位师生解决深信服 EasyConnect 客户端带来的一系列兼容性问题，由本文档作者根据个人经验撰写，并非深信服公司官方的解决方案。作者也不对解决方案的可用性及带来的后果负有任何直接或间接的责任。本章节没有任何对深信服公司 EasyConnect 产品的功能或设计进行批评、否定、抵制的意味和目的。**

深信服 EasyConnect 客户端的功能实现较为独特，采用 LSP 劫持、DNS 劫持、修改注册表、静默签发根 CA 证书等方式，容易导致各种系统异常：

- 游戏无法正常运行：例如 CS:GO 的反作弊无法启动导致游戏崩溃
- IPv6 功能异常：由于注册表被修改导致无法使用 IPv6 网络
- DNS 解析异常：EasyConnect 接管并劫持系统 DNS，导致部分网站无法加载
- 网络安全隐患：EasyConnect 会静默签发系统根证书，并在用户删除后再次静默安装，不利于网络数据安全
- 不兼容 ARM 架构系统：深信服公司对于产品的迭代较为缓慢，目前还不支持 ARM 架构

如果您的系统遇到了以上问题，建议将 EasyConnect 安装在虚拟机环境或是使用 Docker 容器（操作难度较高，适合专业人士）封装该应用。参见由重庆大学 @Hagb 的项目：[docker-easyconnect](https://github.com/Hagb/docker-easyconnect)
