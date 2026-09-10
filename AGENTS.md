# Learn system instructions

Use `skills/teach/SKILL.md` for all teaching and explanation requests.
Use `skills/visualize/SKILL.md` when a visual genuinely improves the explanation.

The canonical role prompts live in `agents/`. Provider-specific files in
`.github/`, `.agents/`, and `.claude/` are adapters that point back to those
shared prompts. Do not assume Pi APIs, Pi extensions, or Pi-specific tools are
available.

When delegation is supported, use these roles:

- `researcher` for fact verification and focused web research
- `mermaid-maker` for structural diagrams
- `svg-maker` for spatial or geometric diagrams

If the current provider cannot delegate an agent or render a visual, continue
the teaching session without that optional capability rather than inventing
research or an unverified image.

## Markdown session logging

To link a session, say:

> Link this session to `path/to/note.md`

The target must already exist and must be a file. Resolve relative paths from
the workspace root; do not create a file or parent directory because of a
typo. Once linked, mirror future user and assistant messages into that file
using these Obsidian callouts:

```markdown
> [!quote] YOU
>
> User message

> [!abstract] ASSISTANT
>
> Assistant response
```

Keep the log append-only. Do not include hidden instructions, tool chatter,
credentials, or internal reasoning. To stop logging, say:

> Unlink this session

Because Copilot, Codex, and Claude Code do not expose one shared message-event
API, this protocol is provider-neutral rather than a guaranteed automatic
background hook. When the provider supports session hooks, use them to
automate the same behavior; otherwise append the blocks as part of each turn.
