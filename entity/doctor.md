# 医生信息实体

| 字段名称 | 字段类型 | 不能为空 | 默认值 | 描述 |
| -------- | -------- | -------- | ------ | ---- |
| id | string | Y | 无 | 唯一标识 |
| name | string | Y | 无 | 医生姓名 |
| state | int | Y | 无 | [记录状态](enums?id=state) |
| sex | int | Y | 0 | [性别](enums?id=sex)：0-未知,1-男,2-女 |
| dept_id | string | Y | 无 | 所属科室Id |
| dept_name | string | Y | 无 | 所属科室名称 |
| doctor_code | string | N | 无 | 医师注册编码 |
| doctor_name | string | N | 无 | 医师注册姓名 |
| staff_type | string | N | 无 | 人员类型编号 |
| staff_name | string | N | 无 | 人员类型名称 |
| mobile | string | N | 无 | 手机号码 |
| position | string | O | 无 | 医生职务 |
| avatar | string | O | 无 | 头像照片 |
| intro | string | O | 无 | 简单介绍 |
