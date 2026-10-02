# spec-stress-tester

Stress a PRD into PM decision cards before eng starts.

## What it does

The spec stress-tester finds decisions a PM must make before starting eng: ambiguities, untestable acceptance criteria, missing edges, and trust/compliance gaps. It outputs a PM decision artifact, not an eng bug dump.

## Install

### Cursor

1. Open [marvinvista/spec-stress-tester](https://github.com/marvinvista/spec-stress-tester) in Cursor (Clone repo or open the folder).
2. Copy `skills/spec-stress-tester/` into your project's `.cursor/skills/`.
3. In chat, ask: "Stress this PRD" and paste a PRD or Notion link.

### Codex

1. Clone or download [marvinvista/spec-stress-tester](https://github.com/marvinvista/spec-stress-tester).
2. Copy `skills/spec-stress-tester/` into the project's `.agents/skills/`.
3. In Codex, ask: "Stress this PRD" and paste a PRD or Notion link.

### Claude Code

1. Clone or download [marvinvista/spec-stress-tester](https://github.com/marvinvista/spec-stress-tester).
2. Copy `skills/spec-stress-tester/` into the project's `.claude/skills/`.
3. In Claude Code, ask: "Stress this PRD" and paste a PRD or Notion link.

## Usage

Attach your PRD or product brief and tell the agent to use the spec stress-tester skill. The agent runs the checklist and outputs prioritized decision cards.
