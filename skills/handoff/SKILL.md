---
name: handoff
description: Refresh or prepare repository handoff docs from verified state; use concise task indexes to reduce Agent context. Trigger on handoff requests and consider before a requested new conversation or end of one. Repository cleanup only when requested; not for application RAM or system-wide storage analysis.
---

# Handoff

Keep handoff material short enough to use and specific enough to resume work safely. Prefer one current entry point with task-based links over repeating implementation history across several files.

## Workflow

1. Determine whether the user wants a review, document edits, or a handoff for a new conversation. For a review-only request, report findings without changing files. For an explicit request to start another conversation or end this one, consider whether a durable handoff is useful; do not assume it is always needed.
2. Read applicable `AGENTS.md` files, the project README, current-version/status indexes, and only the task-specific source records needed to establish current facts. Check `git status --short` and relevant diffs before editing. Treat untracked files as user work.
3. Separate content into:
   - **Current state and next action:** verified versions, what is unfinished, and any decision that must come from a person.
   - **Stable constraints:** only the safety, evidence, data, and authorization boundaries needed by a successor.
   - **Reference index:** map likely next tasks to canonical files, reports, or frozen evaluation folders.
   - **History:** dated facts that explain past decisions but must not appear as live tasks.
4. Reduce context load by removing repeated explanations and copied logs, using short summaries plus task-based links, and loading detailed evidence only when the task needs it. Keep enough context to identify the next step and its constraints; do not optimize for brevity at the cost of a safe handoff.
5. If the user also asks to reduce repository footprint, inspect only relevant large/generated candidates. Distinguish application RAM, Agent context, and files on disk. Check reproducibility, references, and uniqueness before cleanup; never treat “can be downloaded again” as sufficient reason to delete. Preserve frozen evaluations, raw/source data, raw evidence, human ratings, hashes, unique decisions, and referenced deliverables. Prefer removing confirmed regenerable clutter over source or history.
6. Within the requested document-editing or cleanup scope, before deleting, moving, renaming, or collapsing a document, search references and confirm its unique information remains available. When slimming old handoffs, prefer a dated summary pointing to original evidence; mark archived instructions as history, not current tasks.
7. Update incoming links and project reading order when the current entry point changes. Keep one authoritative home for mutable facts; link to it instead of copying long explanations into every handoff.
8. Never include credentials or secret values in a handoff. For portable or public-facing skill/handoff content, prefer repository-relative references and exclude personal paths and private identifiers. Include local paths or private identifiers only when needed for an explicitly requested local-only handoff.
9. Verify local Markdown links relative to each file, scan current entry points for stale versions or pending tasks, inspect edited text directly, and run `git diff --check` where applicable. Remember Git diff checks omit untracked files. Documentation-only edits do not need application tests unless requested or warranted by a code change.
10. Report which documents changed, what was shortened or indexed, what historical material was preserved, and the checks performed. State any genuinely pending human decision without presenting it as completed.

## Conversation handoffs

When a user explicitly asks to start a new conversation, prepare a concise handoff from verified project state and relevant sources if it will improve continuity. If they explicitly ask to end the current conversation, consider preparing or updating the handoff before ending. A handoff request does not itself authorize unrelated cleanup, publishing, or external messages. Use the conversation-management tool only for the action the user explicitly requested; otherwise leave the handoff ready in the requested location.
