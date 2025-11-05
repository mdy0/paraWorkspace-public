# Use Case Instructions

This document defines the specific actions Claude should take for each use case in the PARA writing system.

## How to Use This Document

When the user triggers a use case (either explicitly by number like "UC-12" or implicitly by request), Claude should follow the corresponding workflow below. Each use case specifies:
- What the user says/does
- What Claude should do (step-by-step)
- What confirmation to provide

---

## CAPTURE

### UC-1: Capture idea (no source attached)

**User says:** "I have an idea about [topic]"

**Claude does:**
1. Create folder: `3-Resources/01-inbox/YYYYMMDD-topic-name/`
2. Create file: `idea.md` inside with the idea content
3. Confirm: "Captured idea in inbox"

---

### UC-2: Capture idea with source(s) attached

**User says:** "I just read this [source] and it gave me an idea about [topic]" [provides link/file]

**Claude does:**
1. Create folder: `3-Resources/01-inbox/YYYYMMDD-topic-name/`
2. Create file: `idea.md` with the idea
3. Save source: `source-name.md` (or .pdf, etc.) in same folder
4. Confirm: "Captured idea with source in inbox"

---

### UC-3: Capture source only

**User says:** "Save this article/source for later"

**Claude does:**
1. Create folder: `3-Resources/01-inbox/YYYYMMDD-source-description/`
2. Save source: `source-name.md` (or link, pdf, etc.)
3. Confirm: "Source saved to inbox"

---

### UC-4: Create snippet from source

**User says:** "Here's a screenshot/text of something I wrote in [email/Slack/chat] - save this as a snippet"

**Claude does:**
1. Read/extract text from screenshot or provided text
2. Create file: `3-Resources/03-snippets-library/snippet-topic-name.md`
3. Add markdown content with context (where it came from, date)
4. Confirm: "Snippet saved to library"

---

### UC-5: Review list of captured items to decide what to work on

**User says:** "Show me what's in my inbox" or "What ideas do I have waiting?"

**Claude does:**
1. List contents of `3-Resources/01-inbox/`
2. Scan each folder's `idea.md` (if exists)
3. Present summary: "You have X items in inbox: [list with brief descriptions]"
4. Ask: "Which would you like to develop into a project?"

---

## RESEARCH

### UC-6: Get AI assessment of source usefulness for specific project

**User says:** "Which sources would be useful for [project]?"

**Claude does:**
1. Read project context: `1-Projects/[project-name]/00-status.md` and `02-outline.md`
2. Review sources in `3-Resources/01-inbox/` and `02-sources/to-read/`
3. Analyze relevance to project goals
4. Provide ranked recommendations with reasoning

---

### UC-7: Track read vs unread status of sources

**User says:** "I just finished reading this [topic] article - file it"

**Claude does:**
1. Move from: `3-Resources/02-sources/to-read/[source-file]`
2. Move to: `3-Resources/02-sources/[Category]/[source-file]`
   - Categories: AI, Tech, Business, Politics, Culture, Science, Writing
3. Confirm: "Source marked as read and filed under [Category]"

**Note:** Being in to-read/ = unread; Being in a category folder = read

---

### UC-8: Extract quotes/key points with attribution

**User says:** "Extract the key quotes from this article for my project"

**Claude does:**
1. Read the source article
2. Identify key quotes/insights
3. Add to: `1-Projects/[project-name]/01-research/quotes.md` with proper attribution
4. Format: `"Quote text" - Author Name, Source Title`
5. Confirm: "Added X quotes to project research"

---

### UC-9: Synthesize multiple sources into own perspective

**User says:** "Help me synthesize what I've learned from these sources about [topic]"

**Claude does:**
1. Read sources in `1-Projects/[project-name]/01-research/sources/`
2. Review existing `quotes.md`
3. Create/update synthesis in: `1-Projects/[project-name]/01-research/synthesis.md`
4. Include: common themes, contradictions, emerging perspective
5. Confirm: "Created/updated synthesis document"

---

## INCUBATION

### UC-10: Revisit idea periodically, add thoughts over time (marination)

**User says:** "I have more thoughts on that [topic] idea from [timeframe]"

**Claude does:**
1. Find: `3-Resources/01-inbox/YYYYMMDD-topic-name/idea.md`
2. Append new thoughts with date stamp: `## Update YYYY-MM-DD`
3. Confirm: "Added thoughts to marinating idea"

