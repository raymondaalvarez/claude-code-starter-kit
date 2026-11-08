# Claude Code starter kit (ArrayTechLabs)

The setup from our reel: the files that make Claude Code remember your project, follow your rules,
and check its own work. Copy them into the root of your project.

```
CLAUDE.md                          ← your project's rules, loaded at the start of every session
.claude/
  settings.json                    ← a hook: formats every file Claude edits (always runs)
  skills/
    ship-check/SKILL.md            ← a skill: pre-launch audit (secrets, Supabase RLS, Stripe, SEO)
  agents/
    reviewer.md                    ← a subagent: reviews your changes in its own context
```

## Install
1. Get the files: click **Code → Download ZIP** on this page (or
   `git clone https://github.com/raymondaalvarez/claude-code-starter-kit`). Then copy `CLAUDE.md` and the
   `.claude/` folder into your project root.
2. Fill in the `CLAUDE.md` placeholders, or run `/init` in Claude Code to generate one from your
   codebase and merge in the rules section.
3. The hook needs [`jq`](https://jqlang.org/) and Prettier (`npm i -D prettier`). Don't use Prettier?
   Swap the command for your formatter, or delete the hook.
4. Start Claude Code in the project and try:
   - "What are this project's rules?" (reads CLAUDE.md)
   - `/ship-check` (runs the skill)
   - "Use the reviewer agent on my last change." (delegates to the subagent)

## Connectors (MCP)
Connect your real tools with `claude mcp add`. For example, the docs show
`claude mcp add --transport http notion https://mcp.notion.com/mcp`. Only connect servers you trust.

## Docs
- CLAUDE.md and memory: https://code.claude.com/docs/en/memory
- Skills: https://code.claude.com/docs/en/skills
- Hooks: https://code.claude.com/docs/en/hooks-guide
- MCP: https://code.claude.com/docs/en/mcp
- Subagents: https://code.claude.com/docs/en/sub-agents

Made by ArrayTechLabs · websites + AI apps · arraytechlabs.com · MIT licence, use it however you like.
