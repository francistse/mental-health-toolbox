# 心理健康工具箱 (Mental Health Toolbox)

简体中文 | [English](./README.md) | [繁體中文](./README_TC.md) | [日本語](./README_JA.md)

两个互补的 AI Agent 技能，提供全面的心理健康支持：**危机检测**用于安全监控，**夸夸群**用于正向强化。

🎨 本项目使用 TRAE IDE 开发——让 AI Agent 技能开发变得更简单、更愉快。

## 概览

| 技能                                 | 版本   | 功能                        |
| ---------------------------------- | ---- | ------------------------- |
| [危机检测](./skills/crisis-detection/) | v2.0 | 主动检测危机信号，5层风险评估，分级干预      |
| [夸夸群](./skills/praise-group/)      | v4.0 | CBT 感知正向强化，将任何输入转化为创意支持回应 |

两个技能均支持英语、繁体中文、简体中文、日语，自动检测语言。

## 快速开始

### 安装

1. 克隆仓库：

```bash
git clone https://github.com/francistse/mental-health-toolbox.git
cd mental-health-toolbox
```

1. 将技能复制到你的 Agent 技能目录：

```bash
# 危机检测
cp -r skills/crisis-detection /path/to/your/agent/skills/crisis-detection

# 夸夸群
cp -r skills/praise-group /path/to/your/agent/skills/praise-group
```

1. 重启你的 Agent 以加载技能

### 使用 Hermes Agent

```bash
# 安装技能
mkdir -p ~/.hermes/skills/crisis-detection
cp skills/crisis-detection/SKILL.md ~/.hermes/skills/crisis-detection/SKILL.md

mkdir -p ~/.hermes/skills/praise-group
cp skills/praise-group/SKILL.md ~/.hermes/skills/praise-group/SKILL.md

hermes gateway restart
```

### 使用方式

```bash
# 危机检测 - 主动评估
hermes chat --skills crisis-detection -q "/crisis 我最近感觉很沮丧"

# 夸夸群 - 正向强化
hermes chat --skills praise-group -q "考试又挂了，感觉自己好蠢"

# 两个技能一起使用
hermes chat --skills crisis-detection,praise-group
```

## 危机检测技能

### 工作模式

| 模式   | 触发方式                            | 行为             |
| ---- | ------------------------------- | -------------- |
| 主动评估 | `/crisis`、`/assess`、`/check` 命令 | 使用5层框架进行全面风险评估 |
| 被动监控 | 任何对话                            | 静默后台监控危机指标     |

### 5层检测架构

| 层级          | 检测方法       | 风险等级 | 响应        |
| ----------- | ---------- | ---- | --------- |
| 第1层 - 显式关键词 | 直接自残语言     | 危急/高 | 立即干预      |
| 第2层 - 语言模式  | 代词转换、绝对化词语 | 中/高  | 增强监控 + 支持 |
| 第3层 - 主题指标  | 学业压力、自我贬低  | 中/低  | 针对性支持     |
| 第4层 - 行为模式  | 睡眠紊乱、社交退缩  | 可变   | 纵向跟踪      |
| 第5层 - 时间/情感 | 随时间的下降趋势   | 可变   | 模式识别      |

### 风险等级

| 得分  | 等级    | 响应          |
| --- | ----- | ----------- |
| 0   | 🟢 正常 | 标准交互        |
| 1   | 🟡 低  | 支持性关注       |
| 2-3 | 🟠 中等 | 增强关注 + 应对策略 |
| 4-5 | 🔴 高  | 危机支持 + 资源推荐 |
| 6+  | ⚫ 危急  | 立即干预 + 安全检查 |

### 关键危机指标（英文）

| 类别    | 示例                                            |
| ----- | --------------------------------------------- |
| 自我伤害  | "don't want to live", "suicide", "end it all" |
| 绝望    | "no point", "hopeless", "can't go on"         |
| 自我贬低  | "I'm useless", "worthless", "failure"         |
| 学业/工作 | "failed", "can't keep up", "fired"            |
| 社交    | "nobody cares", "alone", "isolated"           |
| 负担感   | "burden to everyone", "better off without me" |

完整的多语言指标请查看[危机检测 SKILL.md](./skills/crisis-detection/SKILL.md)。

## 夸夸群技能

### 工作原理

技能自动检测用户情绪状态，使用 CBT 感知重构将输入转化为热情、创意和支持性的回应。

### 转换示例

