---
tags:
  - robot-lightweight-design
  - peek-die
  - cad-cae
status: planned
---
# 🔥 PEEK Die CAD and Thermal
返回：[[README|Robot Lightweight Design]] · [[robot-lightweight-design/notes/03-仿真案例/🔥 PEEK Die CAD and Thermal/📅 Two-Week Execution Plan|📅 Two-Week Execution Plan]] · [[robot-lightweight-design/notes/03-仿真案例/🔥 PEEK Die CAD and Thermal/🌡️ Thermal Analysis Workbook|🌡️ Thermal Analysis Workbook]]

## 🎯 Project Goal
把已有 PEEK 浸渍模具二维图纸重建为 SolidWorks 参数化零件和装配体，并完成首轮稳态热分析准备；资料和软件条件满足时，完成基准求解、网格检查与一组敏感性对比。

当前起点：有部分 FreeCAD 经验，SolidWorks 接近初学。二维图纸存在，但本笔记编制时尚未核对图纸及设备参数。以下均为待执行任务，没有已完成 CAD 或仿真结果。

## 🔗 Connection to Robot Lightweight Design
承接已有 [[robot-lightweight-design/notes/02-轻量化材料/2026-08-17-项目启动-轻量化连杆设计|轻量化连杆项目]] 和 [[robot-lightweight-design/notes/报告/轻量化连杆材料对比分析|材料对比分析]]。

| 已有学习 | 本次实战 | 后续机器人应用 |
|---|---|---|
| FreeCAD 参数化连杆、实心/空心版本 | 草图约束、特征树、图纸尺寸追溯 | 关节壳体、连杆的可修改模型 |
| 材料与质量对比 | 分清模具金属材料和被加工的 PEEK，记录物性来源 | 材料选择与热管理权衡 |
| 载荷、约束与 FEM 结果 | 热源、接触、散热边界和网格敏感性 | 电机座与关节壳体的分析判断 |
| 设计版本与报告 | 基准模型、单因素方案、同尺度结果图 | 有证据的设计迭代与作品集 |

模具练习训练 CAD/CAE 方法；并不直接证明机器人结构减重或强度性能。本阶段不追求模具减重，也不把已有连杆静力结果当作模具的热学参数。PEEK 科研库保持独立，此处只记录机器人学习所需的实践过程。

## 📦 Deliverables
- [ ] 图纸清单、零件清单、缺失尺寸和假设记录。
- [ ] 原生 SLDPRT / SLDASM、关键剖视截图、核对表、STEP 交换文件。
- [ ] 热分析简化模型、材料与边界表、接触示意、测点定义。
- [ ] 条件满足：基准工况、网格对比、单因素敏感性结果和简短报告。
- [ ] 条件不足：可交接的分析设置包、缺项负责人/获取方式及下一步；状态明确写为“未求解”。
- [ ] 两次周里程碑记录。

模型和求解文件继续使用现有项目的 models / simulations 目录；本次只新增笔记。后续产出可分别放入其中的 `🔥 PEEK Die CAD and Thermal` 子目录，报告沿用现有“报告”目录，新增文件用英文与 emoji 命名。

## ✅ Completion Criteria
1. 关键尺寸可追溯，未知尺寸明确标记；装配没有未解释的干涉。
2. 工况表包含单位、来源、选中面/实体和假设；软件文件能重新打开。
3. 有结果时，报告保留工况、网格和数值表；没有结果时不填写虚构温度或完成状态。
4. 两周核心为 CAD 与初始稳态热分析。瞬态升温、热应力、给定压力结构分析、流体压力 CFD 列为后续任务，不作为两周验收要求。

