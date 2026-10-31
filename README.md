# lovkart-skills

Claude skills for Norwegian legal work, built around [Lovkart](http://lovkart.no/), plus two builder skills that turn a skill or an idea into a tool your team can use together.

## Skills

| Skill | What it does |
| --- | --- |
| [`builders/skill-to-page-and-chat`](builders/skill-to-page-and-chat/SKILL.md) | Turns a skill you already have into a team tool: an artifact page for people, a Claude chat for the work. |
| [`builders/prompt-to-page-and-chat`](builders/prompt-to-page-and-chat/SKILL.md) | Does the same from a plain description, when there is no skill to start from. It writes the method first. |

More skills for Norwegian law will follow in `norwegian-law/`.

## How the tools work

The tools follow the same design as Anthropic's legal artifacts:

- **The page is for people.** You add files, make choices, press a button, follow the results and record decisions.
- **The work runs in a normal Claude chat.** Claude reads, researches with your connectors and writes each result back as it goes.
- **A shared database connects the two.** Close the page and nothing is lost. The chat keeps working, and the page shows the results when you come back.

In short: the skill is the method, the artifact is the workplace.

Both builder skills also create a companion "run" skill. It tells any Claude chat what to do when a request arrives from the page.

## Install

**Claude (web or desktop):** zip a skill's folder, then upload it in **Customize > Skills**.

**Claude Code:** copy a skill's folder to `~/.claude/skills/`.

Then use it, for example:

```
/skill-to-page-and-chat contract-change-review
/prompt-to-page-and-chat a board where we drop supplier contracts and see which expire soon
```

## Using a tool with your team

- Teammates who press **Run** need the run skill and the original skill. On Team and Enterprise plans, share them from **Customize > Skills**. Updates reach everyone automatically.
- Teammates who only view the board or record decisions don't need any skill.
- The documents' text is stored in the artifact's database on Claude's side. Think carefully about what you are willing to store and share.
- Check a new run skill against the original before relying on it. In our tests, some instructions got lost on the way. The builder skills now include a test that compares the two.

## Norwegian law

For Norwegian law, connect [Lovkart](http://lovkart.no/). It is an MCP server with Norwegian laws, regulations, Supreme Court decisions and preparatory works, and it shows how they link together.

## Disclaimer

Output from these skills is a draft for review by a lawyer. It is not legal advice.

## License

[Apache 2.0](LICENSE)
