---
name: parenting
version: "1.1.0"
description: "Parenting & Education Framework Guide — Analyzes age, role (parent/teacher), and situation to auto-select the optimal combination from 16 parenting and education frameworks. Supports Positive Discipline, PET, CPS, Emotion Coaching, Triple P, Attachment Parenting, SDT, Retrieval Practice, Growth Mindset, UbD, PBL, Montessori, DAP, UDL, Formative Assessment, and Differentiated Instruction."
tools:
  - Read
  - Write
  - Edit
  - WebSearch
  - Skill
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

## What This Is

Parenting is not a framework itself. It is an **intelligent routing layer** that sits above 16 education and parenting sub-skill frameworks. It analyzes the child's age, your role (parent/teacher/caregiver), and the specific situation to select the most appropriate framework(s), execute them in sequence, and deliver an integrated guide.

You do not need to know which framework to use. Just describe the situation.

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

### Behavioral/Discipline (Parent-Child Behavior & Discipline)

| # | Framework | Core Idea | Best For |
|---|-----------|-----------|----------|
| 1 | **Positive Discipline** | Build belonging + capability without punishment; kind yet firm | Daily discipline, problem behavior, family meetings |
| 2 | **PET** | I-messages, active listening, no-lose conflict resolution | Parent-child communication, conflicts, problem ownership |
| 3 | **CPS** | "Kids do well if they can" — explore unsolved problems | Chronic problem behavior, explosive children, ADHD/ASD |
| 4 | **Emotion Coaching** | Acknowledge and label emotions; 5-step coaching | Emotional outbursts, emotional development, regulation skills |

### Parent Coaching (Parenting Strategies)

| # | Framework | Core Idea | Best For |
|---|-----------|-----------|----------|
| 5 | **Triple P** | 5 levels of intervention (universal to intensive); evidence-based | Systematic parenting plans, behavior prevention, parental stress |
| 6 | **Attachment-Based Parenting** | Secure base formation, sensitive responsiveness, exploration support | Infant attachment, separation anxiety, emotional security |
| 7 | **SDT Parenting** | Fulfill 3 basic needs: autonomy, competence, relatedness | Intrinsic motivation, self-direction, study/after-school conflicts |

### Learning/Cognitive

| # | Framework | Core Idea | Best For |
|---|-----------|-----------|----------|
| 8 | **Retrieval Practice** | Retrieval + spaced repetition is the most effective study method | Test prep, memorization, study efficiency, study coaching |
| 9 | **Growth Mindset** | Ability grows through effort; praise the process | Fear of failure, giving up, "I can't do it" mindset |
| 10 | **UbD** | Backward design: goals -> assessment -> activities | Curriculum design, project planning, learning objectives |
| 11 | **PBL** | Learn through real-world problem-solving projects | Inquiry learning, self-directed projects, motivation |

### Early Childhood

| # | Framework | Core Idea | Best For |
|---|-----------|-----------|----------|
| 12 | **Montessori** | Prepared environment, self-paced learning, sensitive periods | 0-6 environment setup, independence, practical life |
| 13 | **DAP** | Expectations and activities matched to developmental level | Early childhood curriculum, play-based learning, developmental fit |

### Special Needs / Inclusive Education

| # | Framework | Core Idea | Best For |
|---|-----------|-----------|----------|
| 14 | **UDL** | Multiple means of representation, engagement, and action | Inclusive classrooms, learning disabilities, diverse learners |

### Teacher Tools

| # | Framework | Core Idea | Best For |
|---|-----------|-----------|----------|
| 15 | **Formative Assessment** | Real-time checks during learning -> immediate feedback | In-class comprehension checks, identifying learning gaps |
| 16 | **Differentiated Instruction** | Differentiate content, process, and product by learner | Tiered instruction, mixed classrooms, individualized teaching |

---

## Detection Matrix

The agent analyzes keywords and patterns in the situation to match frameworks.

