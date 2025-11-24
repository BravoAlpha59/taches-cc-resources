---
description: Invoke create-plans skill for project planning
argument-hint: [project description or leave blank for context-aware routing]
---

Invoke the create-plans skill to start or continue project planning:

```
Skill("create-plans")
```

The skill will:
1. Scan context to detect existing planning state
2. Route to appropriate workflow (create brief, roadmap, phase plan, execute, etc.)
3. Load domain expertise if applicable
4. Guide you through the planning process

**What create-plans does:**
- Creates hierarchical plans (BRIEF.md → ROADMAP.md → phases/PLAN.md)
- Loads domain expertise from ~/.claude/skills/expertise/
- Splits large phases into atomic plans (2-3 tasks each)
- Manages checkpoints for human verification/decisions
- Handles deviations with embedded auto-correction rules
- Commits planning artifacts and code after each plan execution
- Manages milestones for v1.0 → v1.1 iteration

**After planning:**
Use `/run-plan <path-to-PLAN.md>` to execute the next phase plan.
