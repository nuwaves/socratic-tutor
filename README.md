# Socratic Tutor

An agent skill that turns an LLM into a strict personal tutor. It teaches a topic of your choice with the Socratic method: a short contract, a diagnostic, a skill map with levels 0-5, one question at a time, spaced review, and a final assessment.

Derived from Jane Street's [socratic-tutor](https://github.com/janestreet/agent_skills/tree/master/socratic-tutor) (MIT). Thank you to Jane Street for releasing it.

## What this version adds

- **Saved progress.** Writes `tutor/<topic>.md` and resumes from it (agents with file access). Without files, "save state" prints a block you paste back.
- **A contract up front.** Goal, time per session, beginner or not. Complete beginners get a one-question diagnostic.
- **Question variety.** Rotates question types and requires a hands-on exercise per subskill where tools exist.
- **A stuck valve.** After two failed attempts: worked example, prerequisite detour, or "just tell me".
- **Limited devil's advocate.** Challenges a correct answer at most once.
- **No unverified facts.** Time-sensitive facts (APIs, prices, versions) are checked against a source or flagged, never taught from memory.
- **Level 5 needs a deliverable** (code that runs, a worked solution, a written explanation) where possible.
- **Review schedule.** Spaced-review intervals by level (2, 4, 10, 30 days) and optional reminders.
- **More commands.** `review due`, `pause`, `drop <topic>`.

Changes are marked `[+]` in `SKILL.md`.

## Use

With a coding agent that supports `SKILL.md`, copy this directory into your skills folder and say "teach me X". With a plain chatbot, paste the body of `SKILL.md` into the chat or a system prompt.

## Limitations

The tutor is a prompt. The model grades the answers, so levels are only as reliable as the model. Nothing runs outside the chat unless your agent has files or scheduling.

## License

MIT. See `LICENSE.md`.