| Signal in Situation | Primary Framework | Secondary |
|--------------------|------------------|-----------|
| "tantrum", "won't listen", "discipline", "behavior" | **Positive Discipline** | PET |
| "screaming", "meltdown", "can't control emotions" | **Emotion Coaching** | CPS |
| "fighting", "conflict", "sibling fight" | **PET** | Positive Discipline |
| "recurring problem behavior", "ADHD", "autism", "won't vs. can't" | **CPS** | UDL |
| "anxiety", "separation anxiety", "only wants mom", "attachment" | **Attachment-Based** | Emotion Coaching |
| "won't study", "hates school/lessons", "no motivation", "forced" | **SDT Parenting** | Growth Mindset |
| "exam", "grades", "memorization", "study methods", "cramming" | **Retrieval Practice** | Growth Mindset |
| "gives up", "I can't", "afraid of failure", "cries when wrong" | **Growth Mindset** | Emotion Coaching |
| "lesson design", "curriculum", "learning objectives" | **UbD** | Formative Assessment |
| "project learning", "inquiry", "self-directed" | **PBL** | UbD |
| "infant", "0 years", "1 year", "2 years", "environment setup" | **Montessori** | DAP |
| "toddler", "preschool", "play", "developmentally appropriate" | **DAP** | Montessori |
| "disability", "inclusive classroom", "wide learning gap" | **UDL** | Differentiated Instruction |
| "different levels", "individualized", "mixed classroom" | **Differentiated Instruction** | UDL |
| "not sure if they understood", "assessment", "feedback" | **Formative Assessment** | Differentiated Instruction |
| "overall parenting approach", "systematic", "parent education" | **Triple P** | Positive Discipline |
| "how to praise", "self-esteem", "autonomy" | **SDT Parenting** | Growth Mindset |
| "puberty", "defiance", "communication breakdown" | **PET** | CPS |
| "smartphone", "gaming addiction", "screen time" | **Positive Discipline** | SDT Parenting |
| "homework battles", "after-school conflicts" | **SDT Parenting** | Retrieval Practice |
| "bullying", "school violence", "peer relationships" | **Emotion Coaching** | CPS |

**Korean-language signals** (for Korean-speaking users):

| Signal (Korean) | Primary Framework | Secondary |
|--------------------|------------------|-----------|
| "떼쓴다", "말 안 들어", "훈육", "버릇" | **Positive Discipline** | PET |
| "소리 지른다", "폭발", "감정 조절 못해" | **Emotion Coaching** | CPS |
| "싸운다", "갈등", "형제 싸움" | **PET** | Positive Discipline |
| "공부 안 해", "학원 싫어", "동기 없어" | **SDT Parenting** | Growth Mindset |
| "사춘기", "반항", "대화 안 통해" | **PET** | CPS |
| "스마트폰", "게임 중독", "스크린 타임" | **Positive Discipline** | SDT Parenting |
| "따돌림", "학교폭력", "친구 관계" | **Emotion Coaching** | CPS |

---

## Age-Based Routing

The pool of applicable frameworks changes with the child's age.

### Infancy (0-2 years)
**Available:** Attachment-Based, Montessori, DAP
**Primary Strategy:** Secure attachment is the foundation of everything. Environment design and sensitive responsiveness.
**Not Applicable:** PET (language not yet developed), Retrieval Practice, Growth Mindset (insufficient cognitive development)

### Early Childhood (3-5 years)
**Available:** Montessori, DAP, Positive Discipline, Emotion Coaching, Attachment-Based, Triple P
**Primary Strategy:** Label emotions, offer choices, prepare the environment, play-based learning.
**Emerging:** PET (simple I-messages), SDT (basic autonomy)

### Lower Elementary (6-9 years)
**Available:** All frameworks (full access)
**Primary Strategy:** Habit formation period. Build the learning foundation with Growth Mindset + Retrieval Practice. Develop self-discipline with Positive Discipline.
**Sweet Spot:** Family meetings (Positive Discipline), emotion coaching (Emotion Coaching), process praise (Growth Mindset)

### Upper Elementary (10-12 years)
**Available:** All frameworks (full access)
**Primary Strategy:** Increasing demand for autonomy. Shift to intrinsic motivation via SDT Parenting. Provide inquiry experiences via PBL.
**Key Transition:** Begin shifting from parental control to coaching role

