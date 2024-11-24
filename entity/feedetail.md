# 费用明细信息实体

| 字段名称 | 字段类型 | 不能为空 | 默认值 | 描述 |
| -------- | -------- | -------- | ------ | ---- |
| feedetail_sn | string | Y | 无 | 业务办理号、费用明细流水号，单次就诊唯一 |
| mdtrt_id | string | Y | 无 | 就诊ID |
| psn_no | string | N | 无 | 人员编号 |
| patient_id | string | Y | 无 | 所属就诊档案（卡）Id |
| patient_no | string | Y | 无 | 所属档案医保系统人员编号 |
| patient_name | string | Y | 无 | 所属就诊档案（卡）姓名 |
| disease_code | string | N | 无 | 疾病诊断编码（非挂号时不能为空，按照标准编码填写：按病种结算病种目录代码(bydise_setl_list_code)、门诊慢特病病种目录代码(opsp_dise_cod)） |
| charge_batch_no | string | Y | 无 | 平台交易流水号、收费批次号（同一收费批次号病种编号必须一致） |
| recipe_id | string | Y | 无 | 处方号 |
| recipe_cric_flag | string | Y | 无 | 外购处方标志，[0：否，1：是](enums?id=yesno) |
| fee_ocur_time | string | Y | 无 | 费用发生时间，格式：`yyyy-MM-dd HH:mm:ss` |
| med_list_code | string | Y | 无 | 医疗目录编码 |
| med_list_name | string | Y | 无 | 医疗目录名称 |
| med_list_specs | string | Y | 无 | 医疗目录规格 |
| medins_list_codg | string | Y | 无 | 医药机构目录编码 |
| detail_fee_should | decimal | Y | 无 | 明细项目费用总额(should_money应付金额) |
| detail_fee_sumamt | decimal | Y | 无 | 明细项目费用总额(actual_money实付金额) |
| count | decimal | Y | 无 | 数量 |
| price | decimal | Y| 无 | 单价 |
| specs | string | Y | 无 | 规格 |
| unit | decimal | Y | 无 | 计量单位 |
| single_dosage_dscr | string | N | 无 | 单次剂量描述 |
| used_frequency_dscr | string | N | 无 | 使用频次描述 |
| period_days | decimal | N | 无 | 周期天数 |
| medc_way_dscr | string | N | 无 | 用药途径描述 |
| billing_dept_code | string | Y | 无 | 开单科室编码 |
| billing_dept_name | string | Y | 无 | 开单科室名称 |
| billing_doctor_code | string | Y | 无 | 开单医生编码 |
| billing_doctor_name | string | Y | 无 | 开单医生姓名 |
| acrod_dept_code | string | N | 无 | 受单科室编码 |
| acrod_dept_name | string | N | 无 | 受单科室名称 |
| acrod_doctor_code | string | N | 无 | 受单医生编码 |
| acrod_doctor_name | string | N | 无 | 受单医生姓名 |
| hosp_appr_flag | int | N | 无 | 医院审批标志，1：已审批，2：转自费 |
| tcmdrug_used_way | string | N | 无 | 中药使用方式 |
| etip_flag | string | N | 无 | 外检标志，[0：否，1：是](enums?id=yesno) |
| etip_hosp_code | string | N | 无 | 外检医院编码 |
| dscg_tkdrug_flag | string | N | 无 | 出院带药标志，[0：无，1：有](enums?id=yesno)  |
| matn_fee_flag | string | N | 无 | 生育费用标志，[0：否，1：是](enums?id=yesno) |
| init_feedetail_sn | string | N | 无 | 原费用流水号，退单时传入被退单的费用明细流水号 |
| drord_no | string | N | 无 | 医嘱号 |
| med_type | string | Y | 无 | [医疗类别](enums?id=med_type) |
| memo | string | N | 无 | 备注 |
