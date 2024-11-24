# 处方明细信息实体

| 字段名称 | 字段类型 | 不能为空 | 默认值 | 描述 |
| -------- | -------- | -------- | ------ | ---- |
| recipe_id | string | Y | 无 | 就诊档案（卡）唯一标识 |
| branch_id | string | N | 所属院区编号 |
| branch_name | string | N | 所属院区名称 |
| patient_id | string | Y | 所属就诊档案（卡）Id |
| patient_name | string | N | 所属就诊档案（卡）姓名 |
| apply_time | string | Y | 发起时间，Unix时间戳（精确到秒） |
| apply_dept_id | string | Y | 发起科室Id |
| apply_dept_name | string | N | 发起科室名称 |
| apply_doctor_id | string | Y | 发起医生Id |
| apply_doctor_name | string | N | 发起医生姓名 |
| exec_time | long | N | 执行时间，Unix时间戳（精确到秒） |
| exec_dept_id | string | N | 执行科室Id |
| exec_dept_name | string | N | 执行科室名称 |
| exec_doctor_id | string | N | 执行医生Id |
| exec_doctor_name | string | N | 执行医生姓名 |
| project_code | string | N | 所属项目编码（item_code） |
| project_name | string | N | 所属项目名称（item_name） |
| fee_category_code | string | N | [费用类别](enums?id=fee_category) |
| fee_category_name | string | N | 费用类别名称 |
| trade_no | string | N | 交易流水号，已缴费时有输出 |
| total_unit | string | Y | 整单计量单位，如：g |
| should_money | decimal | R | 小计应付金额 |
| actual_money | decimal | R | 小计实付金额 |
| detail_sequence | int | Y | 明细在处方内序号 |
| detail_group | int | Y | 明细组合序号 |
| detail_count | decimal | Y | 明细数量 |
| detail_price | decimal | Y | 单价 |
| detail_specs | string | Y | 规格，如：1 g×1000 g/kg |
| detail_unit | string | Y | 明细计量单位，如：g |
| frequency_code | string | N | [处方频次](enums?id=recipe_frequency) |
| frequency_name | string | N | 处方频次名称 |
| dosage_once_num | decimal | N | 每次用量 |
| dosage_unit_code | string | N | [每次用量单位](enums?id=recipe_dosage_unit) |
| dosage_unit_name | string | N | 每次用量单位名称 |
| dosage_form_code | string | N | [剂型](enums?id=recipe_dosage_form) |
| dosage_form_name | string | N | 剂型名称 |
| term_type_code | string | N | 术语类别（费目）编码 |
| term_type_name | string | N | 术语类别（费目）名称 |
| charge_flag | int | Y | 已缴费标志，0-未缴费，1已缴费 |
