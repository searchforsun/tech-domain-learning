# tech-domain-learning

[![Agent Skills](https://img.shields.io/badge/Agent_Skills-compatible-6e47ff?logo=openai)](https://agentskills.io/)
[![Cursor](https://img.shields.io/badge/Cursor-ready-00b27e)](https://cursor.com/docs/skills)
[![Claude Code](https://img.shields.io/badge/Claude_Code-ready-d97757)](https://docs.anthropic.com/en/docs/claude-code/skills)

**AI 驱动的系统化技术学习框架** —— 将任意技术专题拆解为路线、阶段讲义与可运行 Demo，由 AI 按统一质量约定持续产出。技能定义见 [`SKILL.md`](SKILL.md)。

---

## 为什么用这个技能

| 痛点 | 解法 |
|------|------|
| 收藏一堆链接从不打开 | 按阶段交付 `THEORY.md`：一份文档读完一个子主题 |
| 教程过时、URL 失效 | WebSearch 验证后写入，优先官方文档 |
| 看懂了但写不出代码 | 每阶段配套可运行 `demo/`，本地跑起来改参数做实验 |
| 学习进度不可追踪 | `PROGRESS.md` 是唯一进度真相 |
| 换个方向又要从零规划 | 同一套技能对任意技术方向复用 |

---

## 学习工作流

```
用户说出技术方向
       |
       v
  ROADMAP.md          ← 4~8 阶段路线图
       |
       v
  按阶段推进
       |
       +---> THEORY.md     ← 理论讲义（核心概念 + 原理 + 实践要点）
       +---> demo/          ← 可运行代码（含 README.md）
       |
       v
  PROGRESS.md          ← 追踪每阶段状态与收获
```

交付 ROADMAP.md 后暂停，用户审阅确认后再生成阶段内容。

---

## 快速开始

```bash
git clone https://github.com/searchforsun/tech-domain-learning.git
cd tech-domain-learning
```

安装后在对话里说「帮我学某技术方向」即可。详见 [`SKILL.md`](SKILL.md)。

---

## 技能安装

### Claude Code

```bash
git clone https://github.com/searchforsun/tech-domain-learning.git ~/.claude/skills/tech-domain-learning
```

### Cursor

```bash
git clone https://github.com/searchforsun/tech-domain-learning.git %USERPROFILE%\.cursor\skills\tech-domain-learning
```

---

## 仓库结构

```
tech-domain-learning/
├── README.md
├── SKILL.md                  # 技能主定义
├── reference/                # 模板与约束
│   ├── roadmap-progress.md
│   ├── theory.md
│   └── demo-readme.md
└── learning/                 # 学习产出（按专题生成）
    └── <技术专题简称>/
        ├── ROADMAP.md
        ├── PROGRESS.md
        └── <序号>-<阶段名>/
            ├── THEORY.md
            └── demo/
                └── README.md
```

---

## 许可

MIT。
