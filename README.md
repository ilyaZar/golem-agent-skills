# golem-agent-skills

Shared golem skills packaged for Claude Code and Codex.

Canonical skill content lives in [`skills/`](./skills). Provider-specific plugin
metadata lives under [`plugins/`](./plugins), with marketplaces at
[`/.claude-plugin/marketplace.json`](./.claude-plugin/marketplace.json) and
[`/.agents/plugins/marketplace.json`](./.agents/plugins/marketplace.json).

## Claude Code installation

Add the marketplace from GitHub:

```text
/plugin marketplace add ilyaZar/golem-agent-skills
```

Confirm the marketplace is available:

```text
/plugin marketplace list
```

Install the plugin:

```text
/plugin install golem-claude-skills@golem-skills
```

Reload plugins if prompted:

```text
/reload-plugins
```

After installation, the following plugin skills should be available:

```text
/golem-claude-skills:golem-upgrade
/golem-claude-skills:golem-fix-missing-ns
```

## Remove the plugin

```text
/plugin uninstall golem-claude-skills
/plugin marketplace remove golem-skills
/reload-plugins
```

## golem package helper

The `golem::use_agent_skills()` helper can also install the same skill payloads
into a golem project. It reads from the canonical upstream `skills/` tree and
copies into provider-specific target directories in the consuming project:

- Claude target: `.claude/skills/`
- Codex target: `.agents/skills/`

This keeps the upstream repository canonical while preserving the expected
project layout for each tool.
