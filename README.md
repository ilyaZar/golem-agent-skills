# golem-agent-skills

Shared `{golem}` skills packaged for Claude Code and openAI codex/GPT 5.4.

Canonical skill content lives in [`skills/`](./skills).

Made by [ThinkR](https://thinkr.fr/) for professional Shiny development.

## Claude Code installation

1. Add the marketplace from GitHub:
    ```text
    /plugin marketplace add ilyaZar/golem-agent-skills
    ```

2. Confirm the marketplace is available:
    ```text
    /plugin marketplace list
    ```

3. Install the plugin:
    ```text
    /plugin install golem-skills@thinkr
    ```

4. Reload plugins if prompted:
    ```text
    /reload-plugins
    ```

5. After installation, the following plugin skills should be available:
    ```text
    /golem-skills:golem-upgrade
    /golem-skills:golem-fix-missing-ns
    ```

## Remove the plugin

```text
/plugin uninstall golem-skills
/plugin marketplace remove thinkr
/reload-plugins
```

## `{golem}` package helper

The `golem::use_agent_skills()` (starting with version `0.6.0`) helper can also
install the same skill payloads into a `{golem}` project. It reads from the
canonical upstream `skills/` tree and copies into provider-specific target
directories in the consuming Shiny App project:

- Claude target: `.claude/skills/`
- Codex target: `.agents/skills/`
