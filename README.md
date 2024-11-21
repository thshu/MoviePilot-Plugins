## 简介 
***
* 定时检查公网IP覆盖填写到企业微信“可信IP”列表中。确保微信通知可用（只支持docker部署的MoviePilot）
* 在原[suraxiuxiu库](https://github.com/suraxiuxiu/MoviePilot-Plugins/)的基础上添加了第三方api，扫码登录时收到验证码，请以`?`结尾发送到企业微信应用。如:`110103？`

* 第三方api主要缓解以下问题：

1. 需要经常外出使用企业微信的用户，cookie容易失效，要在异地电脑安装、配置CookieCloud重新上传cookie频繁
2. 在仅有手机微信的情况下更新cookie相对麻烦（**原仓库更新后已支持二维码推送到手机**）
3. 因没有及时扫码，期间公网IP发生变化与可信IP不一致，导致企微应用无法发送通知




### 可选的通知
* 企业微信应用、[Server酱](https://sct.ftqq.com/sendkey)、[AnPush](https://anpush.com/push/tool)、[PushPlus推送](https://www.pushplus.plus/push1.html)。配置任意一个后才可以正常使用`/push_qr`<br>
#### 关于微信作为主通知，第三方作为备用
* 此方案目前**只支持V1**,先放置在[Debug仓库v1.3.6](https://github.com/Rob0088/MoviePilot-Plugins)
* 填写格式参考以下说明，每个通知方式以`||`隔开。如配置微信和Server酱：`WeChat,WangFeng||SCTxxx`

#### 远程命令
* 直接在企业微信应用发送`/push_qr`，MoviePoilt收到后插件开始推送登录二维码。也可以用来**测试通知是否可用**


## 使用说明
***
* 需要获取一个参数和配置CookieCloud。如果收到验证码，请以`?`结尾发送到企业微信应用。如:`110103？`


1. 获取应用ID，图中地址栏的末尾**红线部分就是应用ID**
![image](https://github.com/RamenRa/MoviePilot-Plugins/blob/main/docs/%E5%BA%94%E7%94%A8ID.JPG)

2. 启用CookieCloud，在MoviePilot的`设定`→`站点`中勾选 **“启用本地Cookiecloud服务器”**，即使用内建CookieCloud
   * **关于不使用CookieCloud**，Cookie会没地方保存，导致下一次检查登录失败，进而提示**Cookie失效**。该插件就变成了一次性修改IP的插件(====预计v1.5.2后改善为：当不使用cc时，插件不重启就不失效====)。 
   <br>
   
   * **关于cookie失效太快的可能**：如果你上传Cookie是使用浏览器的CookieCloud插件，修改IP插件会使用该Cookie，此时请**不要使用插件中的任何扫码**行为。否则会挤掉你浏览器的Cookie，而浏览器又会将**无效的Cookie**上传到CookieCloud服务器。
![image](https://github.com/RamenRa/MoviePilot-Plugins/blob/main/docs/CC.JPG)

4. 使用企业微信应用接收示例，第三方推送则将图中 `WeChat,WangFeng` 替换成相应Token/API。<br>
- **特别注意**：MoviePilotV2中**必须**指定userid且插件版本1.5.1及以上
![image](https://github.com/RamenRa/MoviePilot-Plugins/blob/main/docs/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE_20241115_005530.png) <br>
\* 企业微信：V1直接填写WeChat，请先确认企微应用已可以**正常交互**，本插件只负责修改可信IP <br>
\* Server酱：填写SCT开头的SendKey，支持Server<sup>3</sup>(虽说支持系统级推送，但扫码体验并不好) <br>
\* AnPush：需要在左侧`通道配置`找到通道ID，填写 `通道ID,API` <br>
\* PushPlus：填写一键复制的token <br>



## 问题反馈
***
* 可以在[原仓库链接已关闭的PULL](https://github.com/jxxghp/MoviePilot-Plugins/pulls?q=is%3Apr+is%3Aclosed)中，`Ctrl`+`F`查找`RamenRa`，进入对应页面后在评论区反馈问题。最好带上插件设置和日志截图，企业微信通知相关的再加一张MoviePilot设置里微信通知设置的截图 <br>
<p align="center"> ⭐ :point_left: ⭐ :point_right: ⭐ :point_left: ⭐ :point_right: ⭐ :point_left: ⭐ :point_right: ⭐ :point_left: ⭐ :point_right: ⭐ :point_left: ⭐ </p>
