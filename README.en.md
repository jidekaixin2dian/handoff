[![handoff: keep the project moving between conversations](assets/video-preview.jpg)](https://raw.githubusercontent.com/jidekaixin2dian/handoff/main/assets/handoff-intro.mp4)

[中文](README.md) · [Quick start](#start-with-codex) · [Example](docs/example.md) · [Media](#media)

# handoff

**A new conversation. The same project, moving forward.**

Starting a new conversation during a long AI-assisted task often means explaining the project again: which version is current, what is finished, and what comes next?

`handoff` is a lightweight project handoff skill. It verifies the workspace state, prepares a concise current entry point, and links to the evidence needed for the next task. Help the next person or agent pick up where the project stands. Instruction-only, MIT licensed, with no extra service to deploy.

[Watch / download the 36-second introduction](https://raw.githubusercontent.com/jidekaixin2dian/handoff/main/assets/handoff-intro.mp4)

## Start with Codex

Install into the current project using the [skills CLI](https://github.com/vercel-labs/skills):

```bash
npx skills add jidekaixin2dian/handoff --skill handoff --agent codex
```

Then invoke it in a Codex environment that supports `$skill-name`:

```text
$handoff I want to continue this project in a new conversation.
Verify its current state, refresh the handoff entry point,
and preserve the evidence, constraints, and next action.
```

You can also ask `$skill-installer` to install from `https://github.com/jidekaixin2dian/handoff/tree/main/skills/handoff`, or copy the `skills/handoff` directory into a project or user `.agents/skills/` location. Inspect existing skills before overwriting them. See [OpenAI's skill documentation](https://learn.chatgpt.com/docs/build-skills) for discovery and invocation details.

## A useful handoff answers four questions

| Current state | Next action | Constraints | Evidence |
| --- | --- | --- | --- |
| Which version and findings are current? | What is unfinished or needs a human decision? | What must the successor preserve? | Where is the canonical material for this task? |

Keep historical instructions separate from current tasks. An offline check does not establish human acceptance, and an old release plan does not authorize a new publication.

## See the workflow

![Illustrated handoff flow](assets/workflow.gif)

[See the before-and-after example](docs/example.md).

## Keep the boundaries

Preserve raw data, frozen evaluations, human ratings, hashes, unique decisions, and existing user changes, including untracked files. Only consider repository cleanup when requested; a file being downloadable again does not establish that it can be removed safely.

## Media

- [Introduction video](https://raw.githubusercontent.com/jidekaixin2dian/handoff/main/assets/handoff-intro.mp4): 36 seconds, 1080p, 30 fps, with serif titles and an original electric-piano score.
- [Video source ZIP](downloads/handoff-video-source.zip): the editable Remotion project, local fonts, and audio assets.
- [Chinese launch copy](docs/launch.md): titles and descriptions for Douyin and Bilibili, plus a Juejin article.
- [Video cover](assets/video-preview.jpg) · [Social card](assets/social-card.png) · [Workflow GIF](assets/workflow.gif).

## Evidence and feedback

Validation includes format checks, static review of twelve scenarios, one manual isolated file exercise, and public installation checks. See [the validation notes](docs/validation.md) for evidence and limits. Cross-model behavior and token savings have not been measured. The package follows `SKILL.md` conventions; behavior in other clients has not been individually tested.

For feedback, [open an issue](https://github.com/jidekaixin2dian/handoff/issues/new) with the request, observed behavior, and expected behavior. Remove credentials and private material before sharing.

[Skill source](skills/handoff/SKILL.md) · [MIT License](LICENSE) · jidekaixin2dian
