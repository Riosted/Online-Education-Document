# 微信支付API使用文档

## 1、申请资格（1.1～1.3皆为安卓端需要的步骤）

### 1.1 进入[微信开发平台](https://open.weixin.qq.com/)

### 1.2 完善个人信息

### 1.3 需要提供应用签名（release版的签名）。

- 安卓端参见[Android查看应用签名方法](https://www.jianshu.com/p/3d21f76a8edd)

### 1.4 如何申请微信支付接入

- 安卓端[APP接入支付](https://pay.weixin.qq.com/static/applyment_guide/applyment_detail_app.shtml)
- 微信端参见[小程序接入支付](https://pay.weixin.qq.com/static/applyment_guide/applyment_detail_miniapp.shtml)
- 网页端参见[PC网站接入支付](https://pay.weixin.qq.com/static/applyment_guide/applyment_detail_website.shtml)

## 3、商户系统和微信支付系统主要交互说明（前端统一交互步骤）：

### 3.1 用户在商户APP中选择商品，提交订单，选择微信支付。

### 3.2 商户后台收到用户支付单，调用微信支付统一下单接口。参见【[统一下单API](https://pay.weixin.qq.com/wiki/doc/api/app/app.php?chapter=9_1)】。

### 3.3 统一下单接口返回正常的prepay_id，再按签名规范重新生成签名后，将数据传输给APP。参与签名的字段名为appid，partnerid，prepayid，noncestr，timestamp，package。注意：package的值格式为Sign=WXPay

### 3.4 商户APP调起微信支付。api参见【[app端开发步骤说明](https://pay.weixin.qq.com/wiki/doc/api/app/app.php?chapter=8_5)】

### 3.5 商户后台接收支付通知。api参见【[支付结果通知API](https://pay.weixin.qq.com/wiki/doc/api/app/app.php?chapter=9_7)】

### 3.6 商户后台查询支付结果。api参见【[查询订单API](https://pay.weixin.qq.com/wiki/doc/api/app/app.php?chapter=9_2)】