# 统一支付接口
本文档适用于`v2`版本接口

#### 第一步：获取接口调用信息
接口调用需要如下信息：
- 1.服务器地址：https://m.capay.cc/v2 接口统一使用`POST`进行调用
- 2.平台SM2公钥：由平台提供，调用接口时用于加密及接收通知时用于验签
- 3.终端号及商户号：由平台提供，商户号为10位数字编码，终端号为15位数字编码，默认以商户号开头
- 4.终端SM2私钥及公钥：可使用[测试工具](https://bkssl.com/ssl/sm2)自行生成，也可由平台生成，自行生成后需向平台提供`HEX`格式的公钥信息
 
#### 第二步：组装请求参数 
- **time**：当前时间的UNIX时间戳，精确到秒。
- **token**：16位随机字符，用于对data进行`SM4/ECB/Padding7`加密，由终端随机生成。
- **terminal**：本次请求使用的终端号，提前从平台获取。
- **sm4token**：对随机`token`使用终端号对应的平台公钥加密后进行`HEX`编码。
- **sm4data**：将请求参数通过JSON序列化后，使用前面随机`token`进行 `SM4/ECB/Padding7`加密后`HEX`编码。
- **signstr**：将time、sm4data、terminal三个字符串依次拼接。
- **sign**：使用终端号对应的SM2私钥计算`signstr`签名后`HEX`编码，服务端使用终端提供的SM2公钥验签。

`提示：`SM4加密解密可使用 https://lzltool.cn/SM4 工具进行测试，SM2加签验签可使用 https://bkssl.com/ssl/sm2 工具处理。
#### 第三步：接口调用
- **接口地址：** 服务器地址+接口地址
- **请求方式：** POST
- **请求参数：**
    | 参数名称 | 参数位置 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | -------- | ---- |
    | terminal |   body   |  string  |    R     | 客户端终端号 |
    | sm4token |   body   |  string  |    R     | 本次请求使用的SM4密钥（需由平台公钥加密后传输） |
    | sm4data  |   body   |  string  |    R     | 接口调用的业务数据（用sm4token中的密钥`SM4/ECB/Padding7`加密后`HEX`编码所得） |
    | time     |   body   |  string  |    R     | 发起请求的时间戳 |
    | sign     |   body   |  string  |    R     | 当前请求签名，使用终端私钥通过`SM2`算法签名 |
    
- **输出参数：**
    | 参数名称 | 参数位置 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | -------- | ---- |
    | message  |   body   | string   |    R     | 消息：错误消息或成功提示 |
    | code     |   body   | string   |    R     | 状态码，可参考[关于状态码](?id=status_code) |
    | data     |   body   | string   |    R     | 输出数据结果（用请求参数sm4token中的随机密钥`SM4/ECB/Padding7`加密后`HEX`编码所得） |



### 接口列表
* [支付下单](v2/trade_create.md)
* [支付状态查询](v2/trade_query.md)
* [发起退款](v2/trade_refund.md)
* [退款状态查询](v2/trade_refund_query.md)
* [关单](v2/trade_close.md)
* [结算记录查询](v2/trade_list.md)
* [异步通知接口](v2/notice.md)
	* [收款成功通知](v2/notice_pay.md)
	* [退款完成通知](v2/notice_refund.md)