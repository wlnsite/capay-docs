# 发起退款

- **接口说明：** 为交易发起退款
- **接口地址：** /v2/trade/refund
- **请求方式：** POST
- **请求参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | ---- |
    | amount | int | R | 退款金额，单位：`分` |
    | description | string | R | 退款内容，如：客服退款 |
    | out_refund_no | string | R | 商户退款流水号，应在商户侧为唯一值 |
    | origin_trade_no | string | C | 原平台收款流水号（与原商户收款流水号二选一，同时存在时则使用原平台收款流水号） |
    | origin_out_trade_no | string | C | 原商户收款流水号（与原平台收款流水号二选一，同时存在时则使用原平台收款流水号） |
    | notify_url | string | O | 付款成功的通知地址 |
    | attach_data | string | O | 终端附属参数，将在异步通知中原样返回，最大长度为1024 |

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