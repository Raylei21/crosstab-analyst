# crosstab-analyst · 消费者研究交叉表分析师

一个可长期复用的消费者研究 / 市场调研**交叉表分析 Skill**（Claude Code Skill）。上传任意行业、任意问卷结构的交叉表数据，即可自动识别数据结构，找出不同细分用户群体之间的行为与需求差异，提炼消费者洞察，并转化为业务建议。

## 它做什么

- **理解交叉表结构**：自动识别题目、选项、细分维度、样本量、频数与百分比，判断百分比分母与群体关系。
- **先扫描、再分析**：先建立整表数据地图并排序优先级，而不是逐题机械罗列。
- **细分差异分析**：Segment vs Overall、群体内部横向比较、识别真正有区分度的差异化需求。
- **用户画像与跨题目整合**：把同一群体在多道题中的表现串联起来，并主动寻找反例与矛盾。
- **主动质疑、避免确认偏误**：对关键结论强制做反面证据检查。
- **严格标注样本量风险**：Base N < 30 小样本、低频数、无统计检验时的表述边界。
- **洞察分层**：区分 Data Finding / Consumer Insight / Business Implication，不强行给建议。

## 使用方式

把交叉表数据（Excel / CSV / 表格 / 截图）发给 Claude，并说一句类似：

- 「分析这份交叉表」
- 「帮我比较不同用户群体的差异」
- 「提炼这份调研数据的消费者洞察」
- 「高价值用户画像是什么」

未指定模式时默认走 **Quick Analysis（快速分析）**；指定某个群体深入分析时自动切换 **Deep Research Analysis（深度研究）**。

## 安装到 Claude Code

### 方式一：作为个人 Skill

```bash
mkdir -p ~/.claude/skills
git clone https://github.com/Raylei21/crosstab-analyst.git ~/.claude/skills/crosstab-analyst
```

### 方式二：作为项目 Skill

```bash
git clone https://github.com/Raylei21/crosstab-analyst.git .claude/skills/crosstab-analyst
```

安装后在会话中输入 `/crosstab-analyst` 即可调用。

## 目录结构

```
crosstab-analyst/
├── SKILL.md      # Skill 定义（frontmatter + 完整分析方法论）
└── README.md
```

## 设计原则

- **Data First / Evidence-based**：所有结论以实际数据为基础，关键洞察必须附具体数据。
- **通用性**：不绑定任何品牌、行业或固定细分维度。
- **No Fabrication / No Causal Overclaim**：不虚构数据，不把相关当因果。
- **Transparency**：数据不完整或分母无法确定时明确说明，不猜测。
