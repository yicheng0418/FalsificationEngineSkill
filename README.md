# Falsification Engine 证伪引擎

一个 reasoning skill（推理技能），用来对**论断、新闻、商业主张、投资决策、政策方案、AI 生成内容**做批判性检验。

它的核心不是去"证明一个说法是对的"，而是去**找出它在什么条件下会错**。

> 理念来源：波普尔证伪主义（Popperian falsification）——一个理论无法靠反复验证被绝对证明为真，但**一个有效的反例就能推翻它**。

---

## 它干了什么 / What it does

面对任何一段主张，引擎会按固定流程逼问自己：

1. **提取核心论断** —— 这句话到底在断言什么？
2. **识别隐藏假设** —— 要让它成立，哪些前提必须为真？
3. **区分事实与解读** —— 哪些是观察，哪些是人赋予的意义？
4. **构建因果链** —— 事实是怎么推导出结论的？
5. **搜索证伪点** —— 哪里最可能塌？
6. **生成蓝队挑战** —— 假设我是它最强的对手，怎么把它驳倒？
7. **产出结构化报告** —— 把以上结论整理成可读的文档。

最终产出不是"对/错"的武断结论，而是一份标注了**隐藏假设、因果链、证伪点、反例、蓝队挑战、置信度**的清单，让你自己判断。

---

## 核心理念 (Philosophy)

- **证伪主义**：理论无法被反复确认绝对证明，单个有效反例即可推翻。
- **信息价值**：能改变先验信念的信息才有价值；符合预期的事几乎不提供新信息。
- **事实与观点分离**：事实描述观察，观点解释意义，两者必须保持独立。

---

## 何时使用 (When to use)

- 判断新闻 / 社媒内容的可信度
- 审视商业或投资主张
- 评估政策提案的可执行性
- 复盘战略决策的逻辑
- 检验 AI 生成内容是否站得住脚

---

## 模块 (Modules)

| 模块 | 作用 |
| --- | --- |
| `modules/assumption-extractor.md` | **假设提取器**：挖掘结论背后的隐藏前提，标出未经证实的假设 |
| `modules/causal-chain-checker.md` | **因果链检验器**：检查 `事实 → 解释 → 结论` 的推导，识别逻辑跳跃与被忽略的替代解释 |
| `modules/black-swan-detector.md` | **黑天鹅探测器**：优先关注异常、矛盾、缺失信息，寻找能推翻结论的最小证据 |
| `modules/trojan-horse-detector.md` | **特洛伊木马探测器**：识别"9 真 + 1 假"结构，分离真实观察、无支撑推论与隐藏因果假设 |
| `modules/blue-team.md` | **蓝队**：扮演最强对手，提供反驳、替代模型、缺失证据与可能的失败场景 |

---

## 工作流预设 (Workflows)

针对常见场景的专用流程：

| 工作流 | 关注点 |
| --- | --- |
| `workflows/investment-analysis.md` | 检验市场 / 成长 / 竞争优势 / 财务逻辑 / 风险假设，定位投资论点最薄弱的一环 |
| `workflows/news-analysis.md` | 抽取标题主张、识别共识、寻找意外元素、区分报道与评论、检验因果推理 |
| `workflows/policy-analysis.md` | 审视问题定义、假设、执行机制、非预期后果，找出可能在现实中失效的假设 |

---

## 输出报告 (Report)

所有分析统一按 `templates/falsification-report.md` 的结构输出：

- **Claim** —— 原论断
- **Hidden Assumptions** —— 隐藏假设
- **Causal Chain** —— 因果链
- **Falsification Points** —— 证伪点
- **Counterexamples** —— 反例
- **Blue Team Challenge** —— 蓝队挑战
- **Confidence Assessment** —— 置信度评估

---

## 规则 (Rules)

**避免：**
- 自动接受用户的假设
- 把相关性误当因果
- 用个例当作证明

**要求：**
- 主动怀疑（active skepticism）
- 提供替代解释
- 标注不确定性（uncertainty labeling）

---

## 目录结构

```
falsification-engine-skill/
├── SKILL.md                      # 技能主文档（触发条件与总流程）
├── core/
│   └── philosophy.md             # 证伪主义 / 信息价值 / 事实观点分离
├── modules/                      # 五个分析模块
│   ├── assumption-extractor.md
│   ├── causal-chain-checker.md
│   ├── black-swan-detector.md
│   ├── trojan-horse-detector.md
│   └── blue-team.md
├── templates/
│   └── falsification-report.md   # 统一报告模板
└── workflows/                    # 场景化工作流
    ├── investment-analysis.md
    ├── news-analysis.md
    └── policy-analysis.md
```

---

## 使用方法

作为 WorkBuddy / agent 的 skill 加载。典型触发方式：

- "证伪这个观点"
- "检验一下这个投资论点"
- "这条新闻可信吗？找反例"
- "帮我对这个决策做蓝队挑战"

引擎会自动走完上述流程，并按报告模板产出结论。
