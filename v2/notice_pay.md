# 收款成功通知

- **接口说明：** 交易收款成功时向终端发送通知
- **接口地址：** 通过商户平台配置或下单时使用`notice_url`参数配置通知地址
- **请求方式：** POST
- **请求参数：**
    | 参数名称 | 参数类型 | 出现要求 | 描述 |
    | -------- | -------- | -------- | ---- |
    | trade_no   | string | R | 平台交易流水号 |
    | out_trade_no | string | R | 商家订单号 |
    | amount | int | R | 交易金额，单位：`分` |
    | description | string | R | 交易描述，如：住宿费 |
    | platform | string | C | 交易平台，可参考[平台标志](enums?id=platform) |
    | terminal | string | R | 终端号，发起当前交易的终端标识 |
    | merchant | string | R | 商户号，当前交易归属的商户号 |
    | fee_amount | int | R | 交易手续费，单位：`分` |
    | pay_amount | int | R | 交易收款金额，单位：`分` |
    | payment_id | string | O | 本次交易在微信、支付宝等交易平台的流水号 |
    | payment_name | string | O | 交易付款方式 |
    | time_payend | long | R | 付款时间，Unix时间戳（精确到秒） |
    | acct_date | string | R | 交易入账时间，格式：`yyyyMMdd` |
    | attach_data | string | O | 终端附属参数，由终端在交易发起时提交 |

- **通知示例：**
```
{
	"trade_no": "2024092917382200000184200182",
	"out_trade_no": "202409291738222406110001382200",
	"amount": 100,
	"description": "扫码付",
	"platform": "weixin",
	"terminal": "172510577500001",
	"merchant": "1725105775",
	"fee_amount": 0,
	"pay_amount": 100,
	"payment_id": "4200002363202409292822240776",
	"payment_name": "其它渠道",
	"time_payend": 1727583884,
	"acct_date": "20240929"
}
```
此示例由`encdata`参数解密所得，通知原文如下：
```
{
	"terminal": "172510577500001",
	"sm4token": "04e7c0f56951d862429c30e252cdc94a5d94909fced22c2ebd9ce0f49023b79e91edab1bfa7ee5696fd11a54a3f62e5b7f33e425f488f2b01a4af459907966b85230cfaa20082bbc7ff9d2350d8426c449ce0d405395894d31282494becf10c5816b3ef689b66150e9fa6028fe0616aa69",
	"encdata": "f24acbd83284419bb29f60a809108820600d5fcb0201ae1e5067f64fd8cf393e31987e9ab09b941b6ce2ad47691a766bd94a5dfc73c848d4d4e71ce5ae5e8b234490a41272d66e080c739ffdba3ad72ffe2fb606a51b8eb5f617a9b58e5f47db4f7e7a87a552572fe81df24f143699559207b3db576eba1e570280896d8b7e837d7d173b7ed79c9b0972aed40891a055dee0756815ea693782fd37a5e38551202904038bdbe88f2cd69021082713df7a46c0459d30d3afd719429a7b3b91018a81dbdf150098bc138700e2b0ac4748b855324f589d8d19f11eada1150f5ba6f3fb1a4db0690f1bcfb9e288edb12321ac2b32f4ce06b9689cae8d02831e0458b13c4a697956fd008aef7f5bea13b6217299e851de547f20ed9322b4a40f6d71d9ad74b81504f4f17b83a26fb390936c08beffc981b5bb416b97e2c88e6e6b052d9303685363ea8c505a3f5c0f5bbe5aa294db1ca2dfa0e5429e184c57ea2330832d23c7ba5ab56217b993869ef4296ed42d192a739f74eb417d202e230d131a3dab75ac389350930f50e4ce14f9c670a4590f2a01560d9508367567915c53804b4770a8b96f48572904f829868361d0a801d461cc536235cf2402bc6f00dedfb7db2bdd01866d27c6c9a614b27ea4afcbdbc914df8ae1cff10055c54f4664c1d7eaeb6872ab1b9071f4216bf054b7fdd1b61b2b091f3a06bc990281b6e4cea9b304b989fe39a6e4baf8e565e0f8d48d2984cbc12f05e4faec234e32905036f7b3",
	"time": "1727583884",
	"sign": "3046022100b6b55e786c9841da43cd080513f1424b6fb99fb14fc4a476bd753c3c78ddc1830221009959cf184e289e252143faa79464663cd67d7f4fd50d123c6233fe1161139c37"
}
```
