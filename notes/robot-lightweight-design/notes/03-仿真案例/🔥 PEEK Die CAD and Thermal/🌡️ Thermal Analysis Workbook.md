---
tags:
  - peek-die
  - thermal-analysis
status: preparation
---
# 🌡️ Thermal Analysis Workbook
项目：[[robot-lightweight-design/notes/03-仿真案例/🔥 PEEK Die CAD and Thermal/🔥 PEEK Die CAD and Thermal|🔥 PEEK Die CAD and Thermal]] · 计划：[[robot-lightweight-design/notes/03-仿真案例/🔥 PEEK Die CAD and Thermal/📅 Two-Week Execution Plan|📅 Two-Week Execution Plan]]

## 🎯 Study Definition
- Study ID / CAD revision：
- Software / Version / Thermal capability：
- 工况：空载加热 / 加工工况（待选）
- 目标：比较浸渍区温度均匀性、上下模温差及法兰附近热损失。
- 固定观察区域、测点坐标与截面：
- 目标温度 / 允许温差及其工艺依据：待确认。
- 状态：未设置 / 已设置 / 未求解 / 已求解 / 待验证。

首次可用空载固体导热工况，但它不能直接代表运动物料的温度或流体压力。若忽略物料带走热量，必须写入适用范围。

## 📋 Input Register
数值不明时填写“待确认”，附图纸编号、手册页码、测量日期或文献链接。
| Input | Value / Unit | Source / Status | Applied To |
|---|---|---|---|
| 模具、法兰材料牌号 | 待确认 | 待确认 | 对应实体 |
| 导热系数 k(T) | W/(m·K) | 检查适用温度范围 | 对应实体 |
| 加热棒数量、单支实际/额定功率 | W | 区分额定值和控温平均输入 | 每支热源 |
| 环境温度 | °C | 实测/假设 | 外表面环境 |
| 对流系数 | W/(m²·K) | 依据及范围 | 暴露表面 |
| 发射率、辐射环境温度 | 无量纲、°C | 表面状态及依据 | 辐射表面 |
| 接触热阻或接触热导 | 依软件定义填写单位 | 总热阻与单位面积热阻不可混用 | 上下模、棒孔、法兰 |
| 保温层厚度、导热系数 | mm、W/(m·K) | 实物/手册 | 保温覆盖位置 |
| 连接设备的散热边界 | 温度/热阻等 | 实物连接条件 | 法兰/支撑 |
| 物料热负荷（若考虑） | 模型与单位待定 | 待确认 | 流道 |
| 密度、比热、初始温度（后续瞬态） | kg/m³、J/(kg·K)、°C | 待确认 | 对应实体 |

## 🔧 Setup Checklist
- [ ] 保留影响导热的流道、薄壁、热源孔、接触和散热结构；删除小倒角等须记录。
- [ ] 检查热源分配：总功率等于各支输入之和，注意所选多个实体是总量还是逐个施加。
- [ ] 功率驱动与指定温度代表不同问题；同一热源不重复强加两者。
- [ ] 为稳态输入热量提供合理散热通路；未定义表面的绝热假设已检查。
- [ ] 检查接触是否真实连通，理想接触仅作为明确假设。
- [ ] 评估高温辐射，不能无依据地省略；辐射公式中的温度使用绝对温度。
- [ ] 保存网格、边界、选区与求解器信息。
SOLIDWORKS 的热分析流程与可用载荷见 [Performing Thermal Analysis](https://help.solidworks.com/2024/english/solidworks/cworks/t_Performing_Thermal_Analysis.htm)；功能授权先核对本机，官方产品说明见 [SOLIDWORKS Simulation](https://www.solidworks.com/product/solidworks-simulation)。不同版本界面以本机为准。

## 📊 Results Register
空表保留为空，运行后填写。
| Case | CAD / Mesh | Changed Input | T max / min (°C), defined region | Region ΔT (K) | Probe Temperatures | Heat In / Out (W) | Status |
|---|---|---|---|---|---|---|---|
| Baseline | | 无 | | | | | 未求解 |
| Refined Mesh | | 仅网格 | | | | | 未求解 |
| Sensitivity Low | | 参数与依据 | | | | | 未求解 |
| Sensitivity High | | 参数与依据 | | | | | 未求解 |

记录浸渍区 max−min、对应位置的上下模温差，以及法兰/测温孔温度。各图保持相同色标、截面和单位。网格对比记录单元数及关键输出变化；温度比较优先报告绝对差（K），避免以摄氏温度作相对误差分母。验收阈值须结合工艺需求预先设定；两级网格不足以自动证明收敛。

## ✅ Interpretation and Handoff
- 能量收支是否合理；存在指定温度边界时包含其反力热流。
- 结果异常先检查单位、材料、接触及负载；收敛不等于模型真实。
- 有实测时对齐传感器位置、工况与时间状态；无实测时写“尚未实验验证”。
- 报告：问题 → 几何及简化 → 来源与假设 → 网格 → 结果 → 限制 → 下一步。
- 后续瞬态需补密度、比热、初始温度、功率/控制随时间变化及时间步检查；稳态结果不用于推断升温时间。

