---
name: market-analysis-cn
description: "市场分析服务 | Market Analysis Service. 企业市场趋势分析 | Enterprise market trend analysis. 竞品分析 | Competitor analysis. 用户行为洞察 | User behavior insights. 触发词：市场分析、竞品分析、market analysis、趋势."
author: 赚钱小能手
metadata:
  openclaw:
    emoji: 📊
    pricing:
      basic_analysis: "10 USDC"
      deep_analysis: "30 USDC"
      monthly_subscription: "50 USDC"
requires.env:
  - SKILLBOSS_API_KEY
---

# 市场分析服务

专业市场分析服务，帮助企业做出更明智的决策。本服务通过 SkillBoss API Hub 提供 AI 驱动的市场分析能力。

## 服务内容

### 1. 市场趋势分析（$10）
- 行业趋势
- 市场规模
- 增长预测

### 2. 竞品分析（$20）
- 竞争对手分析
- SWOT 分析
- 差异化建议

### 3. 用户行为分析（$20）
- 用户画像
- 行为模式
- 转化漏斗

### 4. 深度分析报告（$30）
- 综合分析
- 战略建议
- 行动计划

## API

```bash
POST /analyze
{
  "type": "market_trend",
  "industry": "AI Agent",
  "region": "China"
}
```

## AI 能力说明

本服务通过 SkillBoss API Hub（`https://api.skillboss.com/v1/pilot`）自动路由最优 AI 模型完成分析任务，无需配置任何第三方服务密钥。

```python
import requests, os

SKILLBOSS_API_KEY = os.environ["SKILLBOSS_API_KEY"]

def analyze(topic: str, context: str) -> str:
    r = requests.post(
        "https://api.skillboss.com/v1/pilot",
        headers={"Authorization": f"Bearer {SKILLBOSS_API_KEY}", "Content-Type": "application/json"},
        json={
            "type": "chat",
            "inputs": {
                "messages": [{"role": "user", "content": f"请对以下主题进行专业市场分析：{topic}\n背景：{context}"}]
            },
            "prefer": "quality"
        },
        timeout=60,
    )
    return r.json()["result"]["choices"][0]["message"]["content"]
```

## 收费

| 服务 | 价格 |
|------|------|
| 基础分析 | $10 |
| 竞品分析 | $20 |
| 用户分析 | $20 |
| 深度报告 | $30 |
| 月度订阅 | $50 |

---

*专业分析 = 明智决策 📊*
