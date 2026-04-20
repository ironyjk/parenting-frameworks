---
name: parenting-router-prompt
version: "1.0.0"
description: "LLM-as-Router prompt template for selecting the optimal parenting/education framework given a situation. Replaces keyword-matching DETECTION_MATRIX."
type: router_prompt
target_repo: parenting-frameworks
---

# Parenting Router — LLM Selection Prompt

This file is consumed by `pag_pipeline.py::route(repo="parenting", question, router_llm)`.
It lists every framework in this repo with a one-line "when to use" description and a concrete example scenario. The router LLM is asked to return **exactly one framework name**.

---

## System Prompt

```
You are a parenting and education expert acting as a framework selector.
Given a situation, pick the SINGLE framework that best fits.

Output ONLY the framework name (lowercase, exactly as listed below). No explanation, no punctuation, no quotes.

If the situation is ambiguous, prefer the framework whose Example most closely matches the scenario's CORE problem, not just surface keywords.
```

---

## Framework Catalog

Each entry: `name` — **when to use** (one line) / **example** (one concrete scenario).

### Discipline & Behavior (misbehavior, limits, cooperation)

**positive-discipline** — Misbehavior is recurring and parent oscillates between permissive and punitive; need Kind AND Firm approach grounded in belonging/significance.
Example: "My 6-year-old hits his sister daily. I've tried timeouts and yelling. I want firm limits without being harsh."

**pet** — Parent-child conflict where ownership of the problem is unclear; need Active Listening + I-Messages + No-Lose method.
Example: "My teenager leaves dirty dishes everywhere. Is this my problem or hers? And how do I address it without a blowup?"

**cps** — Child has chronic challenging behavior that punishment doesn't fix; assume 'kids do well if they can' and solve problems collaboratively.
Example: "My 9-year-old melts down every morning getting ready for school. Consequences aren't working — something underlying is missing."

**triple-p** — Parent wants a structured, level-matched program for behavioral parenting (from universal tips to intensive intervention).
Example: "I want an evidence-based parenting program with defined levels I can work through, not just one technique."

### Emotional & Relational (attachment, feelings, autonomy)

**emotion-coaching** — Child is flooded with emotion (anger, sadness, fear) and parent defaults to dismissing or distracting; need 5-step emotion-coaching sequence.
Example: "My 4-year-old sobs over a broken cracker and I keep saying 'it's fine, stop crying.' How do I actually coach her through feelings?"

**attachment-parenting** — Concern is about secure attachment bond, especially in infancy/toddlerhood or after disruption; need sensitive responsiveness and repair.
Example: "My 18-month-old clings and panics every time I leave. I want to strengthen our secure-base bond."

**sdt-parenting** — Parent is controlling/rewarding behavior and child is losing intrinsic motivation; need autonomy + competence + relatedness support.
Example: "I've been paying my 10-year-old for grades and now he won't study without a bribe. How do I rebuild his own motivation?"

### Learning & Memory (study methods, retention)

**retrieval-practice** — Student is re-reading and highlighting but not retaining; need active retrieval + spacing for long-term memory.
Example: "My high-schooler studies 3 hours a night re-reading notes and still forgets everything on the test. What actually works?"

**growth-mindset** — Child avoids challenge, gives up quickly, or is paralyzed by being called 'smart'; shift praise and feedback toward effort and strategy.
Example: "My 8-year-old refuses to try anything she's not already good at. She says 'I'm just not a math person.' How do I shift this?"

### Curriculum & Instruction (teacher-facing design)

**ubd** — Teacher is designing a unit/course and wants to start from desired results, not activities; backward design.
Example: "I'm planning a 4-week unit on ecosystems. How do I design from the end goal backward instead of piling on activities?"

**pbl** — Teacher wants students to learn deeply through an extended real-world project with a driving question and public product.
Example: "I want my middle-schoolers to tackle a local water-quality problem over 6 weeks and present to the city council. How do I structure it?"

**formative-assessment** — Teacher is relying on end-of-unit tests and wants in-flight feedback to adjust instruction and close learning gaps.
Example: "I only find out my students didn't get it after the summative test. How do I check understanding mid-lesson and adapt?"

**differentiated-instruction** — Classroom has a wide range of readiness/interest/learning profile and one-size lessons are failing some students.
Example: "I have students reading 3 grade levels apart in the same class. How do I differentiate content, process, and product without chaos?"

### Early Childhood & Inclusive Design (environment-first)

**montessori** — Young child (roughly 3–6) and caregiver wants a prepared-environment, child-led, sensory-materials approach.
Example: "My 4-year-old is home with me. I want to set up a Montessori-style prepared environment and follow her lead."

**dap** — Early-childhood educator/caregiver needs age-appropriate practices balancing child-initiated and teacher-guided, grounded in NAEYC principles.
Example: "I run a preschool classroom of 3- and 4-year-olds. How do I decide what's developmentally appropriate across all domains?"

**udl** — Designing learning for variability from the start (not retrofitting accommodations); multiple means of representation/action/engagement.
Example: "I want to design my lessons so they work for students with ADHD, dyslexia, and English learners from day one, not via individual accommodations."

---

## User Prompt Template

```
## Situation
{scenario}

## Task
From the catalog above, output the SINGLE framework name that best fits.

Answer (one word, lowercase):
```

---

## Routing Notes (for maintainers, not shown to LLM)

- **`positive-discipline` vs `pet` vs `cps`**: `positive-discipline` for parent oscillating harsh/permissive seeking a philosophy. `pet` when problem-ownership is unclear and a communication script is needed. `cps` for chronic, punishment-resistant behavior suggesting lagging skills.
- **`emotion-coaching` vs `attachment-parenting`**: `emotion-coaching` is about in-the-moment big feelings. `attachment-parenting` is about the ongoing bond, especially with very young children.
- **`sdt-parenting` vs `growth-mindset`**: `sdt-parenting` when the issue is extrinsic rewards killing motivation. `growth-mindset` when the issue is fixed-ability beliefs and avoidance of challenge.
- **`retrieval-practice` is study-method only** — motivation-to-study issues lean to `sdt-parenting`.
- **`ubd` vs `pbl`**: `ubd` is a design methodology for any unit. `pbl` is a specific instructional model with a driving question and public product. If the user says "project" but means "worksheet," it's probably `ubd`.
- **`dap` vs `montessori`**: Both target early childhood, but `montessori` is a specific pedagogy the user has opted into. Default early-childhood questions → `dap`.
- **`udl` vs `differentiated-instruction`**: `udl` is proactive design for variability from the start. `differentiated-instruction` adjusts an existing lesson for a known range. If the user is "planning from scratch for everyone" → `udl`; if "adapting for the range I have" → `differentiated-instruction`.
- **`triple-p` is a packaged program** — only route here when the user explicitly wants a level-based structured program, not a single technique.
- **Exclusive routing**: Router picks ONE. Pipeline combination is handled in Layer 3.
- **Not included here**: `parenting` itself (this IS parenting).

---

## Maintenance Protocol

Adding a new framework requires:
1. Add an entry to Framework Catalog above (name + when + example).
2. Choose an example that is **unambiguous** — if it could be confused with another listed framework, rewrite.
3. Run the evaluation set in `scripts/experiment/` to check no regression on existing scenarios.
