# 就诊档案（卡）信息实体

| 字段名称 | 字段类型 | 不能为空 | 默认值 | 描述 |
| -------- | -------- | -------- | ------ | ---- |
| id | string | Y | 无 | 就诊档案（卡）唯一标识 |
| name | string | Y | 无 | 姓名，院内手动登记的婴儿可以为空 |
| idcard | string | N | 无 | 证件号码 |
| mobile | string | N | 无 | 手机号码 |
| sex | int | Y | 0 | [性别](enums?id=sex)：0-未知,1-男,2-女 |
| age | double | Y | 0 | 年龄 |
| mzh | string | N | 无 | 门诊号 |
| zyh | string | N | 无 | 住院号 |
| registration_time | long | Y | 0 | 登记时间，Unix时间戳（精确到秒） |
