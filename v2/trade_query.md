# 支付状态查询

- **接口说明：** 查询交易的支付状态
- **接口地址：** /v2/trade/query
- **请求方式：** POST
- **请求参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | ---- |
    | trade_no | string | C | 下单时返回的平台交易流水号（与商户交易流水号二选一，同时存在时则使用平台交易流水号） |
    | out_trade_no | string | C | 下单时提供的商户交易流水号（与平台交易流水号二选一，同时存在时则使用平台交易流水号） |

- **输出参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | ---- |
    | code | string | R | 执行状态：200-仅代表接口调用成功，不代表业务受理成功 |
    | message | string | R | 消息：错误消息或成功提示 |
    | data | encdata | R | 输出数据：SM4加密后的交易订单信息 |
    | - trade_no | string | R | 平台交易流水号 |
    | - out_trade_no | string | R | 商户交易流水号 |
    | - status | string | R | [交易状态](enums?id=paystate) |
    | - amount | int | R | 交易总金额，单位：`分` |
    | - description | string | R | 交易描述，如：住宿费 |
    | - platform | string | C | 交易平台，可参考[平台标志](enums?id=platform) |
    | - terminal | string | R | 终端号，发起当前交易的终端标识 |
    | - merchant | string | R | 商户号，当前交易归属的商户号 |
    | - fee_flag | int | R | 手续费扣款标志 0:默认，1: 外扣，2: 内扣|
    | - fee_amount | int | R | 交易手续费，单位：`分` |
    | - pay_amount | int | R | 交易收款金额，单位：`分` |
    | - payment_id | string | O | 本次交易在微信、支付宝等交易平台的流水号 |
    | - payment_name | string | O | 交易付款方式 |
    | - time_payend | long | R | 付款时间，Unix时间戳（精确到秒） |
    | - acct_date | string | R | 交易入账时间，格式：`yyyyMMdd` |
    | - attach_data | string | O | 终端附属参数，由终端在交易发起时提交 |