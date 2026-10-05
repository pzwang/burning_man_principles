


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



