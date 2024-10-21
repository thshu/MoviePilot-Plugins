### 简介 
***
在原[suraxiuxiu库](https://github.com/suraxiuxiu/MoviePilot-Plugins/)的基础上添加了两个第三方应用的api

两个第三方api主要缓解以下问题：

1. 需要经常外出使用企业微信的用户，cookie容易失效，要在异地电脑安装、配置CookieCloud重新上传cookie频繁的问题
2. 在仅有手机微信的情况下更新cookie相对麻烦

触发使用两个第三方API的条件：
公网IP发生变化 且 从CookieCloud获取的cookie失效 且 填写了两个token

* 小提示：使用CookieCloud浏览器插件上传的cookie失效极快，但是用插件二维码登方式录获取到cookie却正常。也有可能只是我设置的问题，个人暂时停用了CC的浏览器插件

* 虽然没有任何说明，但还是有细心的伙伴发现了`/push_qr_code`远程命令，目前本人还没研究明白远程命令。1.1.x版本应该都是用不了的

### 使用的第三方API
***
[pushplus推送](https://www.pushplus.plus/push1.html)、[helloimg图床](https://www.helloimg.com/)。两个api均需要实名认证才能正常调用。