**Note:** Ideas stay in inbox while marinating; no separate "marinating" folder

---

### UC-11: View all snippets/fragments for a project to spot patterns

**User says:** "Show me all the snippets I've written for [project]"

**Claude does:**
1. List contents of: `1-Projects/[project-name]/04-snippets/`
2. Read each snippet file
3. Present summary with themes/patterns observed
4. Suggest: potential groupings or outline structure
5. Confirm understanding

---

## WRITING

### UC-12: Write draft content (snippet, brain dump, or shitty first draft)

**User says:** "Let me write a snippet/draft about [topic]" (with or without specifying project)

**Claude does:**
1. Determine destination:
   - If assigned to project: `1-Projects/[project-name]/04-snippets/[topic].md`
   - If orphaned: `1-Projects/_orphaned-snippets/[topic].md`
2. User dictates/writes content
3. Save to appropriate location
4. Confirm: "Snippet/draft saved"

---

### UC-13: Use split-screen: notes left, draft right - dump and sculpt

**User says:** "Let's do a dump and sculpt session for [section/topic]"

**Claude does:**
1. Present relevant notes from: `1-Projects/[project-name]/01-research/`
2. User writes/dictates while referring to notes
3. Save draft to: `1-Projects/[project-name]/05-drafts/[section]-draft-v1.md`
4. Confirm: "Draft created from notes"

**Note:** This is collaborative - Claude presents research, user creates draft while looking at it

---

### UC-14: Mark section as "TK" (to come) and skip

**User says:** "I'm stuck on this [section/transition] - mark it TK and let's move on"

**Claude does:**
1. In current draft file, insert: `[TK - brief description of what's needed]`
2. Optional comment: `<!-- TODO: Come back to this -->`
3. Continue with next section
4. Confirm: "Marked as TK, moving forward"

---

### UC-15: Maintain multiple versions/approaches to same section

**User says:** "I want to try a different approach to [section] - save this version first"

**Claude does:**
1. Current version: `05-drafts/[section]-approach-A.md`
2. Create new: `05-drafts/[section]-approach-B.md`
3. User writes alternate version
4. Both versions preserved for comparison
5. Confirm: "Multiple approaches saved"

---

## OUTLINING

### UC-16: Create or modify outline

**User says:** "Let's create/update the outline for [project]"

**Claude does:**
1. Edit: `1-Projects/[project-name]/02-outline.md`
2. Structure with:
   - Sections/subsections
   - Checkboxes for completion tracking
   - References to snippets: `04-snippets/[name].md`
   - Link to shiny dime: `03-shiny-dime.md`
   - Notes on what's needed (TK items)
3. Confirm: "Outline created/updated"

---

## DISTILLATION

### UC-17: Find shiny dime candidates

**User says:** "Help me identify the core idea of this [draft/project]"

**Claude does:**
1. Read draft from: `05-drafts/` or review project materials
2. Analyze for central themes, recurring ideas, surprising insights
3. Update: `1-Projects/[project-name]/03-shiny-dime.md`
4. Add section: `## Candidates` with 3-5 options
5. Present options with rationale for user feedback

---

### UC-18: Finalize shiny dime

**User says:** "Option [X] is the one - that's my shiny dime"

**Claude does:**
1. Update: `1-Projects/[project-name]/03-shiny-dime.md`
2. Add section: `## Final Shiny Dime: [the chosen one]`
3. Add reasoning/context
4. Update `02-outline.md` to reference it
5. Confirm: "Shiny dime finalized and linked in outline"

---

### UC-19: Create coined phrase / lingual meme

**User says:** "This concept needs a catchy name" or "Let's brainstorm a coined phrase"

**Claude does:**
1. Brainstorm options based on the concept
2. Add to: `03-shiny-dime.md` under `## Coined Phrase Candidates`
3. Present options with characteristics (surprising, ambiguous, visual, fun)
4. When chosen, highlight in outline and drafts
5. Confirm: "Coined phrase captured"

---

### UC-20: Compress content without losing substance

**User says:** "This section is too long - compress it from X to Y words"

**Claude does:**
1. Read section in: `05-drafts/[draft-file].md`
2. Identify core points and supporting evidence
3. Remove redundancy, tighten prose, combine related ideas
4. Save as new version: `[draft-file]-v2.md` (preserve original)
5. Report: "Compressed from X to Y words"
6. Confirm substance retained

