# Parenting Frameworks

**An intelligent meta-router that selects the optimal parenting and education framework for any situation.**

Describe your situation. The system analyzes the child's age, your role, and the context to automatically select and combine the best approach from 16 evidence-based frameworks.

You do not need to know which framework to use. Just describe what is happening.

---

## Table of Contents

- [Why This Exists](#why-this-exists)
- [Quick Start](#quick-start)
- [Installation](#installation)
- [The 16 Frameworks](#the-16-frameworks)
- [Architecture](#architecture)
- [Usage Examples](#usage-examples)
- [Age Routing Chart](#age-routing-chart)
- [Commands](#commands)
- [Related Projects](#related-projects)
- [License](#license)

---

## Why This Exists

Parents and teachers face hundreds of situations that require different approaches. A toddler's tantrum needs a different strategy than a teenager's refusal to communicate. A child with ADHD needs a different lens than a child struggling with exam anxiety.

No single framework covers everything. But choosing the right framework requires expertise most people don't have.

**Parenting Frameworks solves this.** It acts as an intelligent routing layer: you describe the situation, and it selects, sequences, and integrates the right frameworks automatically.

---

## Quick Start

```
/parenting My 4-year-old throws a tantrum every time we leave the playground
```

The system will:
1. Detect: age 4, discipline/emotional situation, high emotion level
2. Select: Emotion Coaching (primary) + Positive Discipline (secondary)
3. Generate: A step-by-step strategy with conversation scripts

---

## Installation

### Claude Code (Recommended)

Clone this repository into your Claude Code skills directory:

```bash
# Navigate to your project's .claude/skills/ directory
cd your-project/.claude/skills/

# Clone the frameworks
git clone https://github.com/ironyjk/parenting-frameworks.git

# Or clone individual frameworks you need
cp -r parenting-frameworks/positive-discipline .
cp -r parenting-frameworks/emotion-coaching .
```

Each framework is a self-contained SKILL.md file that Claude Code can invoke directly.

### Claude Projects

1. Go to [claude.ai](https://claude.ai) and open your Project
2. Navigate to Project Knowledge
3. Upload the SKILL.md files from the frameworks you want to use
4. The `parenting/SKILL.md` router should be uploaded first -- it orchestrates the others

### Other AI Platforms

The SKILL.md files are plain Markdown with structured prompts. They work with any LLM that supports system prompts:

1. Copy the contents of `parenting/SKILL.md` as your system prompt
2. Add any sub-framework SKILL.md files as additional context
3. The detection matrix and routing logic are embedded in the text

---

## The 16 Frameworks

### Behavioral / Discipline

| # | Framework | Author | Core Idea | Best For |
|---|-----------|--------|-----------|----------|
| 1 | [Positive Discipline](positive-discipline/) | Jane Nelsen | Kind AND Firm; belonging + capability | Daily discipline, family meetings, problem behavior |
| 2 | [PET](pet/) | Thomas Gordon | I-messages, active listening, no-lose method | Parent-child communication, conflicts |
| 3 | [CPS](cps/) | Ross Greene | "Kids do well if they can" -- lagging skills | Chronic behavior, explosive children, ADHD/ASD |
| 4 | [Emotion Coaching](emotion-coaching/) | John Gottman | Acknowledge and label emotions; 5 steps | Emotional outbursts, regulation skills |

### Parenting Strategies

| # | Framework | Author | Core Idea | Best For |
|---|-----------|--------|-----------|----------|
| 5 | [Triple P](triple-p/) | Matthew Sanders | 5 levels of intervention; evidence-based | Systematic parenting plans, prevention |
| 6 | [Attachment Parenting](attachment-parenting/) | Bowlby / Ainsworth | Secure base, sensitive responsiveness | Infant attachment, separation anxiety |
| 7 | [SDT Parenting](sdt-parenting/) | Deci & Ryan | Autonomy, competence, relatedness | Intrinsic motivation, study conflicts |

### Learning / Cognitive

| # | Framework | Author | Core Idea | Best For |
|---|-----------|--------|-----------|----------|
| 8 | [Retrieval Practice](retrieval-practice/) | Roediger et al. | Pull information out, don't push it in | Test prep, study efficiency |
| 9 | [Growth Mindset](growth-mindset/) | Carol Dweck | Ability grows through effort | Fear of failure, "I can't" mindset |
| 10 | [UbD](ubd/) | Wiggins & McTighe | Backward design: goals > assessment > activities | Curriculum design, learning objectives |
| 11 | [PBL](pbl/) | Larmer et al. | Learn through real-world projects | Inquiry learning, self-directed projects |

### Early Childhood

| # | Framework | Author | Core Idea | Best For |
|---|-----------|--------|-----------|----------|
| 12 | [Montessori](montessori/) | Maria Montessori | Prepared environment, self-paced learning | 0-6 environment, independence |
| 13 | [DAP](dap/) | NAEYC | Match expectations to developmental level | Early childhood, play-based learning |

### Special Needs / Inclusive

| # | Framework | Author | Core Idea | Best For |
|---|-----------|--------|-----------|----------|
| 14 | [UDL](udl/) | CAST | Multiple means of representation and engagement | Inclusive classrooms, diverse learners |

### Teacher Tools

| # | Framework | Author | Core Idea | Best For |
|---|-----------|--------|-----------|----------|
| 15 | [Formative Assessment](formative-assessment/) | Black & Wiliam | Real-time checks during learning | Comprehension checks, learning gaps |
| 16 | [Differentiated Instruction](differentiated-instruction/) | Tomlinson | Differentiate content, process, product | Mixed classrooms, individualized teaching |

---

## Architecture

```
                          User describes situation
                                    |
                                    v
                    +-------------------------------+
                    |     /parenting (Router)        |
                    |                               |
                    |  1. Parse situation            |
                    |  2. Detect age, role, emotion  |
                    |  3. Match via Detection Matrix |
                    |  4. Apply Age Filter           |
                    |  5. Apply Role Filter           |
                    |  6. Design pipeline            |
                    +-------------------------------+
                          |         |         |
                          v         v         v
                    +---------+ +-------+ +--------+
                    | Primary | | Secon | | Support|
                    |Framework| | dary  | |        |
                    +---------+ +-------+ +--------+
                          |         |         |
                          v         v         v
                    +-------------------------------+
                    |     Synthesis Layer            |
                    |                               |
                    |  - Integrate outputs           |
                    |  - Resolve conflicts           |
                    |  - Cultural adaptation         |
                    |  - Conversation scripts        |
                    +-------------------------------+
                                    |
                                    v
                          Unified Strategy
```

### How Routing Works

1. **Detection Matrix** -- Keywords and patterns in the situation are matched against framework signatures (e.g., "tantrum" maps to Emotion Coaching + Positive Discipline)
2. **Age Filter** -- Frameworks inappropriate for the child's age are excluded (e.g., Retrieval Practice is not applicable for ages 0-2)
3. **Role Filter** -- Parent, teacher, and caregiver roles have different core framework pools
4. **Emotion Level** -- Crisis situations bypass frameworks entirely; high-emotion situations restrict to Emotion Coaching and Active Listening first
5. **Pipeline Design** -- Multi-framework situations are sequenced (emotions first, behavior second, structure third)
6. **Conflict Resolution** -- When frameworks disagree, priority rules apply (emotions > behavior, relationship > discipline, development > expectations)

---

## Usage Examples

### Example 1: Toddler Tantrum (Age 3)

```
/parenting My 3-year-old screams and throws things when told "no"
```

**Router selects:** Emotion Coaching (primary) + Positive Discipline (secondary) + CPS (follow-up)

**Pipeline:**
- Phase 1 (Immediate): Emotion Coaching -- "You're really angry right now. It's okay to be angry."
- Phase 2 (After calming): Positive Discipline -- "It's okay to feel angry AND throwing things is not okay."
- Phase 3 (Later): CPS -- If recurring, identify the lagging skill and solve collaboratively.

### Example 2: Homework Refusal (Age 10)

```
/parenting My 10-year-old hates homework and fights us every night about it
```

**Router selects:** SDT Parenting (primary) + Growth Mindset (secondary) + Retrieval Practice (support)

**Pipeline:**
- Diagnosis: SDT -- Is autonomy being crushed? Does the child feel incompetent? Is there a relationship issue with the teacher?
- Mindset: Growth Mindset -- Shift from "I'm bad at math" to "I'm not good at this yet."
- Method: Retrieval Practice -- Replace ineffective re-reading with active recall and spaced repetition.

### Example 3: Teen Communication Breakdown (Age 14)

```
/parenting My 14-year-old won't talk to me anymore. Just grunts and goes to their room.
```

**Router selects:** PET (primary) + SDT Parenting (secondary) + CPS (support)

**Pipeline:**
- Listening: PET -- Active listening without advising. Determine problem ownership.
- Autonomy: SDT -- Reduce control. Expand choices. Provide rationale instead of commands.
- Negotiation: CPS -- Use Plan B to co-create household rules.

### Example 4: Classroom with Wide Skill Gaps (Teacher)

```
/parenting I teach 3rd grade and have students ranging from pre-K to 5th grade reading levels
```

**Router selects:** UDL (primary) + Differentiated Instruction (secondary) + Formative Assessment (support)

**Pipeline:**
- Design: UDL -- Multiple means of representation and engagement. Remove barriers from the start.
- Execution: Differentiated Instruction -- Tier content, process, and product by readiness.
- Monitoring: Formative Assessment -- Exit tickets, traffic lights, peer teaching for real-time checks.

---

## Age Routing Chart

| Age Band | Available Frameworks | Primary Strategy | Not Effective |
|----------|---------------------|-----------------|---------------|
| **0-2** (Infant) | Attachment, Montessori, DAP | Secure attachment is the foundation. Sensitive responsiveness. | PET (no language), Retrieval Practice, Growth Mindset |
| **3-5** (Early Childhood) | Montessori, DAP, Positive Discipline, Emotion Coaching, Attachment, Triple P | Label emotions, offer choices, prepared environment, play-based learning | CPS (limited), UbD, PBL |
| **6-9** (Lower Elementary) | **All 16 frameworks** | Habit formation. Growth Mindset + Retrieval Practice for learning. Positive Discipline for self-discipline. | -- |
| **10-12** (Upper Elementary) | **All 16 frameworks** | Increasing autonomy demands. SDT for intrinsic motivation. PBL for inquiry. | -- |
| **13-15** (Middle School) | SDT, PET, CPS, Growth Mindset, Emotion Coaching, Retrieval Practice | Puberty. Active listening is critical. Respect autonomy. Negotiate. | Be cautious with "firm" Positive Discipline |
| **16-18** (High School) | SDT, PET, CPS, Growth Mindset, Retrieval Practice, PBL | Nearly adult. Coaching mode. Maximize autonomy. | Montessori (age-inappropriate), Triple P (independence phase) |

For a complete age-based guide with developmental milestones, see [docs/AGE-GUIDE.md](docs/AGE-GUIDE.md).

---

## Commands

| Command | Description |
|---------|-------------|
| `/parenting` | Full situation analysis with framework routing and integrated strategy |
| `/parenting:select` | Quick framework selection -- top 3 recommendations with fit scores |
| `/parenting:age` | Age-based developmental guide with applicable frameworks |

Each sub-framework also has its own commands:

| Framework | Commands |
|-----------|---------|
| Positive Discipline | `/positive-discipline`, `:goals`, `:tools`, `:meeting` |
| PET | `/pet`, `:ownership`, `:listen`, `:imessage`, `:nolose` |
| CPS | `/cps`, `:alsup`, `:planb`, `:plans` |
| Emotion Coaching | `/emotion-coaching`, `:style`, `:steps`, `:vocab` |
| Triple P | `/triple-p`, `:level`, `:strategies`, `:self-reg` |
| Growth Mindset | `/growth-mindset` |
| And 10 more... | See individual framework SKILL.md files |

---

## Framework Comparison

For a detailed comparison of all 16 frameworks -- when to use each, compatibility matrix, and parent vs. teacher applicability -- see [docs/FRAMEWORKS.md](docs/FRAMEWORKS.md).

---

## Related Projects

- [How to Talk](https://github.com/ironyjk/parenting-frameworks) -- Meta communication router for 16 interpersonal communication frameworks (NVC, Crucial Conversations, Never Split the Difference, etc.)
- [Counsel](https://github.com/ironyjk/parenting-frameworks) -- Meta-router for 14 psychological counseling frameworks (CBT, ACT, IFS, SFBT, etc.)
- [Think](https://github.com/ironyjk/parenting-frameworks) -- Strategic thinking router for 29 business/analysis frameworks (TOC, TRIZ, Wardley, Porter, etc.)

---

## References

### Core Texts

1. Nelsen, J. (2006). *Positive Discipline*. Ballantine Books.
2. Gordon, T. (2000). *Parent Effectiveness Training*. Three Rivers Press.
3. Greene, R.W. (2014). *The Explosive Child*. Harper Paperbacks.
4. Gottman, J. & DeClaire, J. (1997). *Raising an Emotionally Intelligent Child*. Simon & Schuster.
5. Sanders, M.R. (2012). *Every Parent*. Penguin.
6. Bowlby, J. (1988). *A Secure Base*. Basic Books.
7. Deci, E.L. & Ryan, R.M. (2017). *Self-Determination Theory*. Guilford Press.
8. Brown, P.C. et al. (2014). *Make It Stick*. Harvard University Press.
9. Dweck, C. (2006). *Mindset*. Random House.
10. Wiggins, G. & McTighe, J. (2005). *Understanding by Design*. ASCD.
11. Larmer, J. et al. (2015). *Setting the Standard for PBL*. ASCD.
12. Montessori, M. (1967). *The Absorbent Mind*. Holt Paperbacks.
13. NAEYC (2020). *Developmentally Appropriate Practice*. 4th ed.
14. CAST (2018). *UDL Guidelines* version 2.2.
15. Wiliam, D. (2011). *Embedded Formative Assessment*. Solution Tree Press.
16. Tomlinson, C.A. (2014). *The Differentiated Classroom*. ASCD.

### Integration
- Siegel, D.J. & Bryson, T.P. (2011). *The Whole-Brain Child*. Delacorte Press.
- Siegel, D.J. & Bryson, T.P. (2014). *No-Drama Discipline*. Bantam.

---

## License

MIT License. See [LICENSE](LICENSE) for details.
