# tech-domain-learning

[![Agent Skills](https://img.shields.io/badge/Agent_Skills-compatible-6e47ff?logo=openai)](https://agentskills.io/)
[![Cursor](https://img.shields.io/badge/Cursor-ready-00b27e)](https://cursor.com/docs/skills)
[![Claude Code](https://img.shields.io/badge/Claude_Code-ready-d97757)](https://docs.anthropic.com/en/docs/claude-code/skills)

**AI 驱动的系统化技术学习框架（Cursor / Claude Code Agent Skill）** —— 将任意技术专题拆解为路线、阶段讲义与可运行 Demo，由 AI 按统一质量约定持续产出；你只需专注学习与复盘。技能定义见根目录 [`SKILL.md`](SKILL.md)。

---

## 为什么用这个技能

| 痛点 | 本技能解法 |
|------|-----------|
| 收藏一堆链接从不打开 | **按阶段交付** `THEORY.md`：因果叙事、关键概念、拓展提问，一份文档读完一个子主题 |
| 教程版本过时、URL 失效 | **知识来源四准则**（稳定 / 可信 / 真实 / 前沿），WebSearch 验证后写入 |
| 看懂了但写不出代码 | 每阶段配套 **可运行 `demo/`**，本地跑起来改参数做实验 |
| 学习进度不可追踪 | **`PROGRESS.md` 是唯一进度真相**，阶段状态与完成记录一目了然 |
| 换个方向又要从零规划 | 同一套技能对任意技术方向复用，说出方向即可生成路线 |

---

## 学习工作流

```
用户说出技术方向
       |
       v
  ROADMAP.md          <-- 4~8 阶段路线图，含 ASCII 箭头图 + 阶段详情表
       |
       v
  按阶段推进
       |
       +---> THEORY.md     <-- 理论讲义（索引 + 因果论证 + 具象示例 + 核心概念 + 拓展提问）
       +---> demo/          <-- 可运行代码（Maven / Docker Compose / SQL 等，含 README.md）
       |
       v
  PROGRESS.md          <-- 追踪每阶段状态、日期、时长、收获
```

交付 `ROADMAP.md` 与初始 `PROGRESS.md` 后，技能约定 **暂停并请用户审阅**；确认后再生成阶段 1 的完整物料。详见 [`SKILL.md`](SKILL.md) 工作流 A~D。

---

## 快速开始

```bash
# 1. 克隆本仓库（技能 + 可选本地学习产出）
git clone https://github.com/searchforsun/tech-domain-learning.git
cd tech-domain-learning

# 2. 仅浏览已有学习笔记 —— 打开 learning/<专题>/，从 ROADMAP.md 开始
#    （首次使用可能尚无 learning/，由 AI 按专题创建）

# 3. 在 AI 编辑器中安装技能 —— 见下方「技能安装」
```

安装后在对话里说 **「帮我学某技术方向」**（将「某技术方向」换成你的主题）等触发短语即可使用；完整列表见 [`SKILL.md`](SKILL.md#触发短语)。

---

## 技能安装

### Claude Code / Codex

```bash
git clone https://github.com/searchforsun/tech-domain-learning.git ~/.claude/skills/tech-domain-learning
```

或在其他机器上自定义路径后，将仓库置于 Claude Code 配置的 skills 目录中即可。

### Cursor

**全局安装：**

```bash
git clone https://github.com/searchforsun/tech-domain-learning.git %USERPROFILE%\.cursor\skills\tech-domain-learning
```

**项目级安装：**

```bash
mkdir .cursor\skills
git clone https://github.com/searchforsun/tech-domain-learning.git .cursor\skills\tech-domain-learning
```

安装后在命令面板执行 **Developer: Reload Window**。

### 使用 GitHub URL 安装

部分 Agent 编辑器支持从仓库 URL 直接安装：

```
https://github.com/searchforsun/tech-domain-learning
```

---

## 质量约定

生成或修改内容后自检以下 6 条门禁（与 [`SKILL.md`](SKILL.md#质量门禁) 一致）：

| # | 检查项 | 规则 |
|---|--------|------|
| 1 | 时效标记 | 路线含生成日期 +「以官方文档为准」类免责声明 |
| 2 | 路线图 | 4~8 阶段，含自上而下 ASCII 箭头图 |
| 3 | 反提纲 | 每节有连续因果叙述，禁止整节纯表格/列表充数 |
| 4 | 版式一致 | `## 一、` 顺排，每节末含核心概念 + 拓展提问提示词 |
| 5 | 知识来源 | URL/API/版本号经 WebSearch 验证，引自官方文档或权威出版物 |
| 6 | URL 真实 | 推荐阅读链接经 WebSearch 验证，链接行仅 URL |

理论讲义与 Demo 说明的细纲分别见 [`reference/theory.md`](reference/theory.md)、[`reference/demo-readme.md`](reference/demo-readme.md)；目录与命名见 [`reference/naming-and-layout.md`](reference/naming-and-layout.md)。

---

## 仓库结构

```
tech-domain-learning/
├── README.md                 # 本说明
├── SKILL.md                  # Agent Skill 主定义（触发语、工作流、质量门禁）
├── reference/                # 模板与约束（AI 生成内容时遵循）
│   ├── naming-and-layout.md
│   ├── roadmap-progress.md
│   ├── theory.md
│   ├── theory-recommended-reading.md
│   └── demo-readme.md
└── learning/                 # 学习产出（按专题生成，可随仓库版本管理或私有 fork）
    └── <技术专题中文简称>/
        ├── ROADMAP.md
        ├── PROGRESS.md
        └── <序号>-<阶段中文名>/
            ├── THEORY.md
            └── demo/
                └── README.md
```

若 fork 后修改 `reference/` 内约定或路径，请同步检查 [`SKILL.md`](SKILL.md) 中的相对路径引用。

---

## 相关链接

- [Agent Skills 开放标准](https://agentskills.io/)
- [Cursor — Agent Skills](https://cursor.com/docs/skills)
- [Claude Code — Skills](https://docs.anthropic.com/en/docs/claude-code/skills)

---

## 许可

MIT。学习笔记与技能内容随仓库维护；修改 `reference/` 或技能定义时请保持文档与路径一致。
