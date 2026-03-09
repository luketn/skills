---
name: maven-low-token
description: Use when running Maven tests or verification commands and you want minimal output tokens with actionable failure summaries. Runs `mvn-lt`, which captures the full Maven log, parses Surefire/Failsafe XML reports, and prints a compact pass/fail summary with report paths and relevant log line numbers.
---

# Maven Low Token

Use this skill for Maven test commands when the raw console output would be noisy.

## Workflow

1. Run `mvn-lt <maven args>` from the project root.
2. Assume `mvn-lt` is already on `PATH`.
3. If the shell reports `mvn-lt: command not found`, link the bundled script and rerun:

```bash
ln -sf ~/.codex/skills/mvn-lt/scripts/mvn-lt ~/.local/bin/mvn-lt
```

## Output contract

- Full Maven stdout/stderr goes to `target/codex-logs/maven-*.log`.
- Success output stays compact: status, test counts, duration, log path.
- Failure output prefers structured data from `target/surefire-reports` and `target/failsafe-reports`.
- For failing tests, use the testcase `system-out` from JUnit XML and map matching lines back into the saved Maven log when possible.
- If Maven fails before test reports exist, fall back to a small set of relevant log lines from the saved log.

## Notes

- `mvn-lt` is Maven-specific on purpose. It assumes Surefire/Failsafe report layout.
- The script uses only the Python standard library.
