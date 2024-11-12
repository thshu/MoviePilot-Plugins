### 简介 
***
* 定时检查公网IP覆盖填写到企业微信“可信IP”列表中。确保微信通知可用
* 在原[suraxiuxiu库](https://github.com/suraxiuxiu/MoviePilot-Plugins/)的基础上添加了第三方应用的api，扫码登录时收到验证码，请以`?`结尾发送到企业微信应用。如:`110103？`

第三方api主要缓解以下问题：

1. 需要经常外出使用企业微信的用户，cookie容易失效，要在异地电脑安装、配置CookieCloud重新上传cookie频繁
2. 在仅有手机微信的情况下更新cookie相对麻烦
3. 因没有及时扫码，期间公网IP又发生变化和可信IP不一致，导致企微应用无法发送通知




#### 可选的通知API
* 企业微信应用、[Server酱](https://sct.ftqq.com/sendkey、[AnPush](https://anpush.com/push/tool)、[PushPlus推送](https://www.pushplus.plus/push1.html)。配置任意一个后才可以正常使用`/push_qr`<br>
\* 使用企业微信应用通知，但要确保 **cookie失效** 到 **发送/push_qr** 这段时间，公网IP没有发生变化。以下有使用微信通知的示例图。

#### 远程命令
`/push_qr`也可以用来随时主动刷新cookie


### 使用说明
***
需要获取一个参数和配置CookieCloud，**检测周期**建议设置4分钟以上。如： ` */10 * * * *`，10分钟检测一次IP。

1. 获取应用ID，图中地址栏的末尾**红线部分就是应用ID**
![image](https://github.com/RamenRa/MoviePilot-Plugins/blob/main/docs/%E5%BA%94%E7%94%A8ID.JPG)

2. 启用CookieCloud，在MoviePilot的`设定`→`站点`中勾选 **“启用本地Cookiecloud服务器”**，即使用内建CookieCloud
![image](https://github.com/RamenRa/MoviePilot-Plugins/blob/main/docs/CC.JPG)

3. 使用企业微信应用接收示例，如果使用其他第三方推送则将图中`WeChat`替换成相应Token/API。
![image](https://github.com/RamenRa/MoviePilot-Plugins/blob/main/docs/wechat.JPG) <br>
\* 企业微信直接填写WeChat(注意区分大小写)
\* Server酱填写SCT开头的SendKey <br>
\* AnPush需要推送通道ID，使用英文逗号分隔。如：`推送通道ID,API` <br>
\* PushPlus填写一键复制的token <br>


### 问题反馈
***
* 可以在[原仓库链接已关闭的PULL](https://github.com/jxxghp/MoviePilot-Plugins/pulls?q=is%3Apr+is%3Aclosed)中，`Ctrl`+`F`查找`RamenRa`，进入对应页面后在评论区反馈问题
