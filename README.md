
## 严重声明：

此项目仅限于技术交流和探讨，在您测试完毕后必须在1秒钟内彻底删除项目副本。

此项目为bash一键脚本，其中涉及到的任何软件版权和责任归原作者所有。

## 友情提示：

在中国境内使用、传播、售卖、免费分享等任何翻墙服务，都是违法的。

如果你在中国境内使用、测试此项目脚本，或者使用此脚本搭建服务器发生以上违法行为，都有违作者意愿！

你必须立刻停止此行为！并删除脚本！


# V2RAY 基于 NGINX 的 VMESS+WS+TLS+Website(Use Host) 
### HTTP Header 分流 随机生成 Header，自带 Website 伪装站点 http 强制跳转 https，支持ssl非443端口，自动生成客户端config.json配置文件 web在线下载，重装自动清除残余的Http服务，每天自动升级最新的V2ray内核，支持 cdn 嵌套，自动续签ssl证书，自动生成Windows客户端和便捷启动脚本 一键添加开机自启动服务 一键开启系统ie代理。

使用：1.解析好域名； 2.运行一键安装脚本；
```
wget -N --no-check-certificate https://raw.githubusercontent.com/liyanglan/ws-tls_Website/master/w.sh && chmod +x w.sh && bash w.sh
```
[新手请使用 Debian8/9 纯净系统安装]

备用1：一键更换新的 UUID，同时升级 Windows 客户端 （new）
```
bash w.sh -n
```

备用2：一键删除服务器中储存的客户端 config.json 配置文件，防止 Website 被抓取 （rm）
```
bash w.sh -r
```

共享你的 V2ray 账号 （share）
```
bash w.sh -s

开启共享模式后，每周一自动更换 UUID 并推送至 Website 伪装站点首页。
为防止被恶意抓取，该模式下不提供客户端 config.json 文件下载。
```


嵌套 cloudflare (fullSSL+CDN) 节省资源 人人有责 如果你的ip没有墙 请勿开启
```
# 提前准备
购买域名、VPS；
注册cloudflare，提前24小时配置NS并解析域名。
确保所解析的域名Status位置关闭默认的cdn加速，变为灰色云朵状态。

# 开启 cloudflare (fullssl+cdn)
安装完毕一键脚本，并测试V2ray可以正常使用之后。
注意：在此步骤之前，勿必保持所解析的域名Status处为灰色云朵（及关闭cdn）。重做系统或重新安装时也勿必关闭此处设置。

1.开启全程ssl加密
在 Cloudflare 的 Crypto 那里设置 SSL 为 Full

2.开启cdn隐藏ip地址
返回 Status 点击灰色云朵图标 将其变成 橙色云朵状态 开启cdn，即是 DNS and HTTP proxy(CDN)

其它配置项尽量保持默认，这样有助于你排错。
```

提示：重装系统（Debian 8/9）能解决 100% 的安装错误，HTTP header 分流客户端配置容易出错认真检查配置信息。

### 申明：

此为 wulabing/V2Ray_ws-tls_bash_onekey 的另一个分歧版本

源作者网址：https://github.com/wulabing/V2Ray_ws-tls_bash_onekey
```
修改内容如下：
1.修改路径分流为 HTTP Header 分流（随机生成 Header）；
2.增加 Website 伪装站点。https://你的域名，（http 强制跳转 https 支持非443端口）；
3.自动清除残余的 Http 服务（某些系统自带的 Apache2 以及重装脚本时需要清除的 Nginx ）；
4.每天凌晨自动升级 V2ray 最新内核，每天自动重启vps（减少小内存主机kill进程的几率）；
5.增加 自动生成客户端 config.json 配置文件（Website 随机路径 在线下载，支持 v2rayNG 从 url 导入）；
6.增加 一键删除客户端 config.json 配置文件，防止 Website 被抓取；
7.增加 一键更换新的 UUID；
8.增加 客户端 Kitsunebi ShadowRay v2rayNG BifrostV 的 http header 分流配置提示。
9.增加 V2ray 账号共享功能。
10.增加 脚本重装判断 自动跳过 ssl 重复申请。
11.解决部分设备上偶尔的断流问题（客户端导入 config.json文件）
12.增加 自动生成 v2ray-core-windows 客户端和便捷启动脚本，一键添加开机自启动服务，一键开启系统ie代理。
```
### 其它与原版一致，详细说明请步移 https://github.com/wulabing/V2Ray_ws-tls_bash_onekey
