# No AI slop

This open-source skill removes 20+ patterns of AI slop from your writing without flattening your personal voice. It can also detect slop without guessing whether AI wrote the text.

## What it catches

The patterns it detects include:

| Pattern | Smells like |
|---------|-------------|
| Binary contrasts | "It's not X. It's Y." |
| Throat-clearing openers | "Here's the thing..." |
| Faux-insight setups | "What nobody tells you..." |
| Colon reveals | "The best part: it learns." |
| Superficial analysis | "...highlighting the team's commitment" |
| Importance puffery | "marks a pivotal moment" |
| Weasel attribution | "experts agree," "studies show" |
| Fake-strong verbs | "serves as a centralized hub" |
| Synonym cycling | the agent, then the assistant, then the tool |
| Negative listing | "Not a X. Not a Y. A Z." |
| Dramatic fragmentation | "That's it. That's the whole thing." |
| Punch sentences | "Nothing was lost." |

It also enforces the fundamentals that make writing good: Lead with the point when it helps, use active voice, untangle hard-to-follow sentences, and prefer concrete numbers over abstractions.

This is yunyu's fork of [petergyang/no-ai-slop](https://github.com/petergyang/no-ai-slop). It adds the punch-sentences pattern.

## Install

List the skill available from this repository:

```sh
npx skills add yunyu/no-ai-slop --list
```

Install it globally with the [Vercel Skills CLI](https://github.com/vercel-labs/skills):

```sh
npx skills add yunyu/no-ai-slop --skill no-ai-slop --global --yes
```

Confirm that it is installed:

```sh
npx skills list --global
```

Update the installed skill later:

```sh
npx skills update no-ai-slop --global --yes
```

The repository also contains a skills-only plugin package for ChatGPT and Codex. Tagged releases attach a validated plugin ZIP, and the plugin is available in the public ChatGPT directory.

## Use

**1. Edit a draft.** Paste it and invoke the skill:

```
/no-ai-slop

[your draft]
```

You get back the edited draft plus a short What changed section. The skill makes the minimum effective edit, then checks its own work against [eval.md](skills/no-ai-slop/eval.md).

**2. Detect slop.** Ask whether a piece reads as AI:

```
/no-ai-slop is this AI slop?

[the text]
```

You get every pattern it found each with the quoted line.

## Files

1. `skills/no-ai-slop/SKILL.md`: The editing rules and workflow.
2. `skills/no-ai-slop/eval.md`: Pass/fail checks the skill runs on its own edits.
3. `.codex-plugin/plugin.json`: Metadata for the ChatGPT and Codex plugin.
4. `scripts/build_plugin.py`: Builds and validates the plugin ZIP from the canonical skill files.

## Who made this

This is one skill from my personal AI operating system. The full library, including my courses and workflows, lives at [Behind the Craft](https://behindthecraft.com).

## License

MIT
