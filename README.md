[README.md](https://github.com/user-attachments/files/27513785/README.md)
# ral_mimo
mimo max
# Customer Support Agent Demo

这是一个可直接运行的客服运营 Agent 示例项目，演示了一个简化版多 Agent 客服流程：

- `IntentAgent`：识别用户意图和紧急程度
- `KnowledgeRetrievalAgent`：从知识库检索可用处理规范
- `TicketRetrievalAgent`：匹配相似历史工单
- `RuleEngineAgent`：依据风险规则决定是否升级人工
- `ResponseAgent`：生成客服回复草稿
- `QualityAgent`：对回复进行最终校验和润色

## 运行方式

使用系统 Python：

```powershell
python .\support_agent.py --message "我的订单超过 7 天还没收到，物流一直没更新，请尽快处理。"
```

如果你想使用 Codex 自带 Python：

```powershell
C:\Users\LENOVO\.cache\codex-runtimes\codex-primary-runtime\dependencies\python\python.exe .\support_agent.py --message "我想申请退款，但是商品已经拆封了。"
```

## 示例能力

你可以测试这些输入：

```text
我的订单超过 7 天还没收到，物流一直没更新，请尽快处理。
我想申请退款，但是商品已经拆封了。
账号一直收不到验证码，导致我无法登录。
这个设备发热很严重，我担心有安全问题。
```

## 如何扩展成真实项目

1. 把 `data/knowledge_base.json` 替换为你们的 FAQ、SOP、售后规则。
2. 把 `data/historical_tickets.json` 替换为脱敏后的历史工单数据。
3. 将当前基于关键词的意图识别替换为 LLM 分类。
4. 将简单文本匹配替换为向量检索或 RAG。
5. 将 `RuleEngineAgent` 接入真实工单系统、CRM 或客服平台。
6. 将 `ResponseAgent` 改为调用大模型生成更自然的回复。

## 适合你在表单里怎么描述

你可以把这个项目包装成：

> 我搭建了一个客服运营 Agent，主要解决客服回复依赖人工经验、知识库更新滞后、复杂问题升级链路长的问题。系统会先识别用户意图，再结合知识库检索、历史工单匹配和规则引擎进行多轮判断；在复杂场景下由不同 Agent 分别负责检索、决策、生成和校验，最终输出可直接发送的回复或升级建议，从而显著提升首响效率和标准问题自动化覆盖率。
