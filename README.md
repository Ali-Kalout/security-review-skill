# security-review-skill

A starter AI security review skill: one markdown file with your rules, the bugs you've had before, and a short method. From the talk "AI-Powered Security: Hunting Vulnerabilities Before Attackers Do" at DevFest Beirut 2026.

## Use it

1. Copy `skills/security-review/SKILL.md` into your repo at `.claude/skills/security-review/SKILL.md` (or wherever your agent reads skills from).
2. Replace the example rules and past bugs with your own:
   - List your top 5 past security bugs.
   - Turn user stories into "must never" rules, e.g. "A user can view their invoice" becomes "A user must never view another user's invoice."
3. Run it on every change:
   - Every PR: review the diff (git hook or CI). Keep it advisory at first.
   - Every release: run a full audit.
   - Every bug it misses becomes a new rule.

## How it works

Map the change, hunt for code that breaks a rule, try to disprove each finding, and report only what survives, with a repro.