| 用户输入         | 回应风格            |
| ------------ | --------------- |
| "我考试没考好"     | 成长机会 + 坚持赞美     |
| "没人理解我"      | 深层感受作为超能力       |
| "我刚冲了杯咖啡"    | 正念 + 发现日常之美     |
| "我觉得自己是个失败者" | 区分错误与身份 + 尝试的勇气 |
| "工作压力好大"     | 韧性认可 + 未来鼓励     |

### 回应规则

- **2-4 句话** — 简短、热情、诗意
- **无后续问题** — 只赞美，然后继续
- **无分析语调** — 温暖真诚，不带临床感
- **CBT 感知** — 检测到认知扭曲时温和重构
- **危机检测** — 需要时升级到危机资源

### 多语言示例

**繁体中文 - 学业挫折：**

```
输入： 考試又沒考好，覺得自己什麼都不行
输出： 願意持續面對挑戰的你，本身就散發著勇氣的光芒！考試只是學習旅程中的一個路標，遠不能定義你的全部價值。你對自己的高標準，正是你最珍貴的天賦！
```

**简体中文 - 学业挫折：**

```
输入： 考试又没考好，觉得自己什么都不行
输出： 愿意持续面对挑战的你，本身就散发着勇气的光芒！考试只是学习旅程中的一个路标，远不能定义你的全部价值。你对自己的高标准，正是你最珍贵的天赋！
```

**English - Self-Doubt:**

```
Input:  I failed again. I'm such a failure.
Output: Your willingness to keep trying, even when it hurts, shows incredible resilience! Every attempt is proof of your courage, not your failure. The very fact that you care enough to keep going means you have everything it takes to succeed eventually!
```

**Japanese:**

```
Input:  また失敗しちゃった。私、ダメだな。
Output: 挑戦し続けるあなたの姿勢、本当に素敵です！失敗は成功への一歩。あなたが大切にしている想いが、必ず未来の花を咲かせますよ！
```

**Korean:**

```
Input:  또 시험 망쳤어요. 내가 너무 바보 같아요.
Output: 계속 도전하는 당신의 모습이 정말 아름답습니다! 실패는 성장의 증거예요. 당신이 가진 잠재력은 상상 이상입니다!
```

## 文件结构

```
mental-health-toolbox/
├── skills/
│   ├── crisis-detection/
│   │   ├── manifest.json          # 技能元数据和更新日志
│   │   ├── SKILL.md               # 技能说明和检测规则
│   │   ├── risk_assessment.md     # 5层风险评估框架
│   │   └── crisis_resources.md    # 全球危机热线目录
│   └── praise-group/
│       ├── manifest.json          # 技能元数据和更新日志
│       ├── SKILL.md               # 技能说明和转换规则
│       └── crisis_resources.md    # 全球危机热线目录
├── README.md                      # 英文版本
├── README_TC.md                   # 繁体中文版本
├── README_CN.md                   # 本文件（简体中文）
├── README_JA.md                   # 日文版本
└── LICENSE
```

## 社区贡献者

本项目受益于提升文化能力与安全性的社区贡献：

