# 扫码付

- **接口说明：** 终端直接扫描支付宝/微信等APP的付款码进行支付
- **接口地址：** /v2/trade/scanpay
- **请求方式：** POST
- **请求参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | ---- |
    | amount | int | R | 交易金额，单位：`分` |
    | description | string | R | 交易描述，如：住宿费 |
    | out_trade_no | string | R | 商户交易流水号，应在商户侧为唯一值 |
    | auth_code | string | R | 付款用户出示的付款吗 |
    | scenetag | string | O | 活动参与参数 |
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
    | - payInfo  | object | O | 输出数据：支付订单信息 |
    | &ensp;- trade_no | string | R | 平台交易流水号，用于后续查询支付状态、退款等 |
    | &ensp;- merchant | string | R | 交易所属商户号 |

- **状态码：**
    | 编码 | 说明 |
    | ---- | ---- |
    | 5011 | 参数“auth_code”缺失，请重新扫码 |
    | 5030 | 支付通道配置无效 |
    | 5200 | 终端暂未开通微信/支付宝交易功能 |
    | 9001 | 渠道业务参数错误 |