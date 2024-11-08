### 简介 
***
* 定时检查公网IP覆盖填写到企业微信“可信IP”列表中。确保微信通知可用
* 在原[suraxiuxiu库](https://github.com/suraxiuxiu/MoviePilot-Plugins/)的基础上添加了两个第三方应用的api，扫码登录时收到验证码，请以`?`结尾发送到企业微信应用。如:`110103？`

两个第三方api主要缓解以下问题：

1. 需要经常外出使用企业微信的用户，cookie容易失效，要在异地电脑安装、配置CookieCloud重新上传cookie频繁
2. 在仅有手机微信的情况下更新cookie相对麻烦




#### 两个可选的第三方API
* [pushplus推送](https://www.pushplus.plus/push1.html)、[helloimg图床](https://www.helloimg.com/)。两个api均需要实名认证才能正常调用。配置后才可以正常使用`/push_qr`
* 触发使用两个第三方API的条件：`IP变化` 且 `从CookieCloud获取的cookie失效` 且 `填写两个token`。

#### 远程命令
* **检测周期**建议设置` */10 * * * *`，10分钟检测一次IP。pushplus目前每日限制200条消息，又因为二维码有效期为2分钟左右。用户可能会有8分钟在等待二维码，所以添加了`/push_qr`，也可以用来随时主动刷新cookie


### 使用说明
***
需要获取一个参数和配置CookieCloud

1. 获取应用ID，图中地址栏的末尾**红线部分就是应用ID**
![image](https://github.com/RamenRa/MoviePilot-Plugins/blob/main/docs/%E5%BA%94%E7%94%A8ID.JPG)

2. 启用CookieCloud，在MoviePilot的`设定`→`站点`中勾选 **“启用本地Cookiecloud服务器”**，即使用内建CookieCloud
![image](https://github.com/RamenRa/MoviePilot-Plugins/blob/main/docs/CC.JPG)

