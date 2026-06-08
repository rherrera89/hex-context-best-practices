# Hex Context Best Practices

An Agent Skill that helps data teams build and roll out a **context strategy** for Hex's AI agents
(Threads, the Notebook Agent, and the Modeling Agent). It advises on and **drafts** the context
assets, plans a phased rollout, and diagnoses why an agent gave a wrong answer.

It works across Claude Code, Claude.ai, OpenAI Codex, and other agents that read Markdown skills.

## What's inside

```
hex-context-best-practices/
├── .claude-plugin/
│   ├── marketplace.json                  # Claude Code marketplace catalog
│   └── plugin.json                       # plugin manifest
├── skills/
│   └── hex-context-best-practices/
│       ├── SKILL.md                      # orchestrator — start here
│       ├── agents/
│       │   ├── context-architect.md      # draft the context assets; fix wrong answers
│       │   └── rollout-planner.md        # phased Threads rollout + tracker offer
│       └── references/
│           ├── intake.md                 # questionnaire to customize to a setup
│           ├── context-assets-deep-dive.md  # workspace context/guides + semantic YAML examples
│           ├── advanced-context.md       # reference repositories + External Apps / MCP
│           ├── ask-hex.md                # in-product / MCP / CLI ways to get Hex's improvement signal
│           └── hex-docs.md               # canonical Hex doc links (fetch before UI steps)
├── AGENTS.md                             # Codex / generic-agent entry point
└── README.md
```

## Install

### Claude Code (plugin marketplace)
```
/plugin marketplace add rherrera89/hex-context-best-practices
/plugin install hex-context-best-practices@hex-skills
```
Then just ask, e.g. *"help me build a context strategy for our revenue KPIs in Hex."*

### Any agent CLI (cross-tool, Agent Skills standard)
```
npx skills add rherrera89/hex-context-best-practices
```
Works with Claude Code, Codex, Cursor, Gemini CLI, and others that support the Agent Skills spec.

### OpenAI Codex
Clone the repo into your project (or alongside it); `AGENTS.md` points Codex at the skill:
```
git clone https://github.com/rherrera89/hex-context-best-practices
```
Then ask Codex to follow `skills/hex-context-best-practices/SKILL.md`.

### Claude.ai (no code)
Download `hex-context-best-practices.skill` from the
[latest release](https://github.com/rherrera89/hex-context-best-practices/releases) and upload it in
Settings → Capabilities → Skills (paid plans).

### Manual (Claude Code personal skill)
```
git clone https://github.com/rherrera89/hex-context-best-practices
cp -r hex-context-best-practices/skills/hex-context-best-practices ~/.claude/skills/
```

## How it works
1. The agent reads `SKILL.md`, learns the mental model (four context assets on a guidance→governance
   spectrum, plus advanced sources), and routes to a specialist.
2. It gathers a little context via `references/intake.md` (or mines docs you attach).
3. **Context Architect** drafts paste-ready assets and a test plan, scoped to one use case.
4. **Rollout Planner** produces a phased plan and can turn it into a spreadsheet or Notion tracker.
5. You iterate — context compounds, and each new use case gets faster.

## Credit
Distilled from Hex's *Data Leader's Playbook for AI Analytics* and Hex's published best-practice docs.
Hex and the named features are products of Hex Technologies; this is an independent aid for using them.

## License
MIT
