---
name: triple-p
version: "1.1.0"
description: "Triple P Positive Parenting Program (Matthew Sanders) — Evidence-based 5-level system from universal prevention to intensive family intervention. Self-regulation framework for parents and children."
user-invocable: false
tools:
  - Read
  - Write
---

# Triple P Positive Parenting Program Skill

> "Good parenting is not about being perfect. It's about being good enough — and knowing what to do when things go wrong." — Matthew Sanders

> Background and theory: Read references/foundation.md

## Sub-commands

| Command | Description |
|---------|-------------|
| `/triple-p` | Full Triple P analysis of a parenting situation |
| `/triple-p:level` | Determine appropriate intervention level (1-5) |
| `/triple-p:strategies` | Suggest specific Triple P strategies for a behavior |
| `/triple-p:self-reg` | Parent self-regulation assessment and guidance |

---

## Key Strategies

### Descriptive Praise

The most powerful tool. Specific, immediate feedback on behavior you want to see more of.

| Generic praise | Descriptive praise |
|---|---|
| "Good job!" | "You put all the blocks back without being asked. That's really helpful." |
| "Well done." | "You waited patiently while I was on the phone. That took self-control." |
| "Good boy." | "You used your words to tell your sister how you felt instead of hitting." |

**Rules:** Be immediate, be specific, be genuine. Aim for 6:1 positive-to-correction ratio.

### Planned Activities

Prevent misbehavior by planning ahead for high-risk situations:

1. **Identify** the high-risk situation (shopping, restaurants, visitors)
2. **Plan ahead** — discuss rules, prepare activities
3. **Brief the child** — tell them what will happen and what you expect
4. **Engage** — give them a role during the activity
5. **Debrief** — praise what went well afterward

```
Parent: "We're going to the store. Remember our three rules?"
Child:  "Stay close, hands to myself, use inside voice."
Parent: "Right. And what's your job?"
Child:  "Find the apples and the bread!"
```

### Assertive Discipline (Graduated Response)

1. Descriptive praise (reinforce desired behavior)
2. Clear ground rules (few, fair, enforceable)
3. Directed discussion (brief explanation)
4. Planned ignoring (minor misbehavior)
5. Clear, calm instructions (state what TO do)
6. Logical consequences (related, reasonable, respectful)
7. Quiet time (brief removal from reinforcing situation)
8. Time-out (last resort, serious misbehavior only)

### Quiet Time and Time-Out

**Time-out rules:**
- Maximum: 1 minute per year of age
- Calm voice: "You hit your sister. Time-out." (no lecture)
- Timer starts when calm
- Afterward: brief reconnection, no lengthy discussion, clean slate
- NEVER use a dark, scary, or locked space

```
Parent: [calm] "You hit your brother. That's time-out."
         [guides to spot, sets timer]
         "When the timer goes, you can come back and play."
         [after] "Time-out is over. Ready to play without hitting?"
```

### Behavior Charts

- Maximum 3 behaviors at a time
- Specific and observable
- Child participates in creating
- Phase out once behavior is established (fade the chart)

---

## Anti-patterns

1. **Jumping to time-out** — last tool, not first; exhaust positive strategies
2. **Vague praise** — "Good job" teaches nothing
3. **Inconsistency** — applying rules sometimes but not others
4. **Emotional time-out** — using it while angry turns it into punishment
5. **Too many rules** — 3-5 clear rules beat 20 vague ones
6. **Ignoring parent self-care** — burned-out parents cannot sustain strategies
7. **Expecting immediate results** — behavior change takes 2-4 weeks
8. **Using behavior charts forever** — training wheels, not permanent fixtures
9. **Skipping planned activities** — prevention is easier than intervention

---

## Output Format

```
## Triple P Analysis

**Situation:** [brief description]

### Intervention Level
- **Suggested level:** [1-5 with rationale]

### Relevant Principles
- [Which of the 5 core principles apply]

### Recommended Strategies
1. **Prevention:** [planned activities or environmental changes]
2. **Encouragement:** [specific descriptive praise opportunities]
3. **Management:** [graduated response if needed]

### Example Dialogue Script
[Parent-child dialogue demonstrating the strategies]

### Parent Self-Regulation Check
- **Stress level:** [assessment]
- **Self-care recommendation:** [if applicable]
```
