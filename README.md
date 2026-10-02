# spec-stress-tester

Stress a PRD into PM decision cards before eng starts.

## What it does

The spec stress-tester finds decisions a PM must make before starting eng: ambiguities, untestable acceptance criteria, missing edges, and trust/compliance gaps. It outputs a PM decision artifact, not an eng bug dump.

## Install in Cursor

1. Open this repository in Cursor (clone it or open the folder)
2. Copy `skills/spec-stress-tester/` into your project's `.cursor/skills/` directory
3. In chat, ask "Stress this PRD" and paste a PRD or Notion link

## Usage

Attach your PRD or product brief and tell the agent to use the spec stress-tester skill. The agent runs the checklist and outputs prioritized decision cards.
