---
version: 2.0
status: Stable
---

# AI-Copilot：AI 分析助手

## 概述
输入一个问题，AI Copilot 自动调用五大 OS + Cases + Models，生成完整分析报告。

## 工作流程
```
用户输入（例如："帮我分析腾讯"）
    │
    ▼
1. 识别意图 → 判断需要调用哪些 OS/Models/Cases
2. 调用 Decision-OS → 拆解问题
3. 调用 Financial-OS → 企业分析 + 估值
4. 调用 Business-OS → 商业模式 + 护城河 + 竞争
5. 查询 Cases/腾讯.md → 已有案例参考
6. 查询 Models/ → 引用相关模型
7. 整合 → 生成结构化报告
```

## 触发逻辑表
| 用户输入类型 | 主 OS | 辅助 OS | 查询模型 | 查询案例 |
|------------|-------|---------|---------|---------|
| "分析[某公司]" | Financial-OS | Business-OS | 企业模型、估值模型、护城河 | 对应案例 |
| "这个行业前景如何？" | Business-OS | Financial-OS | 竞争模型、周期模型、S-Curve | AI.md |
| "现在应该投资什么？" | Decision-OS | Financial-OS + Life-OS | 概率思维、机会成本、周期模型 | 2008.md |
| "帮我做一个人生决策" | Life-OS | Decision-OS | 机会成本、反馈循环 | 模板/人生决策 |
| "这个新闻意味着什么？" | Decision-OS | Financial-OS + Business-OS | 信号与噪音、反馈循环 | 模板/新闻分析 |

## 输出模板（Markdown）
```
# AI Copilot 分析报告

## 问题：
## 调用的 OS：
## 引用的模型：
## 引用的案例：
## 分析：
## 结论与建议：

---

*Powered by Project Atlas*
```