---

## REVISION

### UC-21: Revise for clarity, flow, structure, style

**User says:** "Let's polish [draft/section]"

**Claude does:**
1. Read: `05-drafts/draft-vX.md`
2. Make revisions for:
   - Clarity (remove ambiguity)
   - Flow (smooth transitions)
   - Structure (logical progression)
   - Style (voice consistency, word choice)
3. Save as: `05-drafts/draft-v[X+1].md`
4. Highlight major changes made
5. Confirm: "Revised draft saved"

---

### UC-22: Manage version history / track changes between drafts

**User says:** "What changed between draft X and draft Y?"

**Claude does:**
1. Compare: `05-drafts/draft-vX.md` vs `05-drafts/draft-vY.md`
2. Highlight:
   - Additions (new content)
   - Deletions (removed content)
   - Restructuring (moved sections)
   - Refinements (rewritten parts)
3. Present summary of evolution
4. Confirm understanding

---

### UC-23: Save cut content (kill your darlings graveyard)

**User says:** "Cut this [section/paragraph] but save it - might use it later"

**Claude does:**
1. Copy content to be cut
2. Save to: `1-Projects/[project-name]/06-graveyard/cut-from-[source]-YYYYMMDD.md`
3. Add context:
   - Date cut
   - Where it was cut from
   - Why it was cut (if provided)
4. Remove from original draft
5. Confirm: "Content saved to graveyard and removed from draft"

---

## VOICE & STYLE

### UC-24: Study/imitate favorite writers' techniques

**User says:** "I want to study how [writer] does [technique]"

**Claude does:**
1. Create/update: `2-Areas/writing-craft/02-writer-studies/[writer-name]-[technique].md`
2. Capture user's observations and notes
3. Structure analysis of:
   - What the writer does
   - Why it works
   - How to apply it
4. Confirm: "Writer study notes saved"

---

### UC-25: Experiment with voices/styles, track what feels authentic

**User says:** "Let me try rewriting this in a [different style/voice]"

**Claude does:**
1. Create: `2-Areas/writing-craft/01-style-experiments/[style-description]-YYYYMMDD.md`
2. User writes experimental version
3. Capture user's reflections:
   - How it felt to write
   - What worked/didn't work
   - Whether it felt authentic
4. Confirm: "Style experiment saved with reflections"

---

## DISTRIBUTION

### UC-26: Adapt content for different platforms

**User says:** "Turn this article into a [Twitter thread/newsletter/etc.]"

**Claude does:**
1. Read source: `1-Projects/[project-name]/08-published/` or `05-drafts/`
2. Adapt for target platform format:
   - Twitter: thread with hooks, numbered tweets
   - Newsletter: email-friendly formatting
   - Blog: web formatting with headers, links
3. Save to: `07-distribution/[platform-name].md`
4. Confirm: "[Platform] version created"

---

## POST-PUBLICATION

### UC-27: Update/correct published piece

**User says:** "There's a [typo/error/update needed] in the published version"

**Claude does:**
1. Read: `1-Projects/[project-name]/08-published/[piece].md`
2. Make correction/update
3. Add note with date stamp: `<!-- Updated YYYY-MM-DD: [what changed] -->`
4. Confirm: "Published version updated"

---

## PROJECT MANAGEMENT

### UC-28: View all active projects with status

**User says:** "What projects am I working on?" or "Show me my project dashboard"

**Claude does:**
1. Read: `1-Projects/_active-projects.md`
2. Scan each active project's `00-status.md`
3. Present dashboard with:
   - Project name
   - Current phase (research/outlining/drafting/etc.)
   - Progress indicators
   - Next steps
   - Blockers/TK items
4. Confirm understanding and ask what to work on

---

### UC-29: Quick context switch: "where was I on Project X?"

**User says:** "Remind me where I left off on [project]"

**Claude does:**
1. Read: `1-Projects/[project-name]/00-status.md`
2. Present:
   - Last work done (with date)
   - Current state/phase
   - Next immediate steps
   - Open questions/TK items
   - Blockers (if any)
3. Offer to continue where left off
4. Confirm: "Ready to continue?"

---

## SESSION MANAGEMENT

### UC-30: End session (save state, document progress, note what's next)

**User says:** "I'm done for today" or "Let's wrap up"

**Claude does:**
1. Create: `3-Resources/06-session-logs/YYYY-MM-DD-session.md`
2. Document:
   - Date/time
   - Projects worked on (with links)
   - Use cases executed (with UC numbers)
   - Key decisions made
   - Work completed (files created/modified)
   - Problems encountered
   - Next steps for each project
   - Files modified/created (with paths)
3. Update: `1-Projects/_active-projects.md` with current status
4. Update each project's `00-status.md` if worked on
5. Confirm: "Session logged. See you next time!"

**Session Log Format:**
```markdown
# Session Log - YYYY-MM-DD

## Projects Worked On
- [Project Name 1]
- [Project Name 2]

## Use Cases Executed
- UC-X: [Description]
- UC-Y: [Description]

## Key Decisions
- [Decision 1]
- [Decision 2]

## Work Completed
- [Accomplishment 1]
- [Accomplishment 2]

## Problems Encountered
- [Problem/blocker if any]

## Next Steps
- [Project 1]: [Next action]
- [Project 2]: [Next action]

## Files Modified/Created
- path/to/file1.md (created/modified)
- path/to/file2.md (created/modified)
```

---

### UC-31: Resume session (review previous work, load context, identify next steps)

**User says:** "Catch me up on [timeframe]" or "What did we work on in the last [X] days?"

**Claude does:**
1. Find logs in: `3-Resources/06-session-logs/`
2. Identify relevant date range
3. Read all session logs in range
4. Synthesize comprehensive summary:
   - Projects worked on
   - Progress made (with specifics)
   - Decisions made
   - Use cases executed
   - Open items/TKs
   - Blockers
   - Recommended next steps
5. Present narrative summary (not just bullet points)
6. Ask: "What would you like to work on today?"

---

## CROSS-PROJECT

### UC-32: Find all material on Topic X across projects

**User says:** "Find everything I have about [topic] across all projects"

**Claude does:**
1. Search comprehensively across:
   - `1-Projects/*/00-status.md`
   - `1-Projects/*/01-research/`
   - `1-Projects/*/02-outline.md`
   - `1-Projects/*/03-shiny-dime.md`
   - `1-Projects/*/04-snippets/`
   - `1-Projects/*/05-drafts/`
   - `3-Resources/01-inbox/`
   - `3-Resources/02-sources/`
   - `3-Resources/03-snippets-library/`
2. Present findings organized by:
   - Project name
   - Material type (idea/source/snippet/draft)
   - Relevance/context
3. Highlight connections or patterns between projects
4. Confirm: "Found material in X projects and Y resource locations"

---

## FINALIZATION

### UC-33: Final copyedit, fact-check, format, write meta-content

**User says:** "This draft is ready for final polish before publishing"

**Claude does:**
1. Read: `05-drafts/[final-draft].md`
2. Copyedit:
   - Grammar and punctuation
   - Style consistency
   - Flow and transitions
   - Word choice precision
3. Fact-check:
   - Verify claims against sources in `01-research/`
   - Flag anything that needs citation
4. Format for target platform
5. Create meta-content:
   - Title options (3-5)
   - Subtitle options
   - Description/summary
   - Social media snippets
6. Save final version: `08-published/[article-title].md`
7. Save meta-content: `08-published/[article-title]-meta.md`
8. Confirm: "Ready to publish - all checks complete"

---

## Notes on Use Case Execution

### General Principles:
1. **Always confirm** what was done and where files were saved
2. **Use consistent naming** with dates (YYYYMMDD format) where applicable
3. **Preserve versions** - don't overwrite, create new versions
4. **Add context** - include dates, sources, reasoning in files
5. **Update indexes** - keep `_active-projects.md` and session logs current
6. **Cross-reference** - link related files (outline → snippets, status → drafts)

### When in doubt:
- Ask the user which project/location is appropriate
- Default to inbox for captures
- Create new versions rather than overwriting
- Document decisions in status.md files

### File Naming Conventions:
- Dates: `YYYYMMDD` (2025-11-05 becomes 20251105)
- Versions: `-v1`, `-v2`, etc.
- Drafts: `draft-v1.md`, `draft-v2.md`
- Approaches: `section-approach-A.md`, `section-approach-B.md`
- Cuts: `cut-from-[source]-YYYYMMDD.md`
- Sessions: `YYYY-MM-DD-session.md`
- Chats: `YYYY-MM-DD-topic.md`

---

*Last Updated: 2025-11-05*
