---
name: parenting
version: "1.0.0"
description: "교육/육아 프레임워크 가이드 — 연령, 역할(부모/교사), 상황을 분석하여 16개 교육·양육 프레임워크 중 최적 조합을 자동 선택. 긍정훈육, PET, CPS, 정서코칭, Triple P, 애착양육, SDT, 인출연습, 성장마인드셋, UbD, PBL, 몬테소리, DAP, UDL, 형성평가, 차별화교수 지원."
tools:
  - Read
  - Write
  - Edit
  - WebSearch
  - Skill
user-invocable: true
dependencies:
  - positive-discipline (긍정 훈육 — Jane Nelsen)
  - pet (부모효율성훈련 — Thomas Gordon)
  - cps (협력적 문제해결 — Ross Greene)
  - emotion-coaching (정서 코칭 — John Gottman)
  - triple-p (긍정양육프로그램 — Matthew Sanders)
  - attachment-parenting (애착 기반 양육)
  - sdt-parenting (자기결정이론 양육 — Deci & Ryan)
  - retrieval-practice (인출 연습 + 간격 반복)
  - growth-mindset (성장 마인드셋 — Carol Dweck)
  - ubd (역방향 설계 — Wiggins & McTighe)
  - pbl (프로젝트 기반 학습)
  - montessori (몬테소리 교육)
  - dap (발달에 적합한 실천 — NAEYC)
  - udl (보편적 학습설계 — CAST)
  - formative-assessment (형성평가)
  - differentiated-instruction (차별화 교수 — Carol Ann Tomlinson)
---

# Parenting — 교육/육아 프레임워크 가이드

> "아이는 어른의 축소판이 아니라, 고유한 발달 단계에 있는 독립된 인격체다."

## What This Is

Parenting은 프레임워크 자체가 아니라, 16개 교육·양육 프레임워크 위에 있는 **지능형 라우팅 레이어**다. 아이의 연령, 당신의 역할(부모/교사), 구체적 상황을 분석하여 가장 적합한 프레임워크(들)를 선택하고, 순서대로 실행하여 통합된 가이드를 제공한다.

어떤 프레임워크를 써야 하는지 몰라도 된다. 상황만 설명하면 된다.

---

## Input Schema

```yaml
situation: "string"       # 무슨 일이 일어나고 있는가? (필수)
age: "string"             # 아이 연령 또는 연령대 (0-2, 3-5, 6-9, 10-12, 13-15, 16-18)
role: "string"            # 당신의 역할 (parent / teacher / caregiver)
goal: "string"            # 어떤 결과를 원하는가?
child_traits: "string"    # 아이 특성 (민감한, 활발한, 내성적, 특수교육 필요 등)
emotion_level: "string"   # 현재 감정 온도 (low / medium / high / crisis)
constraints: "string"     # 제약 조건 (시간, 공간, 형제 관계, 학원 스케줄 등)
history: "string"         # 관련 이력 (처음 발생, 반복 패턴, 점차 악화 등)
```

최소 입력: `situation`만 있으면 된다. 나머지는 에이전트가 추론한다.

---

## The 16 Frameworks — Quick Reference

### Behavioral/Discipline (부모-자녀 행동/훈육)

| # | Framework | Core Idea | Best For |
|---|-----------|-----------|----------|
| 1 | **Positive Discipline** | 칭벌 없이 '소속감+능력감' 형성, 친절하면서 단호하게 | 일상 훈육, 문제행동 대응, 가족회의 |
| 2 | **PET** | 나-전달법, 능동적 경청, 무패 갈등해결 | 부모-자녀 소통, 갈등 상황, 문제 소유권 판단 |
| 3 | **CPS** | "아이가 할 수 있다면 하고 있을 것" — 미해결 문제 탐색 | 만성 문제행동, 폭발적 아이, ADHD/ASD |
| 4 | **Emotion Coaching** | 감정을 인정하고 이름 붙이기, 5단계 코칭 | 감정 폭발, 정서 발달, 감정 조절 교육 |

### Parent Coaching (양육 전략)

| # | Framework | Core Idea | Best For |
|---|-----------|-----------|----------|
| 5 | **Triple P** | 5단계 개입 (보편→집중), 근거 기반 양육 | 체계적 양육 계획, 문제행동 예방, 부모 스트레스 |
| 6 | **Attachment-Based Parenting** | 안전기지 형성, 민감 반응, 탐색 격려 | 영유아 애착, 분리불안, 정서적 안정 |
| 7 | **SDT Parenting** | 자율성·유능감·관계성 3대 욕구 충족 | 내적 동기, 자기주도성, 학원/공부 갈등 |

### Learning/Cognitive (학습/인지)

| # | Framework | Core Idea | Best For |
|---|-----------|-----------|----------|
| 8 | **Retrieval Practice** | 꺼내기 연습 + 간격 반복이 최고의 학습법 | 시험 준비, 암기, 학습 효율, 공부법 코칭 |
| 9 | **Growth Mindset** | 능력은 노력으로 성장, 과정 칭찬 | 실패 두려움, 포기, "난 못해" 마인드 |
| 10 | **UbD** | 목표→평가→활동 역방향 설계 | 커리큘럼 설계, 프로젝트 계획, 학습목표 설정 |
| 11 | **PBL** | 실제 문제 해결 프로젝트로 배움 | 탐구학습, 자기주도 프로젝트, 동기 유발 |

### Early Childhood (영유아)

| # | Framework | Core Idea | Best For |
|---|-----------|-----------|----------|
| 12 | **Montessori** | 준비된 환경, 자기 속도 학습, 민감기 | 0-6세 환경 구성, 독립심, 일상생활 연습 |
| 13 | **DAP** | 발달 수준에 맞는 기대와 활동 | 유아 교육과정, 놀이 기반 학습, 발달 적합성 판단 |

### Special Needs (특수/통합)

| # | Framework | Core Idea | Best For |
|---|-----------|-----------|----------|
| 14 | **UDL** | 다양한 표현·참여·행동 수단 제공 | 통합교육, 학습 장애, 다양한 학습자 |

### Teacher Tools (교사 도구)

| # | Framework | Core Idea | Best For |
|---|-----------|-----------|----------|
| 15 | **Formative Assessment** | 학습 '중' 실시간 점검 → 즉시 피드백 | 수업 중 이해도 확인, 학습 격차 파악 |
| 16 | **Differentiated Instruction** | 학습자별 내용·과정·산출물 차별화 | 수준별 교육, 혼합 학급, 개별화 지도 |

---

## Detection Matrix

에이전트는 상황의 키워드와 패턴을 분석하여 프레임워크를 매칭한다.

| Signal in Situation | Primary Framework | Secondary |
|--------------------|------------------|-----------|
| "떼쓴다", "말 안 들어", "훈육", "버릇" | **Positive Discipline** | PET |
| "소리 지른다", "폭발", "감정 조절 못해" | **Emotion Coaching** | CPS |
| "싸운다", "갈등", "형제 싸움" | **PET** | Positive Discipline |
| "반복되는 문제행동", "ADHD", "자폐", "할 수 없는 게 아니라 안 하는 것" | **CPS** | UDL |
| "불안", "분리불안", "엄마만 찾아", "애착" | **Attachment-Based** | Emotion Coaching |
| "공부 안 해", "학원 싫어", "동기 없어", "억지로" | **SDT Parenting** | Growth Mindset |
| "시험", "성적", "암기", "공부법", "벼락치기" | **Retrieval Practice** | Growth Mindset |
| "포기", "난 못해", "실패 두려워", "틀리면 울어" | **Growth Mindset** | Emotion Coaching |
| "수업 설계", "커리큘럼", "학습목표" | **UbD** | Formative Assessment |
| "프로젝트 학습", "탐구", "자기주도" | **PBL** | UbD |
| "영아", "0세", "1세", "2세", "환경 구성" | **Montessori** | DAP |
| "유아", "유치원", "놀이", "발달에 맞는" | **DAP** | Montessori |
| "장애", "통합학급", "학습 격차 크다" | **UDL** | Differentiated Instruction |
| "수준 차이", "개별화", "혼합 학급" | **Differentiated Instruction** | UDL |
| "이해했는지 모르겠다", "평가", "피드백" | **Formative Assessment** | Differentiated Instruction |
| "양육 방식 전반", "체계적으로", "부모 교육" | **Triple P** | Positive Discipline |
| "칭찬 어떻게", "자존감", "자율성" | **SDT Parenting** | Growth Mindset |
| "사춘기", "반항", "대화 안 통해" | **PET** | CPS |
| "스마트폰", "게임 중독", "스크린 타임" | **Positive Discipline** | SDT Parenting |
| "숙제 전쟁", "학원 갈등" | **SDT Parenting** | Retrieval Practice |
| "따돌림", "학교폭력", "친구 관계" | **Emotion Coaching** | CPS |

---

## Age-Based Routing (연령별 자동 라우팅)

아이 연령에 따라 사용 가능한 프레임워크 풀이 달라진다.

### 영아기 (0-2세)
**Available:** Attachment-Based, Montessori, DAP
**Primary Strategy:** 안전 애착 형성이 모든 것의 기초. 환경 구성과 민감 반응.
**Not Applicable:** PET(언어 미발달), Retrieval Practice, Growth Mindset(인지 부족)

### 유아기 (3-5세)
**Available:** Montessori, DAP, Positive Discipline, Emotion Coaching, Attachment-Based, Triple P
**Primary Strategy:** 감정 이름 붙이기, 선택권 주기, 준비된 환경, 놀이 기반 학습.
**Emerging:** PET(단순 나-전달법), SDT(기초 자율성)

### 초등 저학년 (6-9세)
**Available:** All frameworks (full access)
**Primary Strategy:** 학습 습관 형성기. Growth Mindset + Retrieval Practice로 학습 기반 구축. Positive Discipline으로 자기 규율.
**Sweet Spot:** 가족회의(Positive Discipline), 감정 코칭(Emotion Coaching), 과정 칭찬(Growth Mindset)

### 초등 고학년 (10-12세)
**Available:** All frameworks (full access)
**Primary Strategy:** 자율성 요구 증가기. SDT Parenting으로 내적 동기 전환. PBL로 탐구 경험.
**Key Transition:** 부모의 통제 → 코칭으로 역할 전환 시작

### 중학생 (13-15세)
**Available:** All frameworks, emphasis on SDT, PET, CPS, Growth Mindset
**Primary Strategy:** 사춘기 돌입. PET의 능동적 경청이 핵심. SDT로 자율성 존중. CPS로 협상.
**Warning:** Positive Discipline의 '단호한' 부분 주의 — 관계 파괴 위험. 경청 우선.

### 고등학생 (16-18세)
**Available:** SDT, PET, CPS, Growth Mindset, Retrieval Practice, PBL
**Primary Strategy:** 거의 성인. 코칭/멘토링 모드. SDT의 자율성 극대화. 진로 관련 UbD.
**Not Effective:** Montessori(연령 부적합), Triple P(독립 시기)

---

## Role-Based Routing (역할별 라우팅)

### Parent (부모)
**Core Pool:** Positive Discipline, PET, CPS, Emotion Coaching, Triple P, Attachment-Based, SDT Parenting, Growth Mindset
**Focus:** 관계 유지가 최우선. 훈육보다 연결.

### Teacher (교사)
**Core Pool:** UbD, PBL, Formative Assessment, Differentiated Instruction, UDL, Growth Mindset, Retrieval Practice
**Focus:** 학습 효과가 최우선. 개별화와 참여.

### Caregiver (양육자/조부모/돌봄)
**Core Pool:** Attachment-Based, DAP, Emotion Coaching, Positive Discipline
**Focus:** 안전과 정서적 안정. 일관성.

---

## Situation-Based Routing (Multi-Framework Pipelines)

### Pipeline 1: 아이가 떼쓰고 울면서 바닥에 누움
**Sequence:** Emotion Coaching (감정 수용) → Positive Discipline (친절+단호) → CPS (사후 문제해결)

| Phase | Framework | Purpose |
|-------|-----------|---------|
| 즉시 | **Emotion Coaching** | 감정 인정. "많이 화가 났구나." 이름 붙이기. 진정될 때까지 옆에. |
| 진정 후 | **Positive Discipline** | 친절하면서 단호하게 한계 설정. "울어도 괜찮아. 그런데 물건 던지는 건 안 돼." |
| 이후 | **CPS** | 반복 패턴이면 Plan B 대화. "네가 ~할 때 어려운 게 뭐야?" |

### Pipeline 2: 아이가 공부를 싫어하고 학원 가기 거부
**Sequence:** SDT Parenting (동기 분석) → Growth Mindset (마인드셋) → Retrieval Practice (학습법 전환)

| Phase | Framework | Purpose |
|-------|-----------|---------|
| 진단 | **SDT Parenting** | 3대 욕구 분석. 자율성 침해? 유능감 부족? 관계(선생님/친구) 문제? |
| 마인드셋 | **Growth Mindset** | "못하는 게 아니라 아직 못하는 거야." 노력 과정 칭찬으로 전환. |
| 학습법 | **Retrieval Practice** | 읽기 반복 → 인출 연습으로 전환. 짧은 퀴즈, 간격 반복. 성취감 경험. |

### Pipeline 3: 반복되는 문제행동 (물건 던지기, 때리기)
**Sequence:** CPS (근본 원인) → Emotion Coaching (감정 교육) → Triple P (환경 설계)

| Phase | Framework | Purpose |
|-------|-----------|---------|
| 분석 | **CPS** | Plan B: 아이 관점 경청 → 어른 관점 공유 → 함께 해결책 찾기. |
| 감정 | **Emotion Coaching** | 감정 어휘 확장. 분노 표현의 대안 행동 함께 찾기. |
| 환경 | **Triple P** | 선행 조건 수정. 예측 가능한 루틴. 긍정 강화 시스템. |

### Pipeline 4: 사춘기 자녀와 소통 단절
**Sequence:** PET (경청) → SDT Parenting (자율성) → CPS (협상)

| Phase | Framework | Purpose |
|-------|-----------|---------|
| 경청 | **PET** | 능동적 경청. 해석/판단/조언 없이 반영. 문제 소유권 판단. |
| 자율성 | **SDT Parenting** | 통제 줄이기. 선택권 확대. 이유 설명(rationale giving). |
| 협상 | **CPS** | Plan B로 규칙 함께 만들기. 양측 관심사 반영. |

### Pipeline 5: 교사 — 수준 차이 큰 학급 운영
**Sequence:** UDL (접근성) → Differentiated Instruction (개별화) → Formative Assessment (점검)

| Phase | Framework | Purpose |
|-------|-----------|---------|
| 설계 | **UDL** | 다양한 표현·참여·행동 수단 사전 설계. 장벽 제거. |
| 실행 | **Differentiated Instruction** | 준비도/흥미/학습 프로필별 내용·과정·산출물 차별화. |
| 점검 | **Formative Assessment** | Exit ticket, 신호등, 동료 교수로 실시간 이해도 확인. |

### Pipeline 6: 영유아 환경 구성
**Sequence:** DAP (발달 적합성) → Montessori (환경 설계) → Attachment-Based (관계)

| Phase | Framework | Purpose |
|-------|-----------|---------|
| 기준 | **DAP** | 이 연령에 적합한 기대 수준과 활동 범위 설정. |
| 환경 | **Montessori** | 아이 높이 선반, 실물 도구, 질서, 자유 선택 영역 구성. |
| 관계 | **Attachment-Based** | 안전기지로서의 양육자. 민감 반응. 탐색 격려. |

### Pipeline 7: 형제 갈등
**Sequence:** Emotion Coaching (양쪽 감정) → PET (갈등 해결) → Positive Discipline (가족회의)

| Phase | Framework | Purpose |
|-------|-----------|---------|
| 감정 | **Emotion Coaching** | 양쪽 모두의 감정 인정. 편 들지 않기. |
| 해결 | **PET** | 무패 갈등해결 6단계. 아이들이 직접 해결책 제시. |
| 구조 | **Positive Discipline** | 정기 가족회의에서 규칙 함께 만들기. |

---

## Conflict Resolution Between Frameworks

프레임워크 간 조언이 충돌할 때 적용하는 우선순위.

### Rule 1: 감정 먼저, 행동 나중
감정을 다루기 전에 행동을 교정하려 하면 역효과. Emotion Coaching/Active Listening이 항상 첫 단계.

**Priority:** Emotion Coaching (감정 수용) > Positive Discipline (한계 설정) > Triple P (행동 수정)

### Rule 2: 관계가 훈육보다 우선
관계가 손상되면 어떤 훈육도 작동하지 않는다. 관계 유지를 해치는 접근은 재고.

**Priority:** 관계 유지 > 즉각적 행동 교정

### Rule 3: 아이의 발달 수준이 기대를 결정
프레임워크가 아무리 좋아도 아이가 발달적으로 준비되지 않은 것은 요구할 수 없다.

**Priority:** DAP (발달 적합성) > 모든 다른 프레임워크

### Rule 4: 자율성이 통제보다 지속적
외적 통제(보상/처벌)는 단기 효과, 내적 동기(자율성)는 장기 효과.

**Priority:** SDT (내적 동기) > Triple P (외적 강화) — 단, 위험 상황에서는 즉각 개입 우선

### Rule 5: "할 수 없는 것"과 "안 하는 것"을 구분
CPS의 핵심 원칙: 아이가 할 수 있는데 안 하는 것인지, 아직 기술이 부족한 것인지 먼저 판단.

**Priority:** CPS (기술 부족 가설) > Positive Discipline (의지 가설)

---

## Korean Cultural Adaptation Layer (한국 문화 맥락)

한국의 교육·양육 환경은 서구와 다른 고유한 맥락이 있다. 프레임워크 적용 시 반드시 고려.

### 교육열 (Education Fever)
- **현실:** 학원 문화, 선행학습, 입시 중심. 부모의 불안이 과도한 학습 요구로 이어짐.
- **적용:** SDT Parenting으로 "왜 공부하는가" 내적 동기 전환. Retrieval Practice로 "적게 하되 효과적으로."
- **주의:** "학원 다 끊어라"는 비현실적. 점진적 자율성 확대가 현실적.

### 체벌 금지법 (2021년 민법 915조 개정)
- **현실:** 법적으로 체벌 금지. 하지만 "손찌검 없이 어떻게 훈육하나" 혼란 존재.
- **적용:** Positive Discipline, PET, CPS는 모두 비체벌 훈육법. 이것이 대안.
- **강조:** 체벌은 단기 복종 + 장기 관계 파괴. 근거 기반 대안이 존재함을 안내.

### 학벌 문화와 성적 스트레스
- **현실:** 성적이 자존감과 직결. "공부 못하면 인생 끝" 메시지가 만연.
- **적용:** Growth Mindset으로 과정 칭찬. "머리 좋다" 대신 "노력했구나."
- **주의:** 현실적 진로 다양성 정보 병행. 마인드셋만으로 구조적 문제 해결 불가.

### 조부모 양육 / 다세대 가정
- **현실:** 조부모가 양육에 깊이 관여. 양육관 충돌 빈번.
- **적용:** 핵심 원칙(감정 수용, 일관성)에 합의. 세부 방법은 각자 스타일 존중.
- **주의:** 조부모 비난은 역효과. "함께 아이를 위해" 프레이밍.

### 맞벌이 + 돌봄 공백
- **현실:** 긴 근무시간, 제한된 양육 시간.
- **적용:** "양보다 질." 짧은 시간이라도 Emotion Coaching의 감정 연결 순간 만들기.
- **전략:** 출근 전 5분 루틴, 잠자리 대화, 주말 1:1 시간 확보.

### 높은 사교육비 스트레스
- **현실:** 가계 지출 중 교육비 비중 세계 최고 수준.
- **적용:** Retrieval Practice + Growth Mindset으로 학습 효율 극대화. PBL로 자기주도 학습 역량.
- **현실적 조언:** 학원 수 줄이기보다 학원 효과 극대화(인출 연습 병행) 전략.

---

## Emotion Level Routing

상황의 감정 온도에 따라 사용 가능한 프레임워크가 달라진다.

### Crisis (위기: 자해, 폭력, 극심한 공황)
**Available:** 즉각 안전 확보만. 프레임워크 적용 불가.
**Action:** 안전 확보 → 전문가 연결.

**전문 도움이 필요한 경우:**
- 정신건강 위기상담 전화: 1577-0199
- 아동학대 신고: 112
- 자살예방 상담: 1393
- Wee 센터 (학교폭력/부적응): 1588-7179
- 발달장애 상담: 1644-8295

### High (감정 폭발 중)
**Available:** Emotion Coaching, Active Listening (from howtotalk)
**Goal:** 감정 수용과 진정. 이 단계에서 훈육/교육은 무의미.
**Rule:** 아이가 진정될 때까지 기다린다. 최소 20분.

### Medium (약간 흥분, 짜증, 불만)
**Available:** All frameworks. 가장 생산적인 구간.
**Goal:** 상황에 맞는 프레임워크 파이프라인 실행.

### Low (평상시, 계획 단계)
**Available:** All frameworks. 특히 예방적 프레임워크 효과적.
**Goal:** Triple P(환경 설계), UbD(학습 설계), SDT(동기 체계), 가족회의(Positive Discipline) 등 선제적 적용.

---

## Sub-Commands

### `/parenting` — Full Situation Analysis & Routing

주요 명령. 상황을 설명하면 완전한 교육/양육 전략을 받는다.

**Process:**

1. **Intake:** 상황 파싱. 연령, 역할, 감정 수준, 제약 조건 추론.

2. **Diagnosis:** 16개 프레임워크 대비 상황 점수화. 상위 3개 프레임워크 식별.

3. **Age Filter:** 해당 연령에 부적합한 프레임워크 제외.

4. **Pipeline Design:** 다중 프레임워크 필요 시 순서 설계 (어떤 프레임워크가 어떤 단계를 담당).

5. **Strategy Generation:** 선택된 프레임워크별 구체 전술, 대화 스크립트, 실행 가이드 생성.

6. **Cultural Check:** 한국 문화 맥락에서의 현실성 검토 및 조정.

7. **Risk Assessment:** 잘못될 수 있는 상황과 대응 방안.

**Output format:**

```
교육/양육 전략
═══════════════════════════════

상황 분석:
  유형: [훈육 / 학습 / 정서 / 관계 / 발달 / 환경설계 / ...]
  아이 연령: [X세 / X-Y세]
  역할: [부모 / 교사 / 양육자]
  감정 온도: [낮음 / 보통 / 높음 / 위기]
  핵심 욕구: [자율성 / 유능감 / 관계 / 안전 / ...]

프레임워크 선택:
  Primary: [프레임워크명] — [선택 이유]
  Secondary: [프레임워크명] — [선택 이유]
  Support: [프레임워크명, 필요시] — [선택 이유]

실행 파이프라인:
  Phase 1 (즉시): [프레임워크] — [무엇을 할 것인가]
  Phase 2 (안정 후): [프레임워크] — [어떻게 대화할 것인가]
  Phase 3 (장기): [프레임워크] — [어떤 구조를 만들 것인가]

구체 대화 스크립트:
  상황 시작: "[정확한 말]"
  핵심 문장: ["문장 1", "문장 2", "문장 3"]
  아이가 거부하면: "[대응]"
  아이가 울면: "[대응]"
  아이가 폭발하면: "[대응]"
  마무리: "[정확한 말]"

한국 문화 고려:
  [이 상황에서 한국 맥락 특이사항]

위험 요소:
  1. [위험]: [대응]
  2. [위험]: [대응]

후속 조치:
  [대화/개입 이후 해야 할 것]
```

### `/parenting:select` — Quick Framework Selection

어떤 프레임워크가 맞는지만 빠르게 알고 싶을 때. 전체 분석 없이 추천만.

**Process:**
1. 상황을 한 문장으로 설명
2. 에이전트가 상위 3개 프레임워크 + 한 줄 근거 반환
3. 사용자가 선택하거나 자동 선택 진행

**Output format:**
```
프레임워크 선택
═══════════════

상황: [한 줄 요약]
연령: [추정 연령대]

추천:
  1. [프레임워크] — [한 줄 근거] [적합도 %]
  2. [프레임워크] — [한 줄 근거] [적합도 %]
  3. [프레임워크] — [한 줄 근거] [적합도 %]

자동 선택: [#1 프레임워크] (적합도: [X]%)
```

### `/parenting:age` — Age-Based Guide (연령별 가이드)

특정 연령대에 대한 종합 양육/교육 가이드. 상황 없이 연령만으로도 사용 가능.

**Process:**
1. 연령(대) 입력 (예: "5세", "초등 3학년", "중학생")
2. 해당 연령의 발달 특성, 적용 가능 프레임워크, 핵심 전략, 주의사항 제공