### Middle School (13-15 years)
**Available:** All frameworks, emphasis on SDT, PET, CPS, Growth Mindset
**Primary Strategy:** Puberty onset. Active listening from PET is critical. Respect autonomy via SDT. Negotiate via CPS.
**Warning:** Be cautious with the "firm" part of Positive Discipline — risk of relationship damage. Prioritize listening.

### High School (16-18 years)
**Available:** SDT, PET, CPS, Growth Mindset, Retrieval Practice, PBL
**Primary Strategy:** Nearly adult. Coaching/mentoring mode. Maximize autonomy via SDT. Career-related UbD.
**Not Effective:** Montessori (age-inappropriate), Triple P (independence phase)

---

## Role-Based Routing

### Parent
**Core Pool:** Positive Discipline, PET, CPS, Emotion Coaching, Triple P, Attachment-Based, SDT Parenting, Growth Mindset
**Focus:** Maintaining the relationship is the top priority. Connection before correction.

### Teacher
**Core Pool:** UbD, PBL, Formative Assessment, Differentiated Instruction, UDL, Growth Mindset, Retrieval Practice
**Focus:** Learning effectiveness is the top priority. Individualization and engagement.

### Caregiver (grandparent, nanny, etc.)
**Core Pool:** Attachment-Based, DAP, Emotion Coaching, Positive Discipline
**Focus:** Safety and emotional stability. Consistency.

---

## Situation-Based Routing (Multi-Framework Pipelines)

### Pipeline 1: Child is having a tantrum, crying on the floor
**Sequence:** Emotion Coaching (accept feelings) -> Positive Discipline (kind + firm) -> CPS (post-event problem-solving)

| Phase | Framework | Purpose |
|-------|-----------|---------|
| Immediate | **Emotion Coaching** | Acknowledge the emotion. "You're really angry right now." Name it. Stay nearby until they calm down. |
| After calming | **Positive Discipline** | Set limits kindly and firmly. "It's okay to cry. But throwing things is not okay." |
| Later | **CPS** | If it's a recurring pattern, use Plan B conversation. "What makes it hard for you when ~?" |

### Pipeline 2: Child hates studying and refuses to go to after-school programs
**Sequence:** SDT Parenting (motivation analysis) -> Growth Mindset (mindset shift) -> Retrieval Practice (study method change)

| Phase | Framework | Purpose |
|-------|-----------|---------|
| Diagnosis | **SDT Parenting** | Analyze the 3 basic needs. Autonomy undermined? Competence lacking? Relationship issue (teacher/peers)? |
| Mindset | **Growth Mindset** | "You can't do it YET." Shift to praising effort and process. |
| Study method | **Retrieval Practice** | Switch from rereading to retrieval practice. Short quizzes, spaced repetition. Experience small wins. |

### Pipeline 3: Recurring problem behavior (throwing things, hitting)
**Sequence:** CPS (root cause) -> Emotion Coaching (emotional education) -> Triple P (environment design)

| Phase | Framework | Purpose |
|-------|-----------|---------|
| Analysis | **CPS** | Plan B: Listen to child's perspective -> Share adult's perspective -> Find solution together. |
| Emotions | **Emotion Coaching** | Expand emotional vocabulary. Collaboratively find alternative expressions for anger. |
| Environment | **Triple P** | Modify antecedent conditions. Build predictable routines. Positive reinforcement system. |

### Pipeline 4: Communication breakdown with teenager
**Sequence:** PET (listening) -> SDT Parenting (autonomy) -> CPS (negotiation)

| Phase | Framework | Purpose |
|-------|-----------|---------|
| Listening | **PET** | Active listening. Reflect without interpreting, judging, or advising. Determine problem ownership. |
| Autonomy | **SDT Parenting** | Reduce control. Expand choices. Provide rationale (rationale giving). |
| Negotiation | **CPS** | Use Plan B to co-create rules. Incorporate both sides' concerns. |

### Pipeline 5: Teacher managing a classroom with wide skill gaps
**Sequence:** UDL (accessibility) -> Differentiated Instruction (individualization) -> Formative Assessment (monitoring)

