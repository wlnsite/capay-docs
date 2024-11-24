# 医保结算信息

| 字段名称 | 字段类型 | 不能为空 | 默认值 | 描述 |
| -------- | -------- | -------- | ------ | ---- |
| psn_no | string | Y | 无 | 人员编号 |
| mdtrt_id | string | Y | 无 | 就诊ID  |
| setl_id | string | Y | 无 | 结算ID  |
| setl_time | string | Y | 无 | 结算时间（格式：`yyyy-MM-dd HH:mm:ss`） |
| med_type | string | Y | 无 | 医疗类别 |
| medfee_sumamt | decimal | Y | 0.00 | 医疗费总额 |
| fulamt_ownpay_amt | decimal | N | 0.00 | 全自费金额 |
| overlmt_selfpay | decimal | N | 0.00 | 超限价自费费用 |
| preselfpay_amt | decimal | N | 0.00 | 先行自付金额 |
| inscp_scp_amt | decimal | N | 0.00 | 符合政策范围金额 |
| act_pay_dedc | decimal | N | 0.00 | 实际支付起付线 |
| hifp_pay | decimal | N | 0.00 | 基本医疗保险统筹基金支出 |
| pool_prop_selfpay | decimal | N | 0.00 | 基本医疗保险统筹基金支付比例 |
| cvlserv_pay | decimal | N | 0.00 | 公务员医疗补助资金支出 |
| hifes_pay | decimal | N | 0.00 | 企业补充医疗保险基金支出 |
| hifmi_pay | decimal | N | 0.00 | 居民大病保险资金支出 |
| hifob_pay | decimal | N | 0.00 | 企业补充医疗保险基金支出 |
| maf_pay | decimal | N | 0.00 | 医疗救助基金支出 |
| oth_pay | decimal | N | 0.00 | 其他支出 |
| fund_pay_sumamt | decimal | N | 0.00 | 基金支付总额  |
| psn_part_amt | decimal | N | 0.00 | 个人负担总金额 |
| acct_pay | decimal | N | 0.00 | 个人账户支出 |
| acct_mulaid_pay | decimal | N | 0.00 | 个人账户共济支付金额(已包含在个人账户支出中) |
| psn_cash_pay | decimal | N | 0.00 | 个人现金支出 |
| hosp_part_amt | decimal | N | 0.00 | 医院负担金额 |
| balc | decimal | N | 0.00 | 个人账户余额 |
| medins_setl_id | string | N | 无 | 医药机构结算ID |
| clr_optins | string | N | 无 | 清算经办机构  |
| clr_way | string | N | 无 | 清算方式 |
| clr_type | string | N | 无 | 清算类别 |