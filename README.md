# Parenting — Education & Parenting Frameworks for AI Agents

16 education and parenting frameworks, one auto-routing entry point.
Describe your situation — `/parenting` picks the best approach for your child's age and needs.

## `/parenting` — One Command, 16 Frameworks

```
/parenting My 7-year-old throws tantrums every time we leave the playground
```

The AI automatically:
1. Identifies child's age band and your role (parent/teacher)
2. Selects the best 1-3 frameworks
3. Designs a phased pipeline (emotion → behavior → structure)
4. Generates specific dialogue scripts you can use today

## Commands

| Command | What It Does |
|---------|-------------|
| `/parenting` | Full analysis → framework selection → strategy with scripts |
| `/parenting:select` | Quick framework recommendation only |
| `/parenting:age` | Age-based developmental guide (no situation needed) |

## The 16 Frameworks

### Behavioral / Discipline

| Framework | Creator | Best For |
|-----------|---------|----------|
| **Positive Discipline** | Jane Nelsen | Daily discipline, family meetings, kind + firm |
| **PET** | Thomas Gordon | Parent-child communication, conflict resolution |
| **CPS** | Ross Greene | Chronic behavior problems, explosive children, ADHD |
| **Emotion Coaching** | John Gottman | Emotional outbursts, emotional intelligence |

### Parent Coaching

| Framework | Creator | Best For |
|-----------|---------|----------|
| **Triple P** | Matthew Sanders | Systematic parenting plan, prevention |
| **Attachment-Based** | Bowlby/Ainsworth/Siegel | Infant bonding, separation anxiety, secure base |
| **SDT Parenting** | Deci & Ryan | Intrinsic motivation, autonomy, study conflicts |

### Learning / Cognitive

| Framework | Creator | Best For |
|-----------|---------|----------|
| **Retrieval Practice** | Roediger et al. | Study methods, test prep, effective learning |
| **Growth Mindset** | Carol Dweck | Fear of failure, "I can't do it" mindset |
| **UbD** | Wiggins & McTighe | Curriculum design, backward planning |
| **PBL** | Buck Institute | Project-based learning, self-directed inquiry |

### Early Childhood / Special Needs / Teacher Tools

| Framework | Creator | Best For |
|-----------|---------|----------|
| **Montessori** | Maria Montessori | 0-6 environment design, independence |
| **DAP** | NAEYC | Developmentally appropriate expectations |
| **UDL** | CAST/David Rose | Inclusive education, learning differences |
| **Formative Assessment** | Black & Wiliam | Real-time learning checks, feedback |
| **Differentiated Instruction** | Tomlinson | Mixed-level classrooms, personalization |

## Age-Based Routing

| Age | Primary Frameworks | Focus |
|-----|-------------------|-------|
| 0-2 | Attachment, Montessori, DAP | Secure attachment, environment |
| 3-5 | Emotion Coaching, Positive Discipline, DAP | Feelings, choices, play |
| 6-9 | All available | Learning habits, Growth Mindset |
| 10-12 | SDT, PBL, PET | Autonomy transition begins |
| 13-15 | PET, SDT, CPS | Puberty. Listen first. |
| 16-18 | SDT, CPS, PET | Near-adult. Coach/mentor mode. |

## Installation

```bash
git clone https://github.com/ironyjk/parenting-frameworks.git /tmp/pf
cp -r /tmp/pf/parenting .claude/skills/
```

## Korean Cultural Adaptation

- Education fever (교육열) — realistic approach to hakwon culture
- Corporal punishment ban (2021) — non-punitive discipline alternatives
- Academic stress — Growth Mindset + diverse success paths
- Grandparent caregiving — aligning across generations
- Dual-income time pressure — quality over quantity

## Related Projects

- **[strategy-frameworks](https://github.com/ironyjk/strategy-frameworks)** — 29 strategy frameworks + `/think`
- **[howtotalk](https://github.com/ironyjk/howtotalk)** — 13 communication frameworks + `/howtotalk`
- **[counsel-frameworks](https://github.com/ironyjk/counsel-frameworks)** — 14 psychology frameworks + `/counsel`
- **[toc-agents](https://github.com/ironyjk/toc-agents)** — Theory of Constraints, 10 tools
- **[triz-agents](https://github.com/ironyjk/triz-agents)** — TRIZ, 9 tools

## License

MIT

## Author

@ironyjk × Claude Code
