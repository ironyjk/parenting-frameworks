---
name: parenting
version: "1.2.0"
description: "Parenting & Education Framework Guide — Analyzes age, role (parent/teacher), and situation to auto-select the optimal combination from 16 parenting and education frameworks. Supports Positive Discipline, PET, CPS, Emotion Coaching, Triple P, Attachment Parenting, SDT, Retrieval Practice, Growth Mindset, UbD, PBL, Montessori, DAP, UDL, Formative Assessment, and Differentiated Instruction."
tools:
  - Read
  - Write
  - Edit
  - WebSearch
  - Skill
  - Agent
user-invocable: true
dependencies:
  - positive-discipline (Positive Discipline — Jane Nelsen)
  - pet (Parent Effectiveness Training — Thomas Gordon)
  - cps (Collaborative & Proactive Solutions — Ross Greene)
  - emotion-coaching (Emotion Coaching — John Gottman)
  - triple-p (Positive Parenting Program — Matthew Sanders)
  - attachment-parenting (Attachment-Based Parenting)
  - sdt-parenting (Self-Determination Theory Parenting — Deci & Ryan)
  - retrieval-practice (Retrieval Practice + Spaced Repetition)
  - growth-mindset (Growth Mindset — Carol Dweck)
  - ubd (Understanding by Design — Wiggins & McTighe)
  - pbl (Project-Based Learning)
  - montessori (Montessori Education)
  - dap (Developmentally Appropriate Practice — NAEYC)
  - udl (Universal Design for Learning — CAST)
  - formative-assessment (Formative Assessment)
  - differentiated-instruction (Differentiated Instruction — Carol Ann Tomlinson)
---

# Parenting — Education & Parenting Framework Meta-Router

> "A child is not a miniature adult, but an independent person at a unique stage of development."

Parenting is not a framework itself. It is an **intelligent routing layer** that sits above 16 education and parenting sub-skill frameworks. It analyzes the child's age, your role (parent/teacher/caregiver), and the specific situation to select the most appropriate framework(s), execute them in sequence, and deliver an integrated guide.

You do not need to know which framework to use. Just describe the situation.

> Background and theory: Read references/pipeline-examples.md, references/korean-cultural-layer.md, references/conflict-resolution.md, references/references.md

---

## Input Schema

```yaml
situation: "string"       # What is happening? (required)
age: "string"             # Child's age or age range (0-2, 3-5, 6-9, 10-12, 13-15, 16-18)
role: "string"            # Your role (parent / teacher / caregiver)
goal: "string"            # What outcome do you want?
child_traits: "string"    # Child characteristics (sensitive, active, introverted, special needs, etc.)
emotion_level: "string"   # Current emotional temperature (low / medium / high / crisis)
constraints: "string"     # Constraints (time, space, sibling dynamics, after-school schedule, etc.)
history: "string"         # Relevant history (first occurrence, recurring pattern, worsening trend, etc.)
```

Minimum input: `situation` alone is sufficient. The agent infers the rest.

---

## The 16 Frameworks — Quick Reference

| # | Framework | Core Idea | Best For |
|---|-----------|-----------|----------|
| 1 | **Positive Discipline** | Kind AND firm; belonging + capability | Daily discipline, problem behavior, family meetings |
| 2 | **PET** | I-messages, active listening, no-lose method | Parent-child communication, conflicts |
| 3 | **CPS** | "Kids do well if they can" — lagging skills | Chronic behavior, explosive children, ADHD/ASD |
| 4 | **Emotion Coaching** | 5-step emotional coaching | Emotional outbursts, regulation skills |
| 5 | **Triple P** | 5 levels of intervention | Systematic parenting plans, behavior prevention |
| 6 | **Attachment-Based** | Secure base, sensitive responsiveness | Infant attachment, separation anxiety |
| 7 | **SDT Parenting** | Autonomy, competence, relatedness | Intrinsic motivation, study conflicts |
| 8 | **Retrieval Practice** | Testing effect + spaced repetition | Study efficiency, exam prep |
| 9 | **Growth Mindset** | Ability grows through effort | Fear of failure, giving up |
| 10 | **UbD** | Backward design: goals -> evidence -> activities | Curriculum design, learning objectives |
| 11 | **PBL** | Real-world problem-solving projects | Inquiry learning, self-directed projects |
| 12 | **Montessori** | Prepared environment, self-paced | 0-6 environment setup, independence |
| 13 | **DAP** | Matched to developmental level | Early childhood, play-based learning |
| 14 | **UDL** | Multiple means of engagement/representation/action | Inclusive classrooms, diverse learners |
| 15 | **Formative Assessment** | Real-time checks -> immediate feedback | Comprehension checks, learning gaps |
| 16 | **Differentiated Instruction** | Differentiate content/process/product | Tiered instruction, mixed classrooms |

