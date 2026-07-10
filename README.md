<div align="center">

<sub>🌐 <a href="README.en.md">English</a> · 中文</sub>

# 鲁班 | Luban

> 把你的Skill拿到班门前，让祖师爷重新打磨一遍。

[![Agent Skills](https://img.shields.io/badge/Agent%20Skills-luban-blueviolet)](skills/luban/SKILL.md)
[![skills.sh](https://skills.sh/b/LearnPrompt/luban-skill)](https://skills.sh/LearnPrompt/luban-skill)
[![Hermes Agent](https://img.shields.io/badge/Hermes%20Agent-compatible-green)](https://hermes-agent.nousresearch.com/docs)
[![实战案例](https://img.shields.io/badge/%E5%AE%9E%E6%88%98%E6%A1%88%E4%BE%8B-ai--news--radar%20v0.7.0-green)](skills/luban/examples/ai-news-radar-case.md)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

**把一个"能用的Skill"，打磨成"能被理解、能被安装、能被传播、能被验证、能持续进化"的公共资产。**

[安装](#快速开始) · [五个动作](#五个动作) · [实战战绩](#实战战绩) · [它和同类有什么不同](#它和同类有什么不同) · [安全边界](#安全边界) · [致谢](#方法论致谢)

</div>

---

## 快速开始

![luban demo](assets/demo.gif)

```bash
npx skills add LearnPrompt/luban-skill -g
```

Claude Code 用户也可以走 plugin marketplace（自动更新）：

```text
/plugin marketplace add LearnPrompt/luban-skill
/plugin install luban
```

Hermes Agent 用户：

```bash
hermes skills install LearnPrompt/luban-skill
```

或手动安装：

```bash
git clone https://github.com/LearnPrompt/luban-skill.git /tmp/luban-skill
cp -r /tmp/luban-skill/skills/luban ~/.hermes/skills/productivity/luban
```

装完对Agent说：

```text
让鲁班看看我这个skill：[你的Skill目录 / GitHub仓库链接 / SKILL.md内容]
```

鲁班会先完成验料、访行、定位、过尺，给你三个打磨方向并推荐一个——**在你选方向之前，它不会动你一行字**。

## 它解决什么问题

你写了一个Skill，自己用着挺好。然后呢？

- 发到GitHub，没人装——别人看不懂它是干嘛的；
- README像工程说明书，没有第一屏钩子，没有能截图的产物；
- 你说它"效果不错"，但拿不出一个能复现的证据；
- 想优化，又不知道该先动哪里——改触发词？重写工作流？补showcase？

普通的做法是"帮我润色一下"。鲁班的做法是把它当**作品**收进工坊：先挑战它值不值得雕，再看同行凭什么立足，三把尺量出短板，一刀一刀刨，每刀都要过验证门，最后发版立规矩。

## 它会交付什么

- **一份13节的《打磨报告》**：验料结论、同行对标表（全部带URL）、生态位判断、评分表、三个打磨方向、可直接替换的改写片段
- **一张可截图的"出师证书"**：打磨前后分数、一句话新定位、绝活、下一步
- **沉淀进你仓库的验证资产**：一次性的对比脚本固化成工具，判断标准立成项目明文规矩

## 五个动作

| 动作 | 干什么 | 一句狠话 |
|---|---|---|
| **验料** | 先挑战这个Skill的前提是否成立 | 朽木不可雕也，不值得就直说 |
| **访行** | 联网找同行，看清生态位 | 闭门造车出不了好工具 |
| **过尺** | 结构、实测、活体三把尺量分 | 绿色的CI会撒谎，要拉真实产物对账 |
| **慢刨** | 冻结基线，改动过验证门才保留 | 量不过就回刀，绝不为显得干了活而多刨 |
| **回炉** | 发布后留对标观察清单，下轮从反馈进 | 交活不是终点 |

## 触发方式

- "让鲁班看看这个skill" / "班门打磨一下"
- "升级我的skill" / "打磨我的skill"
- "skill体检" / "skill审计"
- "为什么我的skill没人装"
- "这个skill怎么发布到GitHub/ClawHub"
- "对标一下同类skill"

## 实战战绩

鲁班的第一单活：把 [ai-news-radar](https://github.com/LearnPrompt/ai-news-radar)（约1k星）从 v0.6 打磨到 [v0.7.0](https://github.com/LearnPrompt/ai-news-radar/releases/tag/v0.7.0)，一个对话内完成，4个PR全部合并：

- **活体检查**揪出 Actions 全绿之下静默停更 **8 天**的数据链路（git add 白名单遗漏）
- 评分修复用 **83,725 条**历史数据回放验证：清除 **327 条假AI**、零误伤
- 精选区单一信源占比 **15/20 → 4/20**；首屏渲染 **806 → 523 卡**，页高 **-30%**
- 验证手段沉淀为仓库工具 `backtest_scoring.py`，并立下"动评分必须附 ≥14 天回放"的项目规矩

全程记录（含事故与教训）：[skills/luban/examples/ai-news-radar-case.md](skills/luban/examples/ai-news-radar-case.md)——每个数字都挂着可点击的PR链接。

## 它和同类有什么不同

| | 直接让Agent"帮我改好看点" | **鲁班** |
|---|---|---|
| 起点 | 直接改文案 | 先挑战前提：这Skill值得存在吗？ |
| 依据 | 模型的审美 | 同行对标（带URL）+ 三把尺评分（带证据） |
| 改法 | 一次全改，无法归因 | 冻结基线，单提交单面，过验证门才保留 |
| 验证 | "看起来更好了" | 真实数据回放，给出翻转数字 |
| 结束 | 改完就完 | 验证工具入库、立规矩、留回炉清单 |

## 安全边界

- **强制停手点**：建议重构定位、merge到默认分支、打tag发版、对真实用户可见的部署——每一步都等你明确授权；**你的疑问句（"都好了吧？"）不构成授权**。
- 不把API key、token、cookie、私人路径写进任何公开产物。
- 改动永远以可审计的提交呈现，不用 `git reset --hard` 之类的暴力回滚。

## 文件结构

```text
luban-skill/
├── skills/luban/
│   ├── SKILL.md                    # 工作流本体：五个动作、九步流程、班规与验收单
│   └── examples/
│       └── ai-news-radar-case.md  # 实战案例：真实仓库、真实数字、全程可查证
├── assets/                         # demo GIF 与可复现的录制脚本（vhs tape）
├── .claude-plugin/                 # Claude Code plugin marketplace 清单
├── README.md
└── LICENSE
```

## 验证与测试

装完用这句验收：

```text
让鲁班看看这个skill：https://github.com/anthropics/skills
```

合格的表现：它先输出验料挑战和带URL的同行对标，给三个方向并停手等你选——而不是直接开始改写。

## 方法论致谢

鲁班的五个动作不是凭空造的，它站在这些工作的肩膀上：

- [KKKKhazix/khazix-skills · hv-analysis](https://github.com/KKKKhazix/khazix-skills/blob/main/hv-analysis/SKILL.md) — 横纵分析法：纵向追来路，横向看同期，交汇出判断（访行与定位的骨架）
- [alchaincyf/darwin-skill](https://github.com/alchaincyf/darwin-skill) — 评估 → 改进 → 实测 → 保留或回滚；独立评委视角；棘轮机制（过尺与慢刨的灵魂）
- [microsoft/SkillOpt](https://github.com/microsoft/SkillOpt) — 冻结基线、有边界的候选编辑、validation-gated接受（验证门的出处）
- 以及一次真实的全程实战 [ai-news-radar v0.7.0](skills/luban/examples/ai-news-radar-case.md)——活体检查、验证资产沉淀、工位纪律、回炉，都是它教的

## License

[MIT](LICENSE) — 随便用，随便改，随便让它帮你打磨。

---

<div align="center">

*验料 · 访行 · 过尺 · 慢刨 · 回炉*

**学手艺，不偷皮。**

</div>

---

<div align="center">

**[LearnPrompt](https://github.com/LearnPrompt) 出品** · 同门手艺

[鲁班·Skill打磨](https://github.com/LearnPrompt/luban-skill) · [庖丁·博主蒸馏](https://github.com/LearnPrompt/paoding-skill) · [蔡伦·对话造纸](https://github.com/LearnPrompt/cailun-skill) · [阿福·LLM Todo](https://github.com/LearnPrompt/afu-llm-todo) · [AI雷达·零API资讯](https://github.com/LearnPrompt/ai-news-radar) · [淘金小镇·ClawHub日榜](https://github.com/LearnPrompt/skillrush-town) · [Irasutoya·正文配图](https://github.com/LearnPrompt/carl-irasutoya-illustrations) · [Humanize PPT·简报编排](https://github.com/LearnPrompt/humanize-ppt) · [CC Harness·六件套](https://github.com/LearnPrompt/cc-harness-skills)

<sub>公众号「卡尔的AI沃茨」 · X @aiwarts · <a href="https://learnprompt.pro/workshop/">learnprompt.pro/workshop</a></sub>

</div>
