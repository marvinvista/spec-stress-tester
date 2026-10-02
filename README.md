# spec-stress-tester

Stress a PRD into PM decision cards before eng starts.

## What it does

The spec stress-tester finds decisions a PM must make before starting eng: ambiguities, untestable acceptance criteria, missing edges, and trust/compliance gaps. It outputs a PM decision artifact, not an eng bug dump.

## Install in Cursor

### As an Agent Plugin

1. In Cursor, go to Settings → Cursor Plugins
2. Add this repo URL as a plugin source
3. Enable the plugin

The skill appears in the agent's available skills.

### As a standalone skill

Copy [`skills/spec-stress-tester/SKILL.md`](skills/spec-stress-tester/SKILL.md) to:
- `~/.cursor/skills-cursor/` for Cloud Agents
- Your local skills folder for Codex / Cursor IDE skills

## Usage

Attach your PRD or product brief and tell the agent to use the spec stress-tester skill. The agent runs the checklist and outputs prioritized decision cards.