---

## Detection Matrix

| Signal in Situation | Primary | Secondary |
|--------------------|---------|-----------|
| "tantrum", "won't listen", "discipline", "behavior" | **Positive Discipline** | PET |
| "screaming", "meltdown", "can't control emotions" | **Emotion Coaching** | CPS |
| "fighting", "conflict", "sibling fight" | **PET** | Positive Discipline |
| "recurring problem behavior", "ADHD", "autism" | **CPS** | UDL |
| "anxiety", "separation anxiety", "attachment" | **Attachment-Based** | Emotion Coaching |
| "won't study", "no motivation", "forced" | **SDT Parenting** | Growth Mindset |
| "exam", "grades", "study methods", "cramming" | **Retrieval Practice** | Growth Mindset |
| "gives up", "I can't", "afraid of failure" | **Growth Mindset** | Emotion Coaching |
| "lesson design", "curriculum", "learning objectives" | **UbD** | Formative Assessment |
| "project learning", "inquiry", "self-directed" | **PBL** | UbD |
| "infant", "0-2 years", "environment setup" | **Montessori** | DAP |
| "toddler", "preschool", "play", "developmentally appropriate" | **DAP** | Montessori |
| "disability", "inclusive classroom", "wide learning gap" | **UDL** | Differentiated Instruction |
| "different levels", "mixed classroom" | **Differentiated Instruction** | UDL |
| "assessment", "feedback", "not sure if understood" | **Formative Assessment** | Differentiated Instruction |
| "overall parenting approach", "systematic" | **Triple P** | Positive Discipline |
| "puberty", "defiance", "communication breakdown" | **PET** | CPS |
| "smartphone", "gaming addiction", "screen time" | **Positive Discipline** | SDT Parenting |
| "homework battles", "after-school conflicts" | **SDT Parenting** | Retrieval Practice |
| "bullying", "school violence", "peer relationships" | **Emotion Coaching** | CPS |

**Korean-language signals:**

| Signal (Korean) | Primary | Secondary |
|--------------------|---------|-----------|
| "떼쓴다", "말 안 들어", "훈육" | **Positive Discipline** | PET |
| "소리 지른다", "폭발", "감정 조절 못해" | **Emotion Coaching** | CPS |
| "싸운다", "갈등", "형제 싸움" | **PET** | Positive Discipline |
| "공부 안 해", "학원 싫어", "동기 없어" | **SDT Parenting** | Growth Mindset |
| "사춘기", "반항", "대화 안 통해" | **PET** | CPS |
| "스마트폰", "게임 중독" | **Positive Discipline** | SDT Parenting |
| "따돌림", "학교폭력" | **Emotion Coaching** | CPS |

---

## Age-Based Routing

| Age Band | Available Frameworks | Primary Strategy | Not Effective |
|----------|---------------------|------------------|---------------|
| **0-2** | Attachment, Montessori, DAP | Secure attachment, environment design | PET, Retrieval Practice, Growth Mindset |
| **3-5** | Montessori, DAP, PD, Emotion Coaching, Attachment, Triple P | Label emotions, offer choices, play-based | — |
| **6-9** | All frameworks | Habit formation, Growth Mindset + Retrieval Practice | — |
| **10-12** | All frameworks | Increasing autonomy via SDT, PBL inquiry | — |
| **13-15** | SDT, PET, CPS, Growth Mindset emphasis | Active listening (PET), respect autonomy | PD "firm" risks relationship |
| **16-18** | SDT, PET, CPS, Growth Mindset, Retrieval Practice, PBL | Coaching/mentoring mode, maximize autonomy | Montessori, Triple P |

## Role-Based Routing

| Role | Core Pool | Focus |
|------|-----------|-------|
| **Parent** | PD, PET, CPS, Emotion Coaching, Triple P, Attachment, SDT, Growth Mindset | Relationship first |
| **Teacher** | UbD, PBL, Formative Assessment, DI, UDL, Growth Mindset, Retrieval Practice | Learning effectiveness |
| **Caregiver** | Attachment, DAP, Emotion Coaching, PD | Safety and emotional stability |

## Emotion Level Routing

