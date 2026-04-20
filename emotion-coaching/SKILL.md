---
name: emotion-coaching
version: "1.1.0"
description: "Emotion Coaching (John Gottman) — Raise emotionally intelligent children through 5 steps: awareness, connection, empathic listening, naming emotions, and problem-solving with limits"
user-invocable: false
tools:
  - Read
  - Write
---

# Emotion Coaching Skill

> "Even more than IQ, your emotional awareness and ability to handle feelings will determine your success and happiness in all walks of life." — John Gottman

> Background and theory: Read references/foundation.md

## Sub-commands

| Command | Description |
|---------|-------------|
| `/emotion-coaching` | Full Emotion Coaching analysis of a situation |
| `/emotion-coaching:style` | Identify your current parenting style for a scenario |
| `/emotion-coaching:steps` | Walk through the 5-step process for a specific incident |
| `/emotion-coaching:vocab` | Age-appropriate emotion vocabulary expansion |

---

## The Five Steps of Emotion Coaching

### Step 1: Be Aware of the Child's Emotion
Notice emotions BEFORE they escalate. Tune in to facial expressions, body language, tone, context. Catch frustration before meltdown.

### Step 2: Recognize as Opportunity for Connection
**Reframe:** "Here we go with another tantrum" -> "This is a chance to help him learn."

### Step 3: Listen Empathically and Validate
Get on their level. Reflect what you hear. Validate: "That makes sense."
Do NOT advise, fix, minimize, lecture, or redirect (yet).

```
Child:  [slams backpack] "I HATE art class."
Parent: [sits next to child] "Something happened in art class that 
         really upset you."
Child:  "Mrs. Kim said my painting wasn't finished!"
Parent: "You felt like you'd done your best and she didn't see that. 
         That's really frustrating."
Child:  [softens] "Yeah."
```

### Step 4: Help Name the Emotion
Naming activates the prefrontal cortex and calms the limbic system. Offer, don't impose: "Could it be that you're feeling [X]?" Accept corrections.

Name mixed emotions: "You're excited about the trip AND nervous about being away from home. Both can be true."

### Step 5: Set Limits and Help Problem-Solve
AFTER steps 1-4: validate feeling, set limit on behavior, help identify alternatives.

```
Parent: "I can see you're really angry at your brother. You have every 
         right to be angry — he broke your model. Being angry is okay. 
         AND hitting is not okay."
Child:  "But he BROKE it!"
Parent: "He did. When you're this angry, what could you do INSTEAD 
         of hitting?"
Child:  "I don't know."
Parent: "Some kids stomp their feet, squeeze a pillow, or come tell 
         a grown-up. Which might work for you?"
```

---

## Full Example: Tantrum at Store (Age 5)

```
[Step 1: Awareness — parent notices rising distress]
[Step 2: Opportunity — "She needs help, not punishment."]

[Step 3: Empathic Listening]
Parent: [crouches] "You really, really wanted that toy."
Child:  "I WANT IT! YOU NEVER BUY ME ANYTHING!"
Parent: "It feels like I say no a lot."

[Step 4: Name the Emotion]
Parent: "You're disappointed. And maybe a little angry at me."
Child:  [still crying but volume decreases] "Yes..."
Parent: "Disappointment is a hard feeling. It's okay to be disappointed."

[Step 5: Limits + Problem-Solve]
Parent: "It's okay to feel disappointed. AND screaming in the store 
         isn't something we do. Would you like to put it on your 
         birthday list?"
Child:  [sniffling] "Birthday list."
Parent: "Let's write it down right now."
```

---

## Anti-patterns

1. **Skipping to Step 5** — "I know you're upset BUT here's what you should do"
2. **Coaching as a technique to stop crying** — the goal is connection, not silence
3. **Naming emotions incorrectly and insisting** — accept corrections
4. **Coaching during a full meltdown** — prefrontal cortex is offline; wait
5. **No limits (Laissez-Faire trap)** — validating without addressing behavior
6. **Only for negative emotions** — coach positive emotions too: "You look so proud!"
7. **Expecting immediate calm** — reduces intensity over TIME, not instantly

---

## Output Format

```
## Emotion Coaching Analysis

**Situation:** [brief description]

### Current Style Assessment
- **Observed style:** [dismissing / disapproving / laissez-faire / emotion coaching]
- **Typical response pattern:** [what the parent is likely doing now]

### 5-Step Emotion Coaching Response

**Step 1 — Awareness:** [what to notice]
**Step 2 — Opportunity:** [reframe]
**Step 3 — Empathic Listening:** [specific reflective statements]
**Step 4 — Name the Emotion:** [age-appropriate label]
**Step 5 — Limits + Problem-Solve:** [validate, limit, alternatives]

### Example Dialogue Script
[Full parent-child dialogue demonstrating all 5 steps]

### Emotion Vocabulary Expansion
[2-3 emotion words to introduce for this developmental stage]
```
