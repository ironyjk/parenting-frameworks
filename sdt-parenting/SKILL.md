---
name: sdt-parenting
version: "1.1.0"
description: "SDT Parenting (Deci & Ryan) — Support children's autonomy, competence, and relatedness. Autonomy-supportive vs. controlling parenting. Why rewards can backfire."
user-invocable: false
tools:
  - Read
  - Write
---

# SDT Parenting (Self-Determination Theory) Skill

> "The more we try to control people, the more we undermine the very motivation we are trying to promote." — Edward Deci

> Background and theory: Read references/foundation.md

## Sub-commands

| Command | Description |
|---------|-------------|
| `/sdt` | Full SDT analysis of a parenting situation |
| `/sdt:needs` | Assess which basic needs are supported or thwarted |
| `/sdt:language` | Reframe controlling language into autonomy-supportive language |
| `/sdt:motivation` | Analyze motivation type and suggest support strategies |

---

## Autonomy-Supportive Parenting: Four Elements

### 1. Acknowledge the Child's Perspective

| Controlling | Autonomy-Supportive |
|---|---|
| "Stop playing and do homework." | "I can see you're really into this game right now. It's hard to stop when you're having fun." |
| "Eat your vegetables." | "I know broccoli isn't your favorite." |
| "Stop complaining about practice." | "It sounds like practice was really tiring today." |

### 2. Provide Meaningful Rationale

| Controlling | Autonomy-Supportive |
|---|---|
| "Because I said so." | "Brushing your teeth protects them from cavities, which really hurt." |
| "You have to share." | "When you share, your friends feel included, and that makes them want to play with you more." |
| "No phone at dinner." | "Dinner is the one time we all get to hear about each other's day." |

### 3. Offer Choices Within Limits

| Controlling | Autonomy-Supportive |
|---|---|
| "Do your homework at 4:00." | "Homework needs to be done before dinner. Would you like to start at 4 or 5?" |
| "Wear your coat." | "It's cold today. Would you prefer your jacket or your hoodie?" |
| "Practice piano for 30 minutes." | "You need to practice today. Do you want to do it before or after snack?" |

### 4. Minimize Pressure and Control

| Controlling language | Autonomy-supportive language |
|---|---|
| "You need to..." | "It would help if..." |
| "You should..." | "You might consider..." |
| "You have to..." | "What do you think about..." |
| "I want you to..." | "Would you be willing to..." |

---

## Application to Common Challenges

### Homework
```
Parent: "I noticed you've been putting off your math. What's going on?"
Child:  "It's boring and hard."
Parent: "That's tough — boring AND hard is the worst combination. 
         [ACKNOWLEDGE] The reason your teacher assigns it is to practice 
         what you learned, so it sticks. [RATIONALE] Would you rather 
         start with the easy problems or tackle the hard ones first? 
         [CHOICE] And would you like the desk or the kitchen table? [CHOICE]"
```

### Screen Time
```
Parent: "Hey, you've been on for a while. I know it's hard to stop 
         when you're having fun. [ACKNOWLEDGE] We agreed on 45 minutes 
         because your brain needs other kinds of activity too. [RATIONALE]
         Would you like to stop now, or do you need 5 minutes to get to 
         a stopping point? [CHOICE]"
```

### Chores
```
Parent: "Our house works because everyone pitches in. [RATIONALE] 
         Here's the list. Which tasks would you like to claim? 
         [CHOICE + COMPETENCE] When do you want to get them done — 
         Saturday morning or Sunday? [CHOICE]"
```

### Eating
```
Parent: "Your body needs different types of food to grow strong and have 
         energy for soccer. [RATIONALE] You don't have to eat anything 
         you don't want to, but the rule is you try one bite of everything 
         new. [STRUCTURE + AUTONOMY]"
```

### What to Do Instead of Rewards

| Situation | Reward approach (problematic) | SDT approach |
|---|---|---|
| Won't do homework | "Finish homework = screen time" | Acknowledge difficulty, provide rationale, offer choices |
| Won't practice instrument | "$1 per practice session" | Connect to their goals, offer autonomy in what to practice |
| Won't do chores | Sticker chart | Frame as family contribution, give meaningful role |

---

## Anti-patterns

1. **Confusing autonomy with permissiveness** — autonomy-supportive parenting includes STRUCTURE
2. **Using rewards "just this once"** — intermittent rewards are even more controlling
3. **Providing rationale as a lecture** — keep it brief, one or two sentences
4. **Offering fake choices** — "Do you want to do homework now or now?" is not a choice
5. **Conditional love disguised as encouragement** — "I'm so proud of you for getting an A"
6. **Autonomy-supportive language with controlling intent** — questions that aren't real questions
7. **Ignoring competence needs** — giving choices but no scaffolding
8. **Over-praising outcomes** — "You're so smart!" creates fragile motivation
9. **Withdrawing relatedness as punishment** — silent treatment delivered punitively

---

## Output Format

```
## SDT Parenting Analysis

**Situation:** [brief description]

### Basic Needs Assessment
- **Autonomy:** [supported / thwarted — how]
- **Competence:** [supported / thwarted — how]
- **Relatedness:** [supported / thwarted — how]

### Motivation Type
- **Current motivation:** [external regulation / introjected / identified / intrinsic]
- **Goal:** [move toward identified or intrinsic motivation]

### Autonomy-Supportive Reframe
1. **Acknowledge perspective:** [specific statement]
2. **Provide rationale:** [brief, genuine reason]
3. **Offer choices:** [real choices within limits]
4. **Minimize pressure:** [reframed language]

### Example Dialogue Script
[Parent-child dialogue demonstrating SDT approach]

### Watch For
[Specific controlling patterns to avoid in this situation]
```
