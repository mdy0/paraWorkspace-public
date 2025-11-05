# paraWriting

A PARA Method implementation optimized for writers and thinkers working with Claude Code.

## What is PARA?

PARA is an organizational method created by Tiago Forte that categorizes information by actionability:

- **Projects** - Active work with specific goals and deadlines
- **Areas** - Ongoing responsibilities and interests to maintain over time
- **Resources** - Reference materials and topics of interest
- **Archives** - Inactive items from the other three categories

## Directory Structure

```
paraWorkspace/
├── 0-Metadata/           # System documentation and external materials
├── 1-Projects/           # Active writing projects
├── 2-Areas/              # Ongoing interests (e.g., writing craft)
├── 3-Resources/          # Reference library and idea inbox
└── 4-Archives/           # Completed/inactive items
```

See the full directory tree and workflow documentation in `0-Metadata/instructions/`.

## Working with Claude

### For Claude Code Agents

**IMPORTANT:** When the user triggers any use case (either explicitly by number like "UC-12" or implicitly by request), Claude must follow the specific workflows defined in:

**`0-Metadata/instructions/usecase-instructions.md`**

This file contains:
- 33 use cases covering the complete writing workflow
- Step-by-step actions for each use case
- File naming conventions
- Where to save different types of content

Before taking action on any user request, Claude should:
1. Identify which use case(s) apply
2. Follow the documented workflow in usecase-instructions.md
3. Confirm actions taken with the user

**Note:** User prefers GitHub Desktop for git operations. See `0-Metadata/instructions/github-desktop-guide.md` for how to provide instructions.

### Session Management

Every session should:
- **Start** with UC-31 (Resume session) if requested
- **End** with UC-30 (End session) to log progress

Session logs in `3-Resources/06-session-logs/` enable "catch me up on the last X days" queries.

## Key Features

### Numbered Workflow Progression
Projects follow a numbered sequence from capture through publication:
- 00-status.md → 01-research/ → 02-outline.md → 03-shiny-dime.md → 04-snippets/ → 05-drafts/ → 06-graveyard/ → 07-distribution/ → 08-published/

### Idea Marination
Ideas captured in `3-Resources/01-inbox/` can stay there indefinitely, accumulating thoughts over time (UC-10). When ready, they move directly to `1-Projects/`.

### Source Organization
Sources flow: `to-read/` (unread) → `[Category]/` (read and categorized by: AI, Tech, Business, Politics, Culture, Science, Writing)

### Version Control
- Multiple draft versions preserved (draft-v1, draft-v2, etc.)
- Cut content saved in graveyard (never lost)
- Multiple approaches to sections maintained (approach-A, approach-B)

## Use Cases Overview

The system supports 33 use cases across categories:
- **Capture** (UC-1 to UC-5): Ideas, sources, snippets
- **Research** (UC-6 to UC-9): Assessment, extraction, synthesis
- **Incubation** (UC-10 to UC-11): Marination, pattern recognition
- **Writing** (UC-12 to UC-15): Drafts, brain dumps, TK marking
- **Outlining** (UC-16): Structure creation
- **Distillation** (UC-17 to UC-20): Finding core ideas, compression
- **Revision** (UC-21 to UC-23): Polish, versioning, graveyard
- **Voice & Style** (UC-24 to UC-25): Writer studies, experiments
- **Distribution** (UC-26): Platform adaptation
- **Post-Publication** (UC-27): Updates and corrections
- **Project Management** (UC-28 to UC-29): Status tracking, context switching
- **Session Management** (UC-30 to UC-31): Logging, resuming
- **Cross-Project** (UC-32): Finding material across all projects
- **Finalization** (UC-33): Copyediting, fact-checking, meta-content

See `0-Metadata/instructions/usecase-instructions.md` for complete details.

## Philosophy

This system is designed to:
1. **Reduce friction** - Capture first, organize later
2. **Support iteration** - Preserve versions, experiment freely
3. **Enable discovery** - Find connections across projects
4. **Maintain context** - Always know where you left off
5. **Build consistently** - Small daily progress over time

## Getting Started

1. Review the use case instructions: `0-Metadata/instructions/usecase-instructions.md`
2. Start with UC-1 (Capture an idea) or UC-31 (Resume session)
3. Let ideas marinate in the inbox
4. Move to projects when ready to develop

## Resources

- [PARA Method by Tiago Forte](https://fortelabs.com/blog/para/)
- [David Perrell's Ultimate Guide to Writing Online](inputs/davidperell_the-ultimate-guide-to-writing-online.md)
- [Thinking Agent System Prompt](inputs/thinking-agent.md)

---

*Last Updated: 2025-11-05*
