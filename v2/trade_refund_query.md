# 退款结果查询

- **接口说明：** 用于查询退款交易的处理状态及退款结果
- **接口地址：** /v2/trade/refundquery
- **请求方式：** POST
- **请求参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | ---- |
    | refund_no | string | C | 发起退款时返回的平台退款流水号（与商户退款流水号二选一，同时存在时则使用平台退款流水号） |
    | out_refund_no | string | C | 发起退款时提交的商户退款流水号（与平台退款流水号二选一，同时存在时则使用平台退款流水号） |

- **输出参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | ---- |
    | code | string | R | 执行状态：200-仅代表接口调用成功，不代表业务受理成功 |
    | message | string | R | 消息：错误消息或成功提示 |
    | data | encdata | R | 输出数据：SM4加密后的退款订单信息 |
    | - refund_no | string | R | 平台退款流水号，用于后续查询退款状态 |
    | - out_refund_no | string | R | 商户退款流水号 |
    | - merchant | string | R | 交易所属商户号 |
    | - amount | int | R | 退款金额，单位：`分` |
    | - description | string | R | 退款内容，如：客服退款 |
    | - time_create | long | R | 退款申请时间，Unix时间戳（精确到秒） |
    | - status | string | R | [退款状态](enums?id=paystate) |
    | - pay_amount | int | O | 实际退款金额，单位：`分` |
    | - fee_amount | int | O | 退返手续费金额，单位：`分` |
    | - fee_flag | int | O | 手续费扣款标志 0:默认，1: 外扣，2: 内扣|
    | - time_payend | long | O | 退款时间，Unix时间戳（精确到秒） |
    | - payment_id | string | O | 本次交易在微信、支付宝等交易平台的流水号 |
    | - payment_name | string | O | 退款返回支付方式 |
    | - acct_date | string | R | 退款入账时间，格式：`yyyyMMdd` |
    | - attach_data | string | O | 终端附属参数，由终端在退款发起时提交 |