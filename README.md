# water-engineering — 水利工程领域 Claude Code Skill

[![Skill](https://img.shields.io/badge/Claude_Code-Skill-8A2BE2)](https://code.claude.com)
[![Size](https://img.shields.io/badge/Size-1667_lines_/_65KB-skill.md)](skill.md)

一套完整的**水利水电工程领域 AI 辅助设计技能**，为中国水利工程师打造，覆盖水文计算、水工设计、中国标准规范、施工组织、工程经济等全专业领域。

---

## 核心能力

| 模块 | 内容 |
|------|------|
| **标准规范** | 国标 12 部 + 水利行标 50+ 部（含 2024-2026 最新发布） |
| **水文计算** | P-III 频率曲线、设计洪水、暴雨推求、马斯京根法、水库兴利调节、PMF |
| **水力学** | 明渠流、水面线计算、水跃、堰流（WES/宽顶堰）、消能、渗流 |
| **水工建筑物** | 重力坝、土石坝、水闸、溢洪道、水工隧洞 |
| **水工结构** | 水工钢筋混凝土（SL 191/DL/T 5057）、水工钢结构、挡土墙 |
| **水电站** | 引水系统、水锤调保、水轮机选型、厂房布置 |
| **灌溉排水** | 灌溉原理、灌水方法、渠道设计、排水系统 |
| **河流动力学** | 泥沙运动、河床演变、河道整治 |
| **报告模板** | 可研/初设/防洪评价/水文专题/水资源论证/大坝安全评价/山洪沟治理标准目录 |
| **批复文书** | 水利部 22 种水行政许可文书模板 |

## 目录结构

```
water-engineering/
├── skill.md                    ← 核心知识（自动加载到上下文）
└── references/                 ← 按需加载的参考文件
    ├── software.md             ← 远盛/理正/AutoBank 操作
    ├── projects.md             ← 实战项目经验
    ├── groundwater.md          ← pastas 地下水分析
    ├── landlab.md              ← 地表过程建模
    └── external-tools.md       ← SkillsBot 引擎参考
```

> skill.md 加载约 65KB 核心知识，reference 文件仅在需要时自动读取。

## 安装

```bash
# 安装到 Claude Code skills 目录
# 将 water-engineering 目录复制到:
#   ~/.claude/skills/water-engineering/
# 然后在 Claude Code 中使用 /water-engineering 调用
```

## 数据来源

本技能的知识体系基于：
- 中国国家标准（GB/GB/T）和水利行业标准（SL/SL/T）
- 经典水利教材（吴持恭《水力学》、詹道江《工程水文学》等）
- 水利部规范文件及报告编制规程
