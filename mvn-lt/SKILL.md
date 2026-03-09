---
name: maven-low-token
description: Use when running Maven tests or verification commands and you want minimal output tokens with actionable failure summaries. Runs `mvn-lt`, which captures the full Maven log, parses Surefire/Failsafe XML reports, and prints a compact pass/fail summary with report paths and relevant log line numbers.
---

# Maven Low Token

Run `mvn-lt <maven args>`.

While `mvn-lt` is running, do not emit intermediary commentary unless the user explicitly asked for progress updates.

If `mvn-lt` is missing, link it and rerun:

```bash
ln -sf ~/.codex/skills/mvn-lt/scripts/mvn-lt ~/.local/bin/mvn-lt
```
