# insigoo-sia · 公益项目社会影响力 L1 逻辑自洽评估

> 公益项目的「逻辑体检医生」——把一份项目方案喂进去，逐环节检查因果链是否自洽，输出带优先级的「诊断报告 + 处方建议」。

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

---

## 这是什么

`insigoo-sia` 是一套可加载到 AI 客户端（Coze / WorkBuddy / Claude 等支持 Skill 加载的平台）的评估技能，专注 **L1 逻辑自洽层**。

社会影响力评估采用三层体系：

| 层级 | 名称 | 说明 | 本仓库 |
|------|------|------|--------|
| **L1** | 逻辑自洽评估 | 必选层。检查「投入→活动→产出→成果→影响」因果链是否自洽、假设是否可靠、是否真正从受益方视角出发 | ✅ 已开源 |
| L2 | 指标量化层 | 推荐层。把成果转化为可度量的指标与数据采集体系 | 更高层级 |
| L3 | 价值评估层 | 可选层。货币化 / 叙事轨道的价值核算 | 更高层级 |

> L1 报告可作为 L2 / L3 评估的输入基础；L2、L3 属更高层级评估，不在本技能范围内。

---

## 核心能力

- **逻辑链体检**：精准定位「断链 / 跳跃 / 伪因果」三类问题，指出具体发生在哪两个环节之间。
- **假设风险筛查**：内置 10 条中国公益项目高频隐式假设踩坑模式库（`references/assumption-patterns.md`），逐项比对。
- **合一性校验**：源自友成「三 A 三力」理论（驱动力 Aim / 行动力 Action / 改变力 Action-effect）。
- **带优先级的改进处方**：P0 必须修复 / P1 应该修复 / P2 建议优化。

## 三种评估模式

| 模式 | 适用场景 | 输出 |
|------|---------|------|
| 快速自检 | 申报前 / 筹款前快速排查 | 10 项快检清单 + 三大最高风险 |
| 完整体检（默认） | 设计纠偏、中期复盘、立项论证 | 完整「体检速览 → ToC → 四维明细 → 问题清单 → 处方 → 复诊建议」报告 |
| 批量评审 | 基金会 / 平台方筛选多份项目申请 | 6 维 100 分制评分卡 + 横向对比表 + 三档筛选 |

## 精美报告输出

完整体检 / 批量评审可一键生成 Insigoo 品牌色（深蓝 `#1B2A4A` + 琥珀金 `#D4A843`）的 HTML / PDF 报告：

```bash
pip install playwright && python -m playwright install chromium
python insigoo-sia/scripts/sia-to-pdf.py "报告.html"
```

模板与转换脚本见 `insigoo-sia/templates/` 与 `insigoo-sia/scripts/`。

---

## 文件结构

```
insigoo-sia/
├── SKILL.md                      # 核心评估流程与模式（加载入口）
├── references/
│   ├── assumption-patterns.md    # 10 条隐式假设模式库
│   ├── doc-extraction.md         # 老格式 .doc 文档提取
│   └── pdf-output.md             # PDF 报告输出指引
├── scripts/
│   └── sia-to-pdf.py             # Playwright HTML → PDF 转换
└── templates/
    └── sia-report.html           # 品牌化 HTML 报告模板
```

完整版本变更见 [`insigoo-sia-v1.2.0-更新说明.md`](insigoo-sia-v1.2.0-更新说明.md)。

---

## 安装与使用

1. 将 `insigoo-sia/` 整个目录放入你的 AI 客户端的 Skill 目录（或对应加载路径）。
2. 在对话中上传 / 描述一个公益项目方案，触发词包括：社会影响力评估、项目逻辑评估、SROI 评估、项目书自检、申报前检查、项目诊断、基金会评审、批量评审、逻辑体检等。
3. 按需要选择快速自检 / 完整体检 / 批量评审模式。

> 评估结果为 AI 辅助诊断意见，重大资助决策需结合人工尽调与专家判断。

---

## 许可证

[MIT](LICENSE) · © 2026 因思阁 (insigoo)

仓库：https://github.com/ericyueric/insigoo-sia · 联系：insigoo@insigoo.cn
