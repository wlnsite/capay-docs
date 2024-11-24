# 挂号信息实体

| 字段名称 | 字段类型 | 不能为空 | 默认值 | 描述 |
| -------- | -------- | -------- | ------ | ---- |
| id | string | Y | 无 | 挂号单据号 |
| mzh | string | Y | 门诊号 |
| patient_id | string | Y | 所属就诊档案（卡）Id |
| patient_name | string | N | 所属就诊档案（卡）姓名 |
| patient_idcard | string | N | 所属就诊档案（卡）证件号 |
| patient_sex | string | N | 看诊患者性别 |
| patient_age | string | N | 看诊患者年龄 |
| schedule_no | string | N | 号源编号 |
| schedule_type | string | N | 号类编号 |
| schedule_date | string | N | 挂号就诊日期（格式：yyyy-MM-dd） |
| schedule_time | string | N | 挂号就诊时间（格式：HH:mm:ss） |
| reg_fee | int | Y | 看诊费用（单位：分） |
| reg_see_no | string | Y | 看诊序号 |
| reg_see_flag | bool | Y | 是否已看诊，true或false |
| reg_level_code | string | N | 挂号级别编码） |
| reg_level_name | string | N | 挂号级别名称 |
| reg_state_code | string | N | 挂号状态编码 |
| reg_state_name | string | N | 挂号状态名称 |
| reg_qrtext | string | N | 签到/看诊时需要出示的二维码（文本值） |
| dept_id | string | N | 挂号科室编号（唯一标识） |
| dept_name | string | N | 挂号科室名称（院内简称） |
| dept_address | string | N | 院内导航地址（楼栋楼层 ） |
| doctor_id | string | N | 出诊医生ID，0或空为轮值医生，其它值为医生ID |
| doctor_name | string | N | 出诊医生姓名 |
| trade_no | string | N | 交易单号，已缴费时有输出 |
| trade_time | unix | N | 交易时间，Unix时间戳（精确到秒） |
| trade_channel_code | string | N | 挂号渠道编码 |
| trade_channel_name | string | N | 挂号渠道名称 |
