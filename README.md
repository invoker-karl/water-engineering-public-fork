# 水利工程技能（water-engineering）

[![Skill](https://img.shields.io/badge/Claude_Code-Skill-8A2BE2)](https://code.claude.com)
[![Release](https://img.shields.io/github/v/release/WhOleit-hub/water-engineering-skill)](https://github.com/WhOleit-hub/water-engineering-skill/releases)
[![License](https://img.shields.io/badge/License-MIT-green)](LICENSE)

面向中国水利工程工作的专业技能包。它把水文、水力、水工结构、涉河建设与洪水影响评价的工作要求组织成可追溯流程：先核实水流路径、资料来源与适用规范，再计算、复核并形成可审查结论。

> 本公开版不包含个人、项目或涉密资料；所有工程数值均应以经核实的设计资料、现行规范和正式计算成果为准。

## 能力范围

| 场景 | 提供的工作支持 |
| --- | --- |
| 水文分析 | 设计洪水、暴雨径流、P-III 频率分析、调洪演算的资料核查与复核流程 |
| 水力计算 | 明渠水面线、曼宁公式、堰流、水跃与消能的适用条件、计算与复核要求 |
| 水工建筑物 | 坝、闸、堤防、挡土墙、渗流与稳定验算的资料组织及审查要点 |
| 涉河与洪评 | 顶管、倒虹吸、围堰、施工导流、壅水、冲淤、河势与防洪工程安全评价 |
| 报告审查 | 可研、初设、施工图、专题与报批报告的资料闭合、计算衔接和问题清单 |
| 工程工具 | 按需引用 HEC-RAS、MIKE、地下水与地貌等工具资料，不以软件名称替代计算依据 |

## 使用原则

1. 先读水系图、总平面、纵断面或控制断面，确认“来水—控制工程—项目—下游出口”。
2. 每项输入应注明来源、桩号/断面、时间、频率、单位和高程基准；资料冲突时优先采用批准变更或最终施工图。
3. 永久工程与施工临时工程分开评价；设计与校核工况、不同频率洪水不得混用。
4. 计算结论至少通过量纲、守恒、反算、等价方法或实测/历史资料中的一种方式独立复核。
5. 不虚构糙率、粒径、级配、断面、模型边界或稳定系数；缺少正式资料时，明确为待核实项。

## 安装与调用

```bash
# 克隆到 Claude Code 的 skills 目录
git clone https://github.com/WhOleit-hub/water-engineering-skill.git ~/.claude/skills/water-engineering

# 在 Claude Code 中调用
/water-engineering
```

使用时可直接描述任务，例如：

```text
根据初设和施工图，复核某涉河顶管工程的洪水影响评价第五章。
请列出资料矛盾、计算假定、独立复核结果及需落实的措施。
```

复杂任务（如 P-III 适线、多断面水面线、多工况稳定、完整洪评或跨多项规范的报告）应先形成计算提纲和资料缺口表，再进入正式计算。

## 目录结构

```text
water-engineering/
├── skill.md                 # 技能入口：任务路由、工作流、数据纪律与交付模板
├── references/
│   ├── standards.md         # 标准状态、等级与防洪标准
│   ├── hydrology.md         # 设计洪水、P-III、暴雨径流与调洪
│   ├── hydraulics.md        # 水面线、曼宁、堰流、水跃与消能
│   ├── structures.md        # 坝闸堤防、挡土墙、渗流与稳定
│   ├── flood-evaluation.md  # 涉河工程与洪水影响评价
│   ├── reporting.md         # 报告编制与审查
│   └── ...                  # 软件、地下水、地貌等按需参考资料
├── evals/evals.json         # 典型任务的验收样例
├── scripts/validate.py      # 文档与链接校验脚本
├── CHANGELOG.md             # 版本变更记录
└── VERSION                  # 当前版本号
```

`skill.md` 只保留高频决策规则，具体方法按任务读取对应工作卡，避免一次加载与当前问题无关的资料。

## 版本与迭代

| 版本 | 日期 | 主要变化 |
| --- | --- | --- |
| [v1.0.1](https://github.com/WhOleit-hub/water-engineering-skill/releases/tag/v1.0.1) | 2026-07-22 | 重构为“技能入口 + 专题工作卡”，新增洪评、报告、水文、水力、结构等任务路由；补充评测样例与文档校验；更新失效外部链接。 |
| [v1.0.0](https://github.com/WhOleit-hub/water-engineering-skill/releases/tag/v1.0.0) | 2026-06-26 | 首次公开发布。 |

后续迭代遵循语义化版本：修订或链接修复使用补丁版本；新增向后兼容的工作卡或流程使用次版本；不兼容的入口或交付规则调整使用主版本。

## 贡献

欢迎提交可复现、可核查的改进。提交前请确保：

1. 不包含项目名称、人员信息、坐标、原始图纸、涉密数据或其他敏感资料；
2. 标准、公式和软件说明有明确出处，且不把经验值写成通用定值；
3. 运行仓库校验：`python scripts/validate.py`；
4. 通过 Pull Request 提交，说明适用场景、资料前提与验证方式。

## 许可

本项目采用 [MIT License](LICENSE)。