| Level | Available | Action |
|-------|-----------|--------|
| **Crisis** | None — safety only | Secure safety -> professionals (1577-0199, 112, 1393) |
| **High** | Emotion Coaching, Active Listening | Accept emotions, wait 20+ min for calm |
| **Medium** | All frameworks | Execute situation-appropriate pipeline |
| **Low** | All frameworks (preventive emphasis) | Triple P environment, UbD design, SDT motivation, family meetings |

---

## Decision Flowchart

```
START → Child in danger? → YES → Safety + professionals
                         → NO  → Child in meltdown? → YES → Emotion Coaching (wait for calm)
                                                     → NO  → Role?
  Parent → Age? → 0-2: Attachment + Montessori
                → 3-5: Emotion Coaching + PD + DAP
                → 6-12: Situation routing (below)
                → 13-18: PET + SDT + CPS
  Teacher → UbD + Formative Assessment + DI
  Caregiver → Attachment + Emotion Coaching

  Parent + 6-12: Situation?
    Discipline → PD + CPS
    Learning → SDT + Growth Mindset + Retrieval Practice
    Emotional → Emotion Coaching + Attachment
    Social → PET + Emotion Coaching
    General → Triple P + SDT
    Unclear → Fallback Sequence
```

## Fallback Strategy — Universal Parenting Sequence

1. **Observe** (PD): Objective facts, no judgment
2. **Emotion** (Emotion Coaching): What is the child feeling? What am I feeling?
3. **Need** (SDT): Which basic need is unmet? (Autonomy? Competence? Relatedness?)
4. **Development** (DAP): Is this reasonable for this child's stage?
5. **Listen** (PET): Active listening for child's perspective
6. **Collaborate** (CPS): Find a solution together (Plan B)

---

## Execution Strategy

### Step 1: Listen and Classify
Parse the situation for: age, role, situation type, emotion level, recurring pattern.

### Step 2: Select Framework(s)
Combine Detection Matrix + Age Filter + Role Filter:
- PRIMARY: 1 framework (best fit)
- SECONDARY: 0-2 frameworks
- One-sentence rationale each

### Step 3: Execute
Invoke sub-skills. For **independent** frameworks (e.g., parallel analysis from different perspectives), use Agent for parallel execution. For **dependent** frameworks (e.g., Emotion Coaching THEN Positive Discipline), use Skill sequentially in pipeline order.

```
# Sequential (dependent pipeline)
Skill("emotion-coaching", args="[situation]")
# then after output:
Skill("positive-discipline", args="[situation + emotion coaching output]")

# Parallel (independent analysis)
Agent("cps", prompt="Analyze lagging skills for: [situation]")
Agent("pet", prompt="Determine problem ownership for: [situation]")
```

### Step 4: Synthesize
Integrate all outputs:
- **Integration:** Agreement and difference between frameworks
- **Priority:** Single most important insight
- **Action:** Max 3 specific next steps
- **Conversation script:** Natural language the user can actually say

---

## Sub-Commands

### `/parenting` — Full Situation Analysis and Routing

**Output format:**
```
Parenting & Education Strategy
================================

Situation Analysis:
  Type: [Discipline / Learning / Emotional / Relationship / Development / ...]
  Child Age: [X years]  |  Role: [Parent / Teacher / Caregiver]
  Emotion Level: [Low / Medium / High / Crisis]
  Core Need: [Autonomy / Competence / Relatedness / Safety / ...]

Framework Selection:
  Primary: [Framework] — [Reason]
  Secondary: [Framework] — [Reason]

Execution Pipeline:
  Phase 1 (Immediate): [Framework] — [What to do]
  Phase 2 (After stabilization): [Framework] — [How to talk]
  Phase 3 (Long-term): [Framework] — [What structure to build]

Conversation Script:
  Opening: "[Exact words]"
  Key phrases: [...]
  If child refuses/cries/escalates: "[Response]"

Cultural Considerations: [If applicable]
Risk Factors: [Risk → Mitigation]
Follow-Up: [What to do after]
```

### `/parenting:select` — Quick Framework Selection
Returns top 3 frameworks with fit percentage and one-line rationale.

### `/parenting:age` — Age-Based Guide
Comprehensive guide for a specific age: developmental characteristics, applicable frameworks, common mistakes, cultural context.

---

## Rules

1. **Emotions first, behavior second** — Always
2. **Relationship over discipline** — When in doubt, choose connection
3. **Developmental level determines expectations** — DAP overrides all
4. **Autonomy outlasts control** — SDT > Triple P (except safety)
5. **"Can't" before "won't"** — CPS lagging skills > PD mistaken goals
6. **Korean context matters** — See references/korean-cultural-layer.md
7. **No framework is universal** — Age, role, and emotion level constrain the pool
