# Changelog

All notable changes to the Parenting Frameworks project are documented in this file.

The format follows [Keep a Changelog](https://keepachangelog.com/), and this project adheres to [Semantic Versioning](https://semver.org/).

## [1.1.0] - 2026-04-15

### Added
- Comprehensive README.md (English) and README.ko.md (Korean)
- docs/FRAMEWORKS.md: Detailed comparison of all 16 frameworks with applicability matrix, compatibility chart, and conflict resolution rules
- docs/AGE-GUIDE.md: Complete age-based guide (0-2, 3-5, 6-9, 10-12, 13-15, 16-18) with developmental milestones, recommended frameworks, common mistakes, and Korean cultural context
- CHANGELOG.md: Version history
- Architecture diagram in README
- Installation instructions for Claude Code, Claude Projects, and other AI platforms
- 4 realistic usage examples spanning toddler to teen scenarios
- Age routing chart with framework applicability ratings
- Framework quick-selection guide
- Parent vs. Teacher framework classification
- Cross-age universal principles section
- Korean emergency resources

### Changed
- Router version bumped from 1.0.0 to 1.1.0
- README restructured with table of contents and clear sections

## [1.0.0] - 2026-04-12

### Added
- Parenting meta-router (parenting/SKILL.md): Intelligent routing layer that analyzes situation, age, role, and emotion level to select optimal framework(s)
- 16 sub-framework skills, each as a self-contained SKILL.md:
  - Behavioral/Discipline: Positive Discipline, PET, CPS, Emotion Coaching
  - Parenting Strategies: Triple P, Attachment Parenting, SDT Parenting
  - Learning/Cognitive: Retrieval Practice, Growth Mindset, UbD, PBL
  - Early Childhood: Montessori, DAP
  - Special Needs/Inclusive: UDL
  - Teacher Tools: Formative Assessment, Differentiated Instruction
- Detection matrix with English and Korean keyword signals
- Age-based routing (6 age bands with framework availability)
- Role-based routing (Parent, Teacher, Caregiver)
- Emotion level routing (Crisis, High, Medium, Low)
- 7 pre-built situation pipelines (tantrum, study refusal, recurring behavior, teen communication, classroom gaps, early childhood environment, sibling conflict)
- Framework conflict resolution rules (5 priority rules)
- Korean cultural adaptation layer (education fever, anti-corporal-punishment law, credential culture, grandparent caregiving, dual-income gaps, private education costs)
- Fallback strategy: Universal Parenting Sequence (Observe, Emotion, Need, Development, Listen, Collaborate)
- Sub-commands: /parenting, /parenting:select, /parenting:age
- MIT License

---

## Version Numbering

- **Major (X.0.0):** New frameworks added or fundamental architecture changes
- **Minor (0.X.0):** New features, documentation, detection matrix updates
- **Patch (0.0.X):** Bug fixes, wording improvements, minor corrections
