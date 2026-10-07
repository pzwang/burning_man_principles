


## Inline directives (user -> agent)
A directive starts with `@@` and runs to the end of the line. It applies to the line or bullet it sits on. If it is on a line of its own, it applies to the paragraph or section just above it.

```
@@ verify this figure             -> any agent
@@c expand with MAS guidance      -> Claude only
@@g counter-argue this            -> GPT only
```

Family codes: `c` or `claude` Claude, `g` or `gpt` GPT, `k` or `kimi` Kimi, `d` DeepSeek. No code means any agent. To place a directive mid-sentence, wrap it in brackets: `...grew 83% [@@ source?] in 2026`. HTML-comment form (`<!-- @claude: ... -->`) is also accepted.

When asked to "process directives" (or "process comments"):
1. Handle only the directives addressed to your family, or to any agent, in files you own. Leave directives for other families untouched.
2. Make the edit, then delete the directive. If you can't resolve it, replace it with `@@user <short reply>`.
3. Summarize your changes in chat, one line per directive.

Find open directives with: `grep -rn "@@" .`

## Agent log
Append an entry to `agent.log` at the end of any session that changes project files. Newest entries go at the bottom. Use the format described at the top of that file: date, agent family and model, a one-line summary, files touched, and open threads for the next agent. Keep entries to a synopsis; the files and git history hold the detail.

## Peer projects
Some sources live in sibling repositories that agents can read locally but readers see on GitHub:

| Project | Published (use in links) | Local copy (read from) |
| --- | --- | --- |
| The Unmoored Self | https://github.com/pzwang/unmoored-self | `../unmoored_self/` |

- In project files, always link the published URL, never the local path. For a file use `https://github.com/pzwang/unmoored-self/blob/main/<path>`.
- Read the local copy for content. It may hold uncommitted or unpushed work, so before linking or quoting a file, check that it is published: `git -C ../unmoored_self ls-tree -r --name-only origin/main | grep <path>`.
- Peer repositories are read-only. Record proposed changes in this project (e.g. `research/UPDATES-TO-UNMOORED-SELF.md`).

## File headers
Don't add dated "Status" lines to documents; git history records dates. A one-line italic note is fine when it changes how a reader should take the text (e.g. unverified quotations, fictional material, not policy).