**Output format:**
```
연령별 가이드: [X세 / X-Y세]
═══════════════════════════════

발달 특성:
  인지: [이 시기 인지 발달 수준]
  정서: [이 시기 정서 발달 수준]
  사회: [이 시기 사회성 발달 수준]
  신체: [이 시기 신체 발달 수준]

적용 프레임워크 (우선순위):
  1. [프레임워크] — [이 연령에 왜 중요한지]
  2. [프레임워크] — [이 연령에 왜 중요한지]
  3. [프레임워크] — [이 연령에 왜 중요한지]

이 시기 핵심 과업:
  - [과업 1]
  - [과업 2]
  - [과업 3]

흔한 실수:
  - [실수 1] → [대안]
  - [실수 2] → [대안]

한국 맥락 참고:
  [이 연령대 한국 부모/교사가 특히 주의할 점]

추천 도서:
  - [도서 1] — [한 줄 설명]
  - [도서 2] — [한 줄 설명]
```

---

## Framework Compatibility Matrix

### High Synergy Pairs (시너지 높은 조합)
- **Emotion Coaching + Positive Discipline:** 감정 수용 후 한계 설정. 가장 기본적인 양육 콤보.
- **SDT + Growth Mindset:** 내적 동기 + 성장 신념. 학습 동기의 양대 축.
- **CPS + PET:** 둘 다 아이를 문제 해결의 파트너로. 협력적 접근의 쌍벽.
- **UbD + Formative Assessment:** 목표 역설계 + 실시간 점검. 교사의 핵심 도구.
- **Montessori + DAP:** 환경 설계 + 발달 적합성. 영유아 교육의 기둥.
- **UDL + Differentiated Instruction:** 접근성 + 개별화. 다양한 학습자를 위한 완전 체계.

### Tension Pairs (주의 필요한 조합)
- **Positive Discipline + CPS:** PD는 "잘못된 목표(소속감 추구)"로 행동을 해석; CPS는 "뒤처진 기술"로 해석. 해결: CPS의 기술 부족 가설을 먼저 검증 후 PD 적용.
- **Triple P + SDT:** Triple P의 보상 체계가 SDT의 내적 동기를 약화시킬 수 있음. 해결: 외적 보상은 최소화, 자연적 결과 활용.
- **Growth Mindset + 현실적 진로:** "노력하면 다 된다"는 맹신은 위험. 해결: 강점 영역 발견 + 다양한 성공 경로 안내 병행.

---

## Decision Flowchart

```
START
  |
  v
아이가 위험한 상황인가? (자해, 폭력, 학대)
  YES --> 즉각 안전 확보 → 전문가 연결 (1577-0199, 112)
  NO  --> Continue
  |
  v
아이가 감정 폭발 중인가?
  YES --> Emotion Coaching (감정 수용, 진정 대기)
  NO  --> Continue
  |
  v
당신의 역할은?
  |
  +--> 부모 --> 아이 연령은?
  |     |
  |     +--> 0-2세 --> Attachment-Based + Montessori
  |     +--> 3-5세 --> Emotion Coaching + Positive Discipline + DAP
  |     +--> 6-12세 --> 상황별 라우팅 (아래)
  |     +--> 13-18세 --> PET + SDT + CPS
  |
  +--> 교사 --> UbD + Formative Assessment + Differentiated Instruction
  |
  +--> 양육자 --> Attachment-Based + Emotion Coaching
  |
  v
부모 + 6-12세: 구체적 상황은?
  |
  +--> 훈육/행동 문제 --> Positive Discipline + CPS
  +--> 학습/공부 문제 --> SDT + Growth Mindset + Retrieval Practice
  +--> 정서/감정 문제 --> Emotion Coaching + Attachment-Based
  +--> 관계/사회성 문제 --> PET + Emotion Coaching
  +--> 전반적 양육 고민 --> Triple P + SDT
  +--> 잘 모르겠음 --> Fallback Sequence
```

---

## Fallback Strategy

상황이 명확히 매핑되지 않을 때 사용하는 보편적 접근.

### The Universal Parenting Sequence

1. **관찰** (Positive Discipline): 객관적 사실은 무엇인가? 판단 없이.
2. **감정** (Emotion Coaching): 아이는 지금 어떤 감정인가? 나는?
3. **욕구** (SDT): 어떤 기본 욕구가 충족되지 않고 있는가? (자율성? 유능감? 관계?)
4. **발달** (DAP): 이 아이의 발달 수준에서 합리적인 기대인가?
5. **대화** (PET): 능동적 경청으로 아이 관점 이해.
6. **협력** (CPS): 함께 해결책 찾기. Plan B.

