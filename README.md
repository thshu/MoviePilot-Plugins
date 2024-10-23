### 简介 
***
在原[suraxiuxiu库](https://github.com/suraxiuxiu/MoviePilot-Plugins/)的基础上添加了两个第三方应用的api

两个第三方api主要缓解以下问题：

1. 需要经常外出使用企业微信的用户，cookie容易失效，要在异地电脑安装、配置CookieCloud重新上传cookie频繁的问题
2. 在仅有手机微信的情况下更新cookie相对麻烦

触发使用两个第三方API的条件：
IP变化 且 从CookieCloud获取的cookie失效 且 填写两个token。

### 使用的第三方API
***
[pushplus推送](https://www.pushplus.plus/push1.html)、[helloimg图床](https://www.helloimg.com/)。两个api均需要实名认证才能正常调用。配置后才可以正常使用`/push_qr`


