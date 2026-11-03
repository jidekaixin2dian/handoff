[![handoff: keep the project moving between conversations](assets/video-preview.jpg)](https://raw.githubusercontent.com/jidekaixin2dian/handoff/main/assets/handoff-intro.mp4)

[中文](README.md) · [Quick start](#start-with-codex) · [Triggers](#triggers-intent-first) · [Example](docs/example.md) · [Demo](#demo)

# handoff

**A new conversation. The same project, moving forward.**

Starting a new conversation during a long AI-assisted task often means explaining the project again: which version is current, what is finished, and what comes next?

`handoff` is a lightweight project handoff skill. It verifies the workspace state, strips stale material out of the handoff, indexes evidence by task, and leaves one current entry point. **You do not have to remember a command**: switching conversations, switching projects, switching agents, or wrapping up should be enough. Instruction-only, MIT licensed, with no extra service to deploy.

[Watch / download the 36-second introduction](https://raw.githubusercontent.com/jidekaixin2dian/handoff/main/assets/handoff-intro.mp4)

## Start with Codex

Install into the current project using the [skills CLI](https://github.com/vercel-labs/skills) (Claude Code and other skill-capable agents work the same way):

```bash
npx skills add jidekaixin2dian/handoff --skill handoff --agent codex
```

Then just say what you are doing:

```text
I want to continue this project in a new conversation.
```

Or invoke it explicitly:

```text
$handoff I want to continue this project in a new conversation.
Verify its current state, refresh the handoff entry point,
and preserve the evidence, constraints, and next action.
```

You can also ask `$skill-installer` to install from `https://github.com/jidekaixin2dian/handoff/tree/main/skills/handoff`, or copy the `skills/handoff` directory into a project or user `.agents/skills/` location. Inspect existing skills before overwriting them. See [OpenAI's skill documentation](https://learn.chatgpt.com/docs/build-skills) for discovery and invocation details.

## Triggers: intent first

`handoff` does not depend on a manual call. Any of these intents should make it run on its own instead of waiting for `$handoff`:

| Intent | What the user might say |
| --- | --- |
| New conversation / restart | “continue in a new window”, “context is too long, new chat”, “I'm closing this session” |
| Switch project | “park this, let's do the other project”, “switch to project X” |
| Light conversation | “just a quick question”, “no code, just asking” |
| Switch agent / hand over | “have another agent pick this up”, “hand it to a colleague” |
| Wrap up / leave | “that's it for today”, “pause here”, “pick it up next time” |
| Explicit | `handoff`, `$handoff`, handoff doc |

Review only, without editing files:

```text
$handoff Review the current handoff read-only: stale status, broken links, gaps. Do not change files.
```

## A useful handoff answers four questions

| Current state | Next action | Constraints | Evidence |
| --- | --- | --- | --- |
| Which version and findings are current? | What is unfinished or needs a human decision? | What must the successor preserve? | Where is the canonical material for this task? |

Keep historical instructions separate from current tasks. An offline check does not establish human acceptance, and an old release plan does not authorize a new publication.

## A handoff should not keep growing

Every handoff does two things by default:

- **Drop what is stale**: finished “next actions”, superseded versions, dead links, pasted logs become current facts — or one dated line plus a link under “History”.
- **Build an index**: past 150 lines, more than 8 open actions, or the same fact spread across files, `handoff.md` keeps only state / next action / constraints / index / history summary, with details linked in place.

See the before-and-after example in [docs/example.md](docs/example.md).

## Keep the boundaries

Preserve raw data, frozen evaluations, human ratings, hashes, unique decisions, and existing user changes, including untracked files. **Cleanup applies to the handoff document itself**; without an explicit request to slim the repository, no other files are touched, and a file being downloadable again does not establish that it can be removed safely.

## Demo

- [Introduction video](https://raw.githubusercontent.com/jidekaixin2dian/handoff/main/assets/handoff-intro.mp4): a 36-second demonstration of the project handoff workflow.
- [Video source ZIP](downloads/handoff-video-source.zip): the editable Remotion project, local fonts, and audio assets.
- [Video cover](assets/video-preview.jpg) · [Social card](assets/social-card.png) · [Workflow GIF](assets/workflow.gif).

## Feedback

For feedback, [open an issue](https://github.com/jidekaixin2dian/handoff/issues/new) with the request, observed behavior, and expected behavior. Remove credentials and private material before sharing.

[Skill source](skills/handoff/SKILL.md) · [MIT License](LICENSE) · jidekaixin2dian
