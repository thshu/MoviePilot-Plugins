## 简介 
***
* 定时检查公网IP覆盖填写到企业微信“可信IP”列表中。确保微信通知可用
* 在原[suraxiuxiu库](https://github.com/suraxiuxiu/MoviePilot-Plugins/)的基础上添加了第三方api，扫码登录时收到验证码，请以`?`结尾发送到企业微信应用。如:`110103？`

* 第三方api主要缓解以下问题：
1. 需要经常外出使用企业微信的用户，cookie容易失效，要在异地电脑安装、配置CookieCloud重新上传cookie频繁
2. 在仅有手机微信的情况下更新cookie相对麻烦（**原仓库v2.0后已支持二维码推送到手机**）
3. 因没有及时扫码，期间公网IP发生变化与可信IP不一致，导致企微应用无法发送通知（v1可以用第三方为备用，企业微信发送失败时会自动尝试第三方）

### 可选的通知
* 企业微信应用、[Server酱](https://sct.ftqq.com/sendkey)、[AnPush](https://anpush.com/push/tool)、[PushPlus推送](https://www.pushplus.plus/push1.html)。配置任意一个后才可以正常使用`/push_qr`<br>

### 远程命令 /push_qr
* 直接在企业微信应用发送`/push_qr`，MoviePoilt收到后插件开始推送登录二维码。也可以用来**测试通知是否可用**
* MP可能会因网络波动没有收到推送命令，尤其是使用Cloudflare隧道的用户。多发送几次即可。收没收到以**MP的日志为准**。


## 使用说明
***
* 需要获取一个参数和配置CookieCloud。如果收到验证码，请以`?`结尾发送到企业微信应用。如:`110103？`
* 从指定URL获取IP。[配置方式](https://github.com/RamenRa/MoviePilot-Plugins#%E5%85%B3%E4%BA%8E%E5%A2%9E%E5%8A%A0%E4%BB%8E%E6%8C%87%E5%AE%9Aurl%E8%8E%B7%E5%8F%96ip-%E9%A2%84%E8%AE%A1v152%E5%AE%9E%E8%A3%85-560)

1. 获取应用ID，图中地址栏的末尾**红线部分就是应用ID**
![image](https://www.helloimg.com/i/2024/11/15/67369975b7769.jpg)

2. 启用CookieCloud，在MoviePilot的`设定`→`站点`中勾选 **“启用本地Cookiecloud服务器”**，即使用内建CookieCloud
* 可以不启用，要取消勾选插件配置中的`使用CookieCloud`开关，这样MP重启后Cookie就会失效。
![image](https://www.helloimg.com/i/2024/11/15/67369975dd82f.jpg)

3. 使用企业微信应用通知示例。使用第三方推送则在`通知方式`填写相应Token/API。保存后，等待检测周期到后会自动开始检查ip，或使用一次`立即检测一次`
* 多个通知以`||`分隔，在MoviePilotV2使用多个通知时，微信设为首选其它通知将会无效。[配置方式](https://github.com/RamenRa/MoviePilot-Plugins#%E5%85%B3%E4%BA%8E%E5%BE%AE%E4%BF%A1%E4%BD%9C%E4%B8%BA%E4%B8%BB%E9%80%9A%E7%9F%A5%E7%AC%AC%E4%B8%89%E6%96%B9%E4%BD%9C%E4%B8%BA%E5%A4%87%E7%94%A8) <br>
![image](https://www.helloimg.com/i/2024/11/15/6736997616de8.png) 
* 企业微信：填写`WeChat`，上图还指定了微信的userid[非必填]。请确保企微应用已可以**正常交互** <br>
* Server酱：填写SCT开头的SendKey，支持Server<sup>3</sup>(虽说支持系统级推送，但扫码体验并不好) <br>
* AnPush：填写 `通道ID,API` ，在左侧`通道配置`找到通道ID <br>
* PushPlus：填写一键复制的Token <br>



### 关于微信作为主通知，第三方作为备用
* 只支持MoviePilot V1，在微信发送消息失败时，自动尝试使用下一个通知
* 参考以上说明，每个通知方式以`||`隔开。如配置微信和Server酱：`WeChat,WangFeng||SCTxxx`

### 关于"增加从指定url获取IP" 预计v1.5.2实装 [示例 #560](https://github.com/jxxghp/MoviePilot-Plugins/issues/560)

* 后续想取消自定义的url可能需要重启MP,预计v1.5.3及以后不需要重启

### 关于Server<sup>3</sup>二维码推送到服务号
* 可以填写 `Server3的key,普通key` 实现将失效通知发给Server<sup>3</sup>系统级推送，二维码发给服务号 <br>

## 问题反馈
***
* 在[Issuse](https://github.com/RamenRa/MoviePilot-Plugins/issues)里反馈,附上插件设置和日志截图,日志中相同的错误重复输出的，重点关注第一次出现错误和最后一次的地方。 <br>
<p align="center"> ⭐ :point_left: ⭐ :point_right: ⭐ :point_left: ⭐ :point_right: ⭐ :point_left: ⭐ :point_right: ⭐ :point_left: ⭐ :point_right: ⭐ :point_left: ⭐ </p>