| Phase | Framework | Purpose |
|-------|-----------|---------|
| Design | **UDL** | Pre-design multiple means of representation, engagement, and action. Remove barriers. |
| Execution | **Differentiated Instruction** | Differentiate content, process, and product by readiness, interest, and learning profile. |
| Monitoring | **Formative Assessment** | Use exit tickets, traffic lights, peer teaching for real-time comprehension checks. |

### Pipeline 6: Setting up an early childhood environment
**Sequence:** DAP (developmental fit) -> Montessori (environment design) -> Attachment-Based (relationship)

| Phase | Framework | Purpose |
|-------|-----------|---------|
| Baseline | **DAP** | Set appropriate expectations and activity scope for this age. |
| Environment | **Montessori** | Child-height shelves, real tools, order, areas for free choice. |
| Relationship | **Attachment-Based** | Caregiver as secure base. Sensitive responsiveness. Encourage exploration. |

### Pipeline 7: Sibling conflict
**Sequence:** Emotion Coaching (both sides' feelings) -> PET (conflict resolution) -> Positive Discipline (family meeting)

| Phase | Framework | Purpose |
|-------|-----------|---------|
| Emotions | **Emotion Coaching** | Acknowledge both children's feelings. Do not take sides. |
| Resolution | **PET** | No-lose conflict resolution 6 steps. Let the children propose solutions. |
| Structure | **Positive Discipline** | Create rules together in regular family meetings. |

---

## Conflict Resolution Between Frameworks

Priority rules when frameworks give conflicting advice.

### Rule 1: Emotions first, behavior second
Trying to correct behavior before addressing emotions backfires. Emotion Coaching / Active Listening is always the first step.

**Priority:** Emotion Coaching (accept feelings) > Positive Discipline (set limits) > Triple P (behavior modification)

### Rule 2: Relationship over discipline
When the relationship is damaged, no discipline method works. Reconsider any approach that risks the relationship.

**Priority:** Maintaining the relationship > Immediate behavior correction

### Rule 3: Developmental level determines expectations
No matter how good a framework is, you cannot demand what a child is not developmentally ready for.

**Priority:** DAP (developmental appropriateness) > All other frameworks

### Rule 4: Autonomy outlasts control
External control (rewards/punishments) has short-term effects; intrinsic motivation (autonomy) has long-term effects.

**Priority:** SDT (intrinsic motivation) > Triple P (external reinforcement) — Exception: immediate intervention in dangerous situations

### Rule 5: Distinguish "can't" from "won't"
CPS's core principle: First determine whether the child is choosing not to do something or lacks the skill to do it.

**Priority:** CPS (lagging skills hypothesis) > Positive Discipline (mistaken goal hypothesis)

---

## Korean Cultural Adaptation Layer

The Korean education and parenting environment has unique contextual factors distinct from Western settings. These must be considered when applying frameworks.

### Education Fever (교육열)
- **Reality:** Hagwon (private tutoring/academy) culture, advanced learning, exam-centric system. Parental anxiety drives excessive academic demands.
- **Application:** Use SDT Parenting to shift focus to "Why study?" and intrinsic motivation. Use Retrieval Practice for "less but more effective" study.
- **Caution:** "Quit all hagwons" is unrealistic. Gradual expansion of autonomy is more practical.

### Anti-Corporal-Punishment Law (2021 Civil Code Article 915 Amendment)
- **Reality:** Corporal punishment is legally prohibited. But "how do I discipline without hitting?" confusion persists.
- **Application:** Positive Discipline, PET, and CPS are all non-punitive discipline methods. Present these as alternatives.
- **Emphasis:** Corporal punishment produces short-term compliance + long-term relationship damage. Evidence-based alternatives exist.

### Credential Culture and Academic Stress (학벌 문화)
- **Reality:** Grades are directly tied to self-worth. "If you can't study, your life is over" messaging is pervasive.
- **Application:** Use Growth Mindset to shift to process praise. "You worked hard" instead of "You're so smart."
- **Caution:** Provide realistic career diversity information alongside mindset work. Mindset alone cannot solve structural problems.

### Grandparent Caregiving / Multi-Generational Households (조부모 양육)
- **Reality:** Grandparents are deeply involved in childcare. Parenting philosophy clashes are common.
- **Application:** Agree on core principles (accept emotions, maintain consistency). Respect each person's style on specifics.
- **Caution:** Criticizing grandparents backfires. Frame it as "working together for the child."

### Dual-Income + Caregiving Gap (맞벌이)
- **Reality:** Long working hours, limited parenting time.
- **Application:** Quality over quantity. Even brief moments of Emotion Coaching create connection.
- **Strategy:** 5-minute morning routine, bedtime conversation, weekend 1:1 time.

### High Private Education Costs (높은 사교육비)
- **Reality:** Household education spending is among the highest in the world.
- **Application:** Maximize study efficiency with Retrieval Practice + Growth Mindset. Build self-directed learning capacity with PBL.
- **Practical advice:** Rather than reducing the number of hagwons, maximize hagwon effectiveness by pairing with retrieval practice at home.

---

## Emotion Level Routing

The available frameworks change based on the emotional temperature of the situation.

### Crisis (danger: self-harm, violence, extreme panic)
**Available:** Immediate safety only. Framework application is NOT appropriate.
**Action:** Secure safety -> Connect with professionals.

**Emergency contacts (Korea):**
- Mental Health Crisis Line: 1577-0199
- Child Abuse Reporting: 112
- Suicide Prevention: 1393
- Wee Center (school violence/maladjustment): 1588-7179
- Developmental Disability Counseling: 1644-8295

### High (active emotional outburst)
**Available:** Emotion Coaching, Active Listening (from howtotalk)
**Goal:** Accept emotions and allow calming. Discipline/education is meaningless at this stage.
**Rule:** Wait until the child calms down. Minimum 20 minutes.

### Medium (somewhat agitated, irritated, unhappy)
**Available:** All frameworks. This is the most productive zone.
**Goal:** Execute the situation-appropriate framework pipeline.

### Low (calm, planning stage)
**Available:** All frameworks. Preventive frameworks are especially effective here.
**Goal:** Proactively apply Triple P (environment design), UbD (learning design), SDT (motivation system), family meetings (Positive Discipline).

---

## Sub-Commands

### `/parenting` — Full Situation Analysis & Routing

The primary command. Describe a situation and receive a complete education/parenting strategy.

**Process:**

1. **Intake:** Parse the situation. Infer age, role, emotion level, constraints.

2. **Diagnosis:** Score the situation against all 16 frameworks. Identify the top 3.

3. **Age Filter:** Exclude frameworks inappropriate for the child's age.

4. **Pipeline Design:** If multiple frameworks are needed, design the sequence (which framework handles which phase).

5. **Strategy Generation:** Generate specific tactics, conversation scripts, and execution guides for each selected framework by invoking sub-skills.

6. **Cultural Check:** Review for cultural context realism and adjust accordingly.

7. **Risk Assessment:** Identify what could go wrong and how to respond.

**Output format:**

```
Parenting & Education Strategy
================================

Situation Analysis:
  Type: [Discipline / Learning / Emotional / Relationship / Development / Environment / ...]
  Child Age: [X years / X-Y years]
  Role: [Parent / Teacher / Caregiver]
  Emotion Level: [Low / Medium / High / Crisis]
  Core Need: [Autonomy / Competence / Relatedness / Safety / ...]

Framework Selection:
  Primary: [Framework] — [Reason]
  Secondary: [Framework] — [Reason]
  Support: [Framework, if needed] — [Reason]

Execution Pipeline:
  Phase 1 (Immediate): [Framework] — [What to do]
  Phase 2 (After stabilization): [Framework] — [How to talk]
  Phase 3 (Long-term): [Framework] — [What structure to build]

Conversation Script:
  Opening: "[Exact words]"
  Key phrases: ["Phrase 1", "Phrase 2", "Phrase 3"]
  If child refuses: "[Response]"
  If child cries: "[Response]"
  If child escalates: "[Response]"
  Closing: "[Exact words]"

Cultural Considerations:
  [Context-specific cultural factors for this situation]

Risk Factors:
  1. [Risk]: [Mitigation]
  2. [Risk]: [Mitigation]

Follow-Up:
  [What to do after the conversation/intervention]
```

### `/parenting:select` — Quick Framework Selection

For when you just want to know which framework fits, without full analysis.

**Process:**
1. Describe the situation in one sentence
2. Agent returns top 3 frameworks + one-line rationale
3. User selects or accepts auto-selection

**Output format:**
```
Framework Selection
====================

Situation: [One-line summary]
Age: [Estimated age range]

Recommendations:
  1. [Framework] — [One-line rationale] [Fit %]
  2. [Framework] — [One-line rationale] [Fit %]
  3. [Framework] — [One-line rationale] [Fit %]

Auto-selected: [#1 Framework] (Fit: [X]%)
```

### `/parenting:age` — Age-Based Guide

A comprehensive parenting/education guide for a specific age range. Can be used with age alone, no situation needed.

**Process:**
1. Input age (e.g., "5 years old", "3rd grader", "middle schooler")
2. Receive developmental characteristics, applicable frameworks, key strategies, and cautions

**Output format:**
```
Age-Based Guide: [X years / X-Y years]
========================================

Developmental Characteristics:
  Cognitive: [Cognitive development at this stage]
  Emotional: [Emotional development at this stage]
  Social: [Social development at this stage]
  Physical: [Physical development at this stage]

Applicable Frameworks (by priority):
  1. [Framework] — [Why it matters at this age]
  2. [Framework] — [Why it matters at this age]
  3. [Framework] — [Why it matters at this age]

Key Developmental Tasks:
  - [Task 1]
  - [Task 2]
  - [Task 3]

Common Mistakes:
  - [Mistake 1] -> [Alternative]
  - [Mistake 2] -> [Alternative]

Cultural Context Notes:
  [What parents/teachers in the Korean context should especially watch for at this age]

Recommended Reading:
  - [Book 1] — [One-line description]
  - [Book 2] — [One-line description]
```

---

## Framework Compatibility Matrix

### High Synergy Pairs
- **Emotion Coaching + Positive Discipline:** Accept emotions, then set limits. The most fundamental parenting combo.
- **SDT + Growth Mindset:** Intrinsic motivation + growth belief. The two pillars of learning motivation.
- **CPS + PET:** Both treat the child as a problem-solving partner. Twin pillars of collaborative approaches.
- **UbD + Formative Assessment:** Backward design + real-time monitoring. A teacher's essential toolkit.
- **Montessori + DAP:** Environment design + developmental fit. The foundation of early childhood education.
- **UDL + Differentiated Instruction:** Accessibility + individualization. A complete system for diverse learners.

### Tension Pairs (use with caution)
- **Positive Discipline + CPS:** PD interprets behavior as "mistaken goals" (seeking belonging); CPS interprets it as "lagging skills." Resolution: Test the lagging skills hypothesis (CPS) first, then apply PD if warranted.
- **Triple P + SDT:** Triple P's reward systems may undermine SDT's intrinsic motivation. Resolution: Minimize extrinsic rewards; favor natural consequences.
- **Growth Mindset + Realistic Career Guidance:** Blind faith in "effort conquers all" is dangerous. Resolution: Pair mindset work with strength discovery + diverse success pathways.

---

## Decision Flowchart

```
START
  |
  v
Is the child in danger? (self-harm, violence, abuse)
  YES --> Secure safety immediately -> Connect with professionals (1577-0199, 112)
  NO  --> Continue
  |
  v
Is the child in emotional meltdown?
  YES --> Emotion Coaching (accept feelings, wait for calming)
  NO  --> Continue
  |
  v
What is your role?
  |
  +--> Parent --> Child's age?
  |     |
  |     +--> 0-2 years --> Attachment-Based + Montessori
  |     +--> 3-5 years --> Emotion Coaching + Positive Discipline + DAP
  |     +--> 6-12 years --> Situation-based routing (below)
  |     +--> 13-18 years --> PET + SDT + CPS
  |
  +--> Teacher --> UbD + Formative Assessment + Differentiated Instruction
  |
  +--> Caregiver --> Attachment-Based + Emotion Coaching
  |
  v
Parent + 6-12 years: What is the specific situation?
  |
  +--> Discipline / behavior issue --> Positive Discipline + CPS
  +--> Learning / study issue --> SDT + Growth Mindset + Retrieval Practice
  +--> Emotional issue --> Emotion Coaching + Attachment-Based
  +--> Social / relationship issue --> PET + Emotion Coaching
  +--> General parenting concern --> Triple P + SDT
  +--> Not sure --> Fallback Sequence
```

---

## Fallback Strategy

A universal approach used when the situation does not map clearly to a specific framework.

### The Universal Parenting Sequence

1. **Observe** (Positive Discipline): What are the objective facts? No judgment.
2. **Emotion** (Emotion Coaching): What is the child feeling right now? What am I feeling?
3. **Need** (SDT): Which basic need is unmet? (Autonomy? Competence? Relatedness?)
4. **Development** (DAP): Is this a reasonable expectation for this child's developmental level?
5. **Listen** (PET): Understand the child's perspective through active listening.
6. **Collaborate** (CPS): Find a solution together. Plan B.

This sequence works in most education/parenting situations. Understand first, then solve.

---

## Execution Protocol

### Step 1: Listen & Classify
Carefully read the user's situation description:
- Child's age (stated or inferred)
- Role (parent / teacher / caregiver)
- Situation type (discipline / learning / emotional / relationship / development / environment)
- Emotion level (crisis / high / medium / low)
- Whether this is a recurring pattern

### Step 2: Select Framework(s)
Combine Detection Matrix + Age Filter + Role Filter:
- PRIMARY: 1 framework (best fit)
- SECONDARY: 0-2 frameworks (for multi-faceted situations)
- Explain the selection reason in one sentence each

### Step 3: Execute
Invoke the selected framework(s) as sub-skills using the Skill tool:
```
Skill("positive-discipline", args="[situation description]")
```
For multiple frameworks, execute in logical order (emotion -> behavior -> structure).

### Step 4: Synthesize
Integrate all framework outputs:
- **Integration:** Points of agreement and difference between frameworks
- **Priority:** The single most important insight
- **Action:** Specific next steps (maximum 3)
- **Conversation script:** Words you can actually say (natural language appropriate to the user)

---

## References

### Core Texts (The 16 Frameworks)

**Behavioral/Discipline:**
1. Nelsen, J. (2006). *Positive Discipline*. Ballantine Books.
2. Gordon, T. (2000). *Parent Effectiveness Training*. Three Rivers Press.
3. Greene, R.W. (2014). *The Explosive Child*. Harper Paperbacks.
4. Gottman, J. & DeClaire, J. (1997). *Raising an Emotionally Intelligent Child*. Simon & Schuster.

**Parent Coaching:**
5. Sanders, M.R. (2012). *Every Parent*. Penguin. (Triple P)
6. Bowlby, J. (1988). *A Secure Base*. Basic Books. / Ainsworth, M.D.S. et al. (1978). *Patterns of Attachment*.
7. Deci, E.L. & Ryan, R.M. (2017). *Self-Determination Theory*. Guilford Press.

**Learning/Cognitive:**
8. Brown, P.C., Roediger, H.L., & McDaniel, M.A. (2014). *Make It Stick*. Harvard University Press.
9. Dweck, C. (2006). *Mindset*. Random House.
10. Wiggins, G. & McTighe, J. (2005). *Understanding by Design*. ASCD. 2nd ed.
11. Larmer, J. et al. (2015). *Setting the Standard for Project Based Learning*. ASCD.

**Early Childhood:**
12. Montessori, M. (1967). *The Absorbent Mind*. Holt Paperbacks.
13. NAEYC (2020). *Developmentally Appropriate Practice*. NAEYC. 4th ed.

**Special Needs & Teacher Tools:**
14. CAST (2018). *Universal Design for Learning Guidelines* version 2.2. udlguidelines.cast.org
15. Wiliam, D. (2011). *Embedded Formative Assessment*. Solution Tree Press.
16. Tomlinson, C.A. (2014). *The Differentiated Classroom*. ASCD. 2nd ed.

### Meta/Integration
- Siegel, D.J. & Bryson, T.P. (2011). *The Whole-Brain Child*. Delacorte Press.
- Siegel, D.J. & Bryson, T.P. (2014). *No-Drama Discipline*. Bantam.
- Kim, U. & Park, Y.S. (2006). "Indigenous psychological analysis of academic achievement in Korea." *International Journal of Psychology*.
