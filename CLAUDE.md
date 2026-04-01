# product-analyst 插件

产品分析师插件，提供结构化的需求发现、风暴、澄清和 PRD 生成流程。

## 插件结构

```
product-analyst/
├── .claude-plugin/plugin.json    # 插件注册
├── hooks/
│   ├── hooks.json                # SessionStart hook 配置
│   └── session-start.sh          # 会话启动时注入 PO Agent 人设 + 创建工作目录
├── prompts/
│   └── po-agent.md               # PO Agent 提示词（由 hook 注入）
├── commands/
│   └── pa.md                     # /pa 斜杠命令入口
└── skills/
    ├── pa/SKILL.md                       # 主编排：串联 SC→BR→CL→GP
    ├── scan-context/SKILL.md             # 扫描上下文（借助 Explore Agent）
    ├── brainstorm-requirements/          # 需求风暴
    │   ├── SKILL.md
    │   └── references/brainstorm-principles.md
    ├── clarify-requirements/             # 需求澄清
    │   ├── SKILL.md
    │   └── references/clarify-principles.md
    └── generate-prd/                     # 生成 PRD
        ├── SKILL.md
        ├── references/prd-writing-guide.md
        └── assets/prd-template.md
```

## 技能清单

| 技能 | 命令 | 说明 |
|------|------|------|
| pa | `/product-analyst:pa` | 完整流程编排 |
| scan-context | `/product-analyst:scan-context` | 扫描项目上下文提取领域知识 |
| brainstorm-requirements | `/product-analyst:brainstorm-requirements` | 收敛式需求风暴 |
| clarify-requirements | `/product-analyst:clarify-requirements` | 逐项追问边界和三条链路 |
| generate-prd | `/product-analyst:generate-prd` | 生成极简 PRD 文档 |
