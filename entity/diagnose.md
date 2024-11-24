# 诊断信息实体

| 字段名称 | 字段类型 | 不能为空 | 默认值 | 描述 |
| -------- | -------- | -------- | ------ | ---- |
| diagnose_type | string | Y | 无 | 诊断类别 |
| diagnose_sortno | string | Y | 无 | 诊断排序号 |
| diagnose_code | string | Y | 无 | 诊断代码 |
| diagnose_name | string | Y | 无 | 诊断名称 |
| diagnose_time | string | Y | 无 | 诊断时间，格式：`yyyy-MM-dd HH:mm:ss` |
| diagnose_dept_codg | string | Y | 无 | 诊断科室编码 |
| diagnose_dept_name | string | Y | 无 | 诊断科室名称 |
| diagnose_doctor_codg | string | Y | 无 | 诊断医生编码 |
| diagnose_doctor_name | string | Y | 无 | 诊断医生姓名 |
| valid_flag | int | Y | 无 | [有效性标识](enums?id=valid)，0：无效，1：有效 |
