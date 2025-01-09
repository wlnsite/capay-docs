# 支付下单

- **接口说明：** 为终端提供下单服务，基于终端提交的支付订单，生成并返回支付订单号，用于后序支付服务
- **接口地址：** /v2/trade/create
- **请求方式：** POST
- **请求参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | ---- |
    | amount | int | R | 交易金额，单位：`分` |
    | description | string | R | 交易描述，如：住宿费 |
    | out_trade_no | string | R | 商户交易流水号，应在商户侧为唯一值 |
    | time_expire | unix | O | 交易有效期，Unix时间戳（精确到秒）,最大值为当前时间24小时内 |
    | transaction_scene | string | R | [交易模式](enums?id=payscene) |
    | transaction_openid | string | C | 交易用户的OpenId |
    | cashier | int | C | 是否使用收银台模式进行结算 |
    | notify_url | string | O | 付款成功的通知地址 |
    | client_ip | string | O | 交易终端的用户IP地址 |
    | client_geohash | string | O | 交易终端用户地理位置坐标定位进行`Geohash`编码 |
    | attach_data | string | O | 终端附属参数，将在异步通知中原样返回，最大长度为1024 |

- **输出参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | ---- |
    | code | string | R | 执行状态：200-仅代表接口调用成功，不代表业务受理成功 |
    | message | string | R | 消息：错误消息或成功提示 |
    | data | encdata | R | 输出数据：SM4加密后的交易订单信息 |
    | - trade_no | string | R | 平台交易流水号，用于后续查询支付状态、退款等 |
    | - merchant | string | R | 交易所属商户号 |
    | - cashier | string | O | 使用收银台模式进行结算时返回收银台跳转连接 |
    | - payInfo  | object | O | 输出数据：支付订单信息 |
    | &ensp;- timeStamp | string | C |  |
    | &ensp;- nonceStr | string | C |  |
    | &ensp;- package | string | C |  |
    | &ensp;- signType | string | C |  |
    | &ensp;- paySign | string | C |  |
    | &ensp;- appId | string | C |  |