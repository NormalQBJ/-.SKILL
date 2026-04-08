# 碧恩优.SKILL

---

`碧恩优.SKILL` 是一个面向碧恩优在读本科生的校园知识 Skill，重点覆盖：
- 选课、课程画像、GPA、成绩单、英语免修
- 保研、留学、就业导向、直博、一年制授课硕士等路径选择
- 学生规模、学部画像、学校资源利用
- 留学案例与方向分布

更多延伸内容可以关注：
- `NORMAL 情报局`
- `舰长说留学`

它不是官方系统，也不提供实时教务数据。它更适合做：
- 校园高频问题问答
- 路径判断与信息差补足
- 网页问答、校园场景演示、私有知识库前置层

## 适合什么场景

- 你想做一个面向碧恩优本科生的问答助手
- 你想快速回答选课、保研、留学、GPA、英语免修等高频问题
- 你想给 OpenClaw、Codex、Claude Code 这样的 AI 助手一套现成的校园知识包
- 你想在后续继续补学院细分资料、课程样本、案例库

## 当前结构

仓库主要由四部分组成：

- [SKILL.md](./SKILL.md)
  给模型看的主说明，定义能力范围、路由规则、回答方式
- [references/00-index.md](./references/00-index.md)
  知识索引，告诉模型不同问题该读哪份资料
- [references](./references)
  具体知识文件，按主题拆分
- [agents/openai.yaml](./agents/openai.yaml)
  Skill 列表里的 UI 元数据

## 知识模块

### 课程与学业

- [references/02-course-insights.md](./references/02-course-insights.md)
- [references/03-gpa-transcript.md](./references/03-gpa-transcript.md)
- [references/04-english-exemption.md](./references/04-english-exemption.md)

### 路径规划

- [references/08-graduate-path-choice.md](./references/08-graduate-path-choice.md)
- [references/09-career-oriented-planning.md](./references/09-career-oriented-planning.md)
- [references/10-phd-paths.md](./references/10-phd-paths.md)
- [references/11-taught-masters.md](./references/11-taught-masters.md)

### 学校画像与资源

- [references/05-graduates-2026.md](./references/05-graduates-2026.md)
- [references/06-resource-strategies.md](./references/06-resource-strategies.md)

### 留学案例

- [references/07-offer-insights.md](./references/07-offer-insights.md)

### 回答辅助

- [references/01-faq.md](./references/01-faq.md)
- [references/90-persona.md](./references/90-persona.md)
- [references/91-disclaimer.md](./references/91-disclaimer.md)
- [references/92-demo-questions.md](./references/92-demo-questions.md)

## 给 AI 助手怎么用

你可以直接把这个仓库链接发给你的 AI 助手，比如：
- OpenClaw
- Codex
- Claude Code

然后让它：
1. 下载或克隆这个仓库
2. 识别 `SKILL.md`
3. 把整个目录安装到对应的 `skills/` 目录
4. 按 `references/00-index.md` 和 `SKILL.md` 的路由规则使用它

一句话理解：
- 这个仓库本身就是一个可直接安装的 Skill 目录，不需要再额外拆文件
- AI 助手拿到仓库后，主要看 `SKILL.md`、`references/00-index.md`、`agents/openai.yaml`
- 如果你的助手支持 Skill / Skills / Tools / Knowledge Pack 这类目录安装方式，通常直接复制整个仓库即可

## 可以直接发给 AI 助手的话术

### 通用版

```text
请下载这个 GitHub 仓库，并把它安装成一个本地 Skill。优先读取仓库里的 SKILL.md 和 references/00-index.md，按里面的路由规则使用。安装完成后，确认 agents/openai.yaml、assets 和 references 都在正确位置。
```

### 给 Codex / Claude Code

```text
请把这个 GitHub 仓库安装成一个可用的本地 skill。识别仓库根目录下的 SKILL.md，把整个目录原样复制到本地 skills 目录，并检查 references、agents/openai.yaml、assets 是否完整。安装后按 SKILL.md 和 references/00-index.md 的路由规则使用它。不要改动知识内容本身，除非我明确让你更新。
```

### 给 OpenClaw

```text
请把这个仓库作为一个校园知识 skill 部署到本地环境。部署后，按 SKILL.md 的说明启用它，并确保它能读取 references/00-index.md 进行问题分流。
```

## 本地部署思路

如果你是手动部署，最简单的方式通常是：

1. 下载或克隆仓库
2. 把整个文件夹放到你的 skills 目录
3. 确保以下文件都存在：
   - `SKILL.md`
   - `references/`
   - `agents/openai.yaml`
   - `assets/bnu-skill.png`
4. 重新加载你的技能系统

## 仓库约定

为了让不同 AI 助手都更容易接入，这个仓库遵循几个简单约定：

- `SKILL.md` 是主入口
- `references/00-index.md` 是知识路由索引
- `references/*.md` 是专题知识文件
- `agents/openai.yaml` 是 UI 和默认提示词元数据
- `assets/` 只放展示资源，不承载核心知识

如果你后续继续扩内容，建议优先保持这个结构，不要把知识直接塞回 `SKILL.md` 里。

## 回答边界

这个 Skill 当前不主打：
- 本科招生
- 志愿填报
- 分数线咨询
- 实时教务查询

如果你准备用它做对外问答，建议保留这条原则：
- 用它做信息整理和判断辅助
- 不把它包装成官方系统
- 遇到强时效问题时，引导用户回学院通知、教务系统和学校最新文件确认

## 后续扩展方向

这套 Skill 适合继续往下扩：
- 更多学院和专业的细分资料
- 更完整的课程画像
- 更细的保研、留学、实习案例
- 更强的 FAQ 命中层
- 后续接网页、公众号入口或私有知识库服务
