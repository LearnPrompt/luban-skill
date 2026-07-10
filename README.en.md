<div align="center">

<sub>🌐 English · <a href="README.md">中文</a></sub>

# Luban | 鲁班

> Bring your Skill before the master's gate, and let the grandmaster polish it anew.

[![Agent Skills](https://img.shields.io/badge/Agent%20Skills-luban-blueviolet)](skills/luban/SKILL.md)
[![skills.sh](https://skills.sh/b/LearnPrompt/luban-skill)](https://skills.sh/LearnPrompt/luban-skill)
[![Case Study](https://img.shields.io/badge/Case%20Study-ai--news--radar%20v0.7.0-green)](skills/luban/examples/ai-news-radar-case.md)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

**Turn a Skill that "works" into a public asset that can be understood, installed, shared, verified, and continuously improved.**

[Install](#quick-start) · [The Five Moves](#the-five-moves) · [Track Record](#track-record) · [How It Differs](#how-it-differs-from-the-alternatives) · [Safety Boundaries](#safety-boundaries) · [Credits](#methodology-credits)

</div>

---

## Quick Start

![luban demo](assets/demo.gif)

```bash
npx skills add LearnPrompt/luban-skill -g
```

Claude Code users can also install via the plugin marketplace (auto-updates):

```text
/plugin marketplace add LearnPrompt/luban-skill
/plugin install luban
```

Once installed, tell your Agent:

```text
Let Luban take a look at my skill: [your Skill directory / GitHub repo link / SKILL.md content]
```

Luban will first complete material inspection, trade survey, positioning, and measurement, then give you three polishing directions with a recommendation — **it will not touch a single line until you pick a direction**.

## What Problem It Solves

You wrote a Skill. It works fine for you. Then what?

- You publish it on GitHub and nobody installs it — people can't tell what it does;
- The README reads like an engineering spec: no first-screen hook, no screenshot-worthy output;
- You say it "works well," but you can't produce a single reproducible piece of evidence;
- You want to improve it, but don't know where to start — rewrite the trigger phrases? Redo the workflow? Add a showcase?

The usual approach is "polish this up for me." Luban's approach is to take it into the workshop as a **piece of craftsmanship**: first challenge whether it's worth carving at all, then see how its peers earn their place, measure its weak spots with three rulers, plane it stroke by stroke — every stroke must pass a validation gate — and finally ship a release with house rules set in place.

## What It Delivers

- **A 13-section Polishing Report**: material-inspection verdict, peer comparison table (all with URLs), ecological-niche assessment, scorecard, three polishing directions, and drop-in rewrite snippets
- **A screenshot-ready "Graduation Certificate"**: before/after scores, a one-line new positioning, the signature strength, and next steps
- **Verification assets deposited into your repo**: one-off comparison scripts hardened into tools, and judgment criteria written down as explicit project rules

## The Five Moves

| Move | What it does | One blunt line |
|---|---|---|
| **验料 Yanliao / Inspect Materials** | Challenge whether the Skill's premise holds at all | Rotten wood cannot be carved — if it's not worth it, say so |
| **访行 Fangxing / Survey the Trade** | Search the web for peers and map the ecological niche | No good tool was ever built behind closed doors |
| **过尺 Guochi / Measure Up** | Score it with three rulers: structure, live testing, liveness | Green CI can lie — reconcile against real artifacts |
| **慢刨 Manpao / Plane Slowly** | Freeze the baseline; keep a change only if it passes the validation gate | If it doesn't measure up, undo the stroke — never plane just to look busy |
| **回炉 Huilu / Back to the Forge** | Leave a post-release watchlist; next round starts from feedback | Delivery is not the finish line |

## How to Trigger

- "Let Luban look at this skill" / "Polish it at the master's gate"
- "Upgrade my skill" / "Polish my skill"
- "Skill checkup" / "Skill audit"
- "Why does nobody install my skill"
- "How do I publish this skill to GitHub/ClawHub"
- "Benchmark this against similar skills"

## Track Record

Luban's first job: polishing [ai-news-radar](https://github.com/LearnPrompt/ai-news-radar) (~1k stars) from v0.6 to [v0.7.0](https://github.com/LearnPrompt/ai-news-radar/releases/tag/v0.7.0), completed within a single conversation, with all 4 PRs merged:

- The **liveness check** caught a data pipeline that had been silently stale for **8 days** under all-green Actions (a git add allowlist omission)
- The scoring fix was validated by replaying **83,725** historical records: **327** false-AI entries purged, zero collateral damage
- Single-source share in the featured section: **15/20 → 4/20**; first-screen render: **806 → 523 cards**, page height **-30%**
- The verification method was deposited as a repo tool, `backtest_scoring.py`, along with a new project rule: "any scoring change must ship with a ≥14-day replay"

Full record (including incidents and lessons): [skills/luban/examples/ai-news-radar-case.md](skills/luban/examples/ai-news-radar-case.md) — every number links to a clickable PR.

## How It Differs from the Alternatives

| | Just asking an Agent to "make it look nicer" | **Luban** |
|---|---|---|
| Starting point | Rewrites the copy immediately | First challenges the premise: does this Skill deserve to exist? |
| Basis | The model's taste | Peer benchmarking (with URLs) + three-ruler scoring (with evidence) |
| Method | Changes everything at once, impossible to attribute | Freezes the baseline; one commit per facet; kept only if it passes the validation gate |
| Verification | "Looks better" | Real-data replay with before/after flip numbers |
| Ending | Done when the edits are done | Verification tools deposited, rules established, forge-return watchlist left behind |

## Safety Boundaries

- **Mandatory stop points**: proposing a repositioning, merging to the default branch, tagging a release, any deployment visible to real users — each waits for your explicit authorization; **your question ("all good, right?") does not count as authorization**.
- Never writes API keys, tokens, cookies, or private paths into any public artifact.
- Changes are always presented as auditable commits — no brute-force rollbacks like `git reset --hard`.

## File Structure

```text
luban-skill/
├── skills/luban/
│   ├── SKILL.md                    # The workflow itself: five moves, nine-step process, house rules and acceptance checklist
│   └── examples/
│       └── ai-news-radar-case.md  # Case study: real repo, real numbers, fully verifiable
├── assets/                         # demo GIF and reproducible recording script (vhs tape)
├── .claude-plugin/                 # Claude Code plugin marketplace manifest
├── README.md
└── LICENSE
```

## Verification & Testing

After installing, run this acceptance check:

```text
Let Luban look at this skill: https://github.com/anthropics/skills
```

A passing run: it first outputs the material-inspection challenge and a peer comparison with URLs, offers three directions, and stops to wait for your choice — instead of jumping straight into rewriting.

## Methodology Credits

Luban's five moves weren't invented from thin air; they stand on the shoulders of:

- [KKKKhazix/khazix-skills · hv-analysis](https://github.com/KKKKhazix/khazix-skills/blob/main/hv-analysis/SKILL.md) — Horizontal-vertical analysis: trace the lineage vertically, compare peers horizontally, and let the intersection form the judgment (the skeleton of Fangxing and positioning)
- [alchaincyf/darwin-skill](https://github.com/alchaincyf/darwin-skill) — Evaluate → improve → test → keep or roll back; independent-judge perspective; the ratchet mechanism (the soul of Guochi and Manpao)
- [microsoft/SkillOpt](https://github.com/microsoft/SkillOpt) — Frozen baselines, bounded candidate edits, validation-gated acceptance (the origin of the validation gate)
- And one real end-to-end engagement, [ai-news-radar v0.7.0](skills/luban/examples/ai-news-radar-case.md) — liveness checks, verification-asset deposits, workbench discipline, and the return to the forge were all learned there

## License

[MIT](LICENSE) — use it, modify it, let it polish your work.

---

<div align="center">

*Yanliao · Fangxing · Guochi · Manpao · Huilu*

**Learn the craft, not just the surface.**

</div>

---

<div align="center">

**更多好用 Skill · More Skills** → [learnprompt.pro/skills](https://learnprompt.pro/skills/)

[鲁班·Skill打磨](https://github.com/LearnPrompt/luban-skill) · [庖丁·博主蒸馏](https://github.com/LearnPrompt/paoding-skill) · [蔡伦·对话造纸](https://github.com/LearnPrompt/cailun-skill) · [阿福·LLM Todo](https://github.com/LearnPrompt/afu-llm-todo) · [愚公·Loop工程](https://github.com/LearnPrompt/loop-engineering) · [搭子·结对开发](https://github.com/LearnPrompt/partner-skill) · [AI雷达·零API资讯](https://github.com/LearnPrompt/ai-news-radar)

[淘金小镇·ClawHub日榜](https://github.com/LearnPrompt/skillrush-town) · [Irasutoya·正文配图](https://github.com/LearnPrompt/carl-irasutoya-illustrations) · [Humanize PPT·演讲系统](https://github.com/LearnPrompt/humanize-ppt) · [CC Harness·六件套](https://github.com/LearnPrompt/cc-harness-skills) · [微信读书教练](https://github.com/LearnPrompt/carl-weread) · [X Article发布](https://github.com/LearnPrompt/x-article-publisher-skill)

<sub>**[LearnPrompt](https://github.com/LearnPrompt) 出品** · 公众号「卡尔的AI沃茨」 · [X @aiwarts](https://x.com/aiwarts)</sub>

</div>