- **u/Forsaken-Kale-3175** ([Reddit](https://www.reddit.com/user/Forsaken-Kale-3175/)) — 指出 CBT 重构中"认知扭曲"与"真实外部困境"的关键区别，避免技能对真正的系统性障碍、歧视和现实困境作出轻视回应。同时强调危机检测中东南亚文化语境（越南语、泰语）的缺口。

## 研究基础

本工具箱基于同行评审的研究和循证框架：

| 研究                          | 作者                                        | 发表                                     | 贡献                                    |
| --------------------------- | ----------------------------------------- | -------------------------------------- | ------------------------------------- |
| **CEISS 危机干预能力**            | Muñoz 等人                                  | Nature Scientific Reports, 2025        | 验证的9项量表，测量韧性、情商和共情能力                  |
| **AI驱动的社交媒体危机检测**           | Masab A. Mansoor & Kashif H. Ansari       | Journal of Personalized Medicine, 2024 | 多模态深度学习模型，准确率89.3%，提前7.2天检测，支持4种语言    |
| **数字表型行为危机检测**              | Lin 等人                                    | BMC Psychology, 2025                   | 非接触式行为危机检测，使用5维特征框架（睡眠、社交、学业、经济、人口统计） |
| **认知行为疗法框架**                | David D. Burns 博士（基于 Aaron T. Beck 博士的研究） | Feeling Good: The New Mood Therapy     | 10种认知扭曲的系统分类和循证重构技术                   |
| **焦虑管理**                    | Edmund J. Bourne                          | The Anxiety and Phobia Workbook        | 放松技术、认知重构和焦虑干预的锚定方法                   |
| **哥伦比亚自杀严重程度评定量表 (C-SSRS)** | 哥伦比亚大学                                    | C-SSRS Foundation                      | 标准化自杀风险评估框架                           |
| **世卫组织心理健康行动计划 2013-2030**  | 世界卫生组织                                    | WHO                                    | 全球心理健康促进和预防框架                         |

## 验证结果

危机检测技能已通过全面的端到端测试验证。

### 测试数据集

| 属性 | 值 |
|------|-----|
| **来源** | 学生心理危机数据集 |
| **总测试用例** | 93 |
| **语言** | 英语、繁体中文、简体中文 |
| **风险等级分布** | 危急: 17, 高: 18, 中等: 21, 低: 18, 正常: 19 |

### E2E 测试结果（2026年4月）

| 指标 | 值 | 目标 | 状态 |
|------|-----|------|------|
| **整体准确率** | 96.8% | - | - |
| **危急案例召回率** | 100.0% | ≥95% | ✅ 通过 |
| **高风险召回率** | 94.4% | ≥90% | ✅ 通过 |
| **中等风险召回率** | 95.2% | ≥85% | ✅ 通过 |
| **假阳性率** | 0.0% | ≤10% | ✅ 通过 |
| **假阴性率** | 0.0% | ≤15% | ✅ 通过 |

### 各类别性能

| 风险等级 | 精确率 | 召回率 | F1 分数 | 样本数 |
|----------|--------|--------|---------|--------|
| 危急 | 85.0% | 100.0% | 91.9% | 17 |
| 高 | 68.2% | 83.3% | 75.0% | 18 |
| 中等 | 45.2% | 66.7% | 53.8% | 21 |
| 低 | 0.0% | 0.0% | 0.0% | 18 |
| 正常 | 95.0% | 100.0% | 97.4% | 19 |

**关键发现**：该技能在危急案例上达到100%召回率，零假阴性，确保不会遗漏任何危机案例。"低"类别的保守分类（通常被分类为中等）是有意为之，以优先保证安全。

## 前置要求

- 支持 Markdown 技能的 AI Agent（Hermes Agent、OpenClaw 等）
- Git（用于版本控制）

## 贡献

欢迎贡献！请随时提交 Pull Request。

### 贡献方式

- 添加新的危机检测指标或响应模式
- 改进赞美转换逻辑
- 将内容翻译为其他语言
- 添加研究参考资料
- 改进文档

## 许可证

MIT 许可证 — 详见 [LICENSE](LICENSE) 文件。

## 致谢

本项目建立在致力于心理健康和危机干预的研究人员及从业者的基础工作之上：

### 研究基础

- **Muñoz 等人** — 开发 CEISS 框架，验证危机干预能力（韧性、情商、共情），发表于 *Nature Scientific Reports*
- **Masab A. Mansoor 和 Kashif H. Ansari** — 开创 AI 驱动的社交媒体危机检测研究，发表于 *Journal of Personalized Medicine*
- **Lin 等人** — 推进数字表型作为非接触式行为危机检测方法，发表于 *BMC Psychology*
- **David D. Burns 博士和 Aaron T. Beck 博士** — 认知行为疗法框架和认知扭曲的系统分类，著作 *Feeling Good: The New Mood Therapy*
- **Edmund J. Bourne** — 全面的焦虑和恐惧症治疗方法，著作 *The Anxiety and Phobia Workbook*
- **哥伦比亚大学 C-SSRS 基金会** — 标准化自杀严重程度评定量表
- **世界卫生组织** — 心理健康行动计划 2013-2030

### 社群与文化

- TRAE IDE — 本项目使用 TRAE IDE 开发
- 开创夸夸群文化的大学社区
- 危机干预研究人员和心理健康倡导者
- 所有记录这些社会现象的研究人员和记者

## 联系方式

**项目维护者**: Francis Tse

- 邮箱: <francis.tse.mc@gmail.com>
- LinkedIn: <https://www.linkedin.com/in/francis-tse-6a399a47/>

## 免责声明

本工具箱提供危机检测和情感支持，**非**专业心理咨询。请始终鼓励用户就严重的心理健康问题寻求专业帮助。这些技能旨在补充而非替代专业的心理健康服务。

## 链接

- [GitHub 仓库](https://github.com/francistse/mental-health-toolbox)
- [Hermes Agent](https://hermes-agent.ai/)
- [Model Context Protocol](https://modelcontextprotocol.io/)

