# 外部引擎与工具（补充参考，非规范依据）

> ⚠️ 以下来自 SkillsBot/GeoscienceSkills 等外部来源，作为**自动化计算工具**使用。
> **工程设计以中国规范为准，外部引擎仅用于快速试算和多方案比选。**

## 水文建模引擎（Hydrologic Modeling Engine）

**来源**：SkillsBot CIV-SK-022 | Slug: `hydrologic-modeling-engine`

**定位**：专业工程分析工具，专注于降雨径流模拟、洪水频率分析和洪水演进计算。

**核心方法**：
| 方法 | 适用 |
|------|------|
| SCS/NRCS 曲线数法（Curve Number） | 无资料地区产流计算 |
| 单位线法（Unit Hydrograph） | 由净雨推求洪水过程线 |
| 马斯京根法（Muskingum Routing） | 河道洪水演进 |
| 强度-历时-频率分析（IDF Curves） | 设计暴雨 |
| 洪水频率分析（Flood Frequency） | P-III型分布/设计洪水 |
| 水文过程线生成（Hydrograph Generation） | 合成洪水过程线 |

## 水力分析引擎（Hydraulic Analysis Engine）

**来源**：SkillsBot CIV-SK-023 | Slug: `hydraulic-analysis-engine`

**核心功能**：
| 功能 | 内容 |
|------|------|
| 水面线计算 | 标准步推法/逐段试算法（缓流/急流控制） |
| 正常水深计算 | 曼宁公式迭代（矩形/梯形/圆形/复合断面） |
| 临界水深计算 | 断面比能最小原理 |
| 渠道设计 | 水力最佳断面 + 不冲不淤条件 |
| 水跃计算 | 共轭水深/水跃长度/消能率 |
| 堰流/孔流 | WES实用堰/宽顶堰/闸孔出流 |
| 稳态与非稳态建模 | 恒定渐变流/非恒定流 |

## 供水管网建模师（Water Distribution Modeler）

**来源**：SkillsBot CIV-SK-025 | Slug: `water-distribution-modeler`

**核心功能**：
| 功能 | 内容 |
|------|------|
| 需水量计算 | 生活/工业/消防/漏损水量分配 |
| Hardy-Cross 法 | 管网平差（Newton-Raphson迭代） |
| 水泵选型分析 | 扬程-流量曲线/比转速/气蚀余量 |
| 供水压力区设计 | 分区供水/减压阀/高位水池 |
| 扩展期模拟 | 近期/远期分期建设模拟 |
| 系统优化 | 管径优化/泵站调度/能耗分析 |

## 三引擎与本地 skill 的关系

| 引擎 | SkillsBot 定位 | 本地 skill 已有对应 |
|------|------|------|
| 水文建模引擎 | 降雨径流/洪水频率/洪水演进 | 水文分析与计算（P-III/设计洪水/单位线/马斯京根） |
| 水力分析引擎 | 曼宁公式/水面线/堰流/水跃 | 水力学（明渠/堰流/水跃/消能） |
| 供水管网建模师 | 供水管网平差/水泵选型 | 灌溉排水工程学（渠道设计/管网） |

## 已整合的外部 Skills

| Skill | 来源 | 核心能力 |
|------|------|------|
| pastas | SteadfastAsArt/geoscience-skills | 地下水时间序列/传递函数噪声模型/含水层参数率定 |
| xarray | SteadfastAsArt/geoscience-skills | NetCDF 多维水文数据/时间聚合/面积加权/Dask 惰性加载 |
| landlab | SteadfastAsArt/geoscience-skills | 地表过程建模/水流路由/河流侵蚀/坡面扩散 |

## 外部教程参考

| 资源 | 地址 | 内容 |
|------|------|------|
| claude-code-for-hydrology | `github.com/lorenliu13/claude-code-for-hydrology` | 9个水文实践练习：SPI干旱指数/NSE-KGE验证/USGS MCP数据读取/并行SPI计算 |
