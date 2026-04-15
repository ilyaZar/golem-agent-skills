# golem-agent-skills

Shared `{golem}` skills packaged for Claude Code and openAI codex/GPT 5.4.

Canonical skill content lives in [`skills/`](./skills).

Made by [ThinkR](https://thinkr.fr/) for professional Shiny development.

## Overview

This repository provides:
- Claude Code and Codex plugin packaging around shared golem skills
- Best practice guidelines for Shiny app development
- A routed golem app builder skill for end-to-end app work
- Complete documentation for installation and development workflows

## What This Plugin Provides

A set of skills and guidelines for creating production-ready Shiny applications following R package best practices and golem conventions.

### Skills

- **Golem App Builder** - Build and evolve golem applications using routed references
- **Golem Upgrade** - Upgrade golem apps across package and structure changes
- **Golem Fix Missing ns** - Check modules for missing `ns()`

## Key Features

- Enforces R package best practices
- Golem naming conventions and patterns
- Reactive programming guidelines
- Module and function templates
- Test-driven development support
- Complete documentation and examples

## Development Workflow

```text
Create App -> Add Modules -> Add Functions -> Test -> Check -> Deploy
```

## Requirements

- R 4.0+
- golem package
- devtools package
- Shiny package

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
    /golem-skills:golem-app-builder
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

This keeps the upstream repository canonical while preserving the expected
project layout for each tool.
