# Skills

Public repository for reusable Codex skills.

Codex skill discovery uses each skill's `SKILL.md` metadata. This repository-level `README.md` is for humans and does not change skill triggering.

| Skill | What it does | Benefit |
| --- | --- | --- |
| [`mvn-lt`](./mvn-lt/) | Runs Maven with low terminal output, saves the full log, and summarizes failures from Surefire/Failsafe reports. | Cuts noisy test output while keeping actionable failure details and log/report paths. |

## Example

- Plain `mvn test`: 27,094 tool-output tokens
- `mvn-lt test`: 509 tool-output tokens
- Reduction: about 98.1%