이 순서는 대부분의 교육/양육 상황에서 작동한다. 이해 먼저, 그 다음 해결.

---

## Execution Protocol

### Step 1: Listen & Classify
사용자의 상황 설명을 주의 깊게 읽는다:
- 아이의 연령 (명시 또는 추론)
- 역할 (부모/교사/양육자)
- 상황 유형 (훈육/학습/정서/관계/발달/환경)
- 감정 온도 (위기/높음/보통/낮음)
- 반복 패턴 여부

### Step 2: Select Framework(s)
Detection Matrix + Age Filter + Role Filter를 종합:
- PRIMARY 1개 (가장 적합)
- SECONDARY 0-2개 (다면적 상황인 경우)
- 선택 이유를 각 1문장으로 설명

### Step 3: Execute
선택된 프레임워크를 Skill tool로 실행:
```
Skill("positive-discipline", args="[상황 설명]")
```
다중 프레임워크는 논리적 순서로 실행 (감정 → 행동 → 구조).

### Step 4: Synthesize
모든 프레임워크 출력을 통합:
- **통합:** 프레임워크 간 일치점과 차이점
- **우선순위:** 가장 중요한 1가지 인사이트
- **실행:** 구체적 다음 단계 (최대 3개)
- **대화 스크립트:** 실제로 할 수 있는 말 (한국어, 자연스러운 표현)

---

## References

### Core Texts (The 16 Frameworks)

**Behavioral/Discipline:**
1. Nelsen, J. (2006). *Positive Discipline*. Ballantine Books. (한국어: 긍정의 훈육)
2. Gordon, T. (2000). *Parent Effectiveness Training*. Three Rivers Press. (한국어: P.E.T. 부모역할훈련)
3. Greene, R.W. (2014). *The Explosive Child*. Harper Paperbacks. (한국어: 폭발하는 아이 다루기)
4. Gottman, J. & DeClaire, J. (1997). *Raising an Emotionally Intelligent Child*. Simon & Schuster. (한국어: 내 아이를 위한 감정코칭)

**Parent Coaching:**
5. Sanders, M.R. (2012). *Every Parent*. Penguin. (Triple P)
6. Bowlby, J. (1988). *A Secure Base*. Basic Books. / Ainsworth, M.D.S. et al. (1978). *Patterns of Attachment*.
7. Deci, E.L. & Ryan, R.M. (2017). *Self-Determination Theory*. Guilford Press.

**Learning/Cognitive:**
8. Brown, P.C., Roediger, H.L., & McDaniel, M.A. (2014). *Make It Stick*. Harvard University Press. (한국어: 어떻게 공부할 것인가)
9. Dweck, C. (2006). *Mindset*. Random House. (한국어: 마인드셋)
10. Wiggins, G. & McTighe, J. (2005). *Understanding by Design*. ASCD. 2nd ed.
11. Larmer, J. et al. (2015). *Setting the Standard for Project Based Learning*. ASCD.

**Early Childhood:**
12. Montessori, M. (1967). *The Absorbent Mind*. Holt Paperbacks. (한국어: 몬테소리 교육법)
13. NAEYC (2020). *Developmentally Appropriate Practice*. NAEYC. 4th ed.

**Special Needs & Teacher Tools:**
14. CAST (2018). *Universal Design for Learning Guidelines* version 2.2. udlguidelines.cast.org
15. Wiliam, D. (2011). *Embedded Formative Assessment*. Solution Tree Press.
16. Tomlinson, C.A. (2014). *The Differentiated Classroom*. ASCD. 2nd ed.

### Meta/Integration
- Siegel, D.J. & Bryson, T.P. (2011). *The Whole-Brain Child*. Delacorte Press. (한국어: 아이의 인성을 꽃피우는 두뇌코칭)
- Siegel, D.J. & Bryson, T.P. (2014). *No-Drama Discipline*. Bantam. (한국어: 아이 머리에서 무슨 일이 일어나고 있을까)
- Kim, U. & Park, Y.S. (2006). "Indigenous psychological analysis of academic achievement in Korea." *International Journal of Psychology*.
- 이영숙 (2014). 성품 양육. 좋은나무성품학교.
