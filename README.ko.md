# Parenting — AI를 위한 교육/육아 프레임워크

16개 교육·양육 프레임워크, 하나의 진입점.
아이 연령과 상황을 말하면 `/parenting`이 최적의 접근법을 자동 선택합니다.

## `/parenting` — 하나의 명령어로 16개 프레임워크

```
/parenting 7살인데 놀이터에서 갈 때마다 떼를 써요
```

AI가 자동으로:
1. 아이 연령대 + 역할(부모/교사) 파악
2. 최적 프레임워크 1~3개 선택
3. 단계별 파이프라인 설계 (감정 → 행동 → 구조)
4. 오늘 바로 쓸 수 있는 대화 스크립트 생성

## 명령어

| 명령어 | 설명 |
|--------|------|
| `/parenting` | 전체 분석 → 프레임워크 선택 → 대화 스크립트 포함 전략 |
| `/parenting:select` | 빠른 프레임워크 추천만 |
| `/parenting:age` | 연령별 발달 가이드 (상황 없이도 사용 가능) |

## 16개 프레임워크

### 행동/훈육

| 프레임워크 | 창시자 | 적합한 상황 |
|-----------|--------|------------|
| **긍정 훈육** | Jane Nelsen | 일상 훈육, 가족회의, 친절+단호 |
| **PET** 부모효율성훈련 | Thomas Gordon | 부모-자녀 소통, 갈등 해결 |
| **CPS** 협력적 문제해결 | Ross Greene | 만성 문제행동, 폭발적 아이, ADHD |
| **정서 코칭** | John Gottman | 감정 폭발, 정서지능 발달 |

### 양육 전략

| 프레임워크 | 창시자 | 적합한 상황 |
|-----------|--------|------------|
| **Triple P** | Matthew Sanders | 체계적 양육 계획, 예방 |
| **애착 기반 양육** | Bowlby/Ainsworth/Siegel | 영유아 애착, 분리불안 |
| **SDT 양육** 자기결정이론 | Deci & Ryan | 내적 동기, 자율성, 공부 갈등 |

### 학습/인지

| 프레임워크 | 창시자 | 적합한 상황 |
|-----------|--------|------------|
| **인출 연습** | Roediger 외 | 공부법, 시험 준비, 효율적 학습 |
| **성장 마인드셋** | Carol Dweck | 실패 두려움, "나는 못해" |
| **UbD** 역방향 설계 | Wiggins & McTighe | 교육과정 설계, 학습목표 |
| **PBL** 프로젝트 학습 | Buck Institute | 탐구학습, 자기주도 |

### 영유아 / 특수 / 교사

| 프레임워크 | 적합한 상황 |
|-----------|------------|
| **몬테소리** | 0-6세 환경 구성, 독립심 |
| **DAP** 발달적합실천 | 발달에 맞는 기대와 활동 |
| **UDL** 보편적 학습설계 | 통합교육, 학습 차이 |
| **형성평가** | 실시간 이해도 확인, 피드백 |
| **차별화 교수** | 수준별 교육, 개별화 |

## 연령별 라우팅

| 연령 | 핵심 프레임워크 | 초점 |
|------|---------------|------|
| 0-2세 | 애착, 몬테소리, DAP | 안전 애착, 환경 |
| 3-5세 | 정서코칭, 긍정훈육, DAP | 감정, 선택권, 놀이 |
| 6-9세 | 전체 사용 가능 | 학습 습관, 성장 마인드셋 |
| 10-12세 | SDT, PBL, PET | 자율성 전환 시작 |
| 13-15세 | PET, SDT, CPS | 사춘기. 경청 우선. |
| 16-18세 | SDT, CPS, PET | 거의 성인. 코칭 모드. |

## 설치

```bash
git clone https://github.com/ironyjk/parenting-frameworks.git /tmp/pf
cp -r /tmp/pf/parenting .claude/skills/
```

## 한국 문화 적응

- 교육열 — 학원 문화 속 현실적 접근
- 체벌 금지법 (2021) — 비체벌 훈육 대안
- 학벌 스트레스 — 성장 마인드셋 + 다양한 성공 경로
- 조부모 양육 — 세대 간 양육관 조율
- 맞벌이 시간 부족 — 양보다 질

## 관련 프로젝트

- **[strategy-frameworks](https://github.com/ironyjk/strategy-frameworks)** — 전략 29개 + `/think`
- **[howtotalk](https://github.com/ironyjk/howtotalk)** — 커뮤니케이션 13개 + `/howtotalk`
- **[counsel-frameworks](https://github.com/ironyjk/counsel-frameworks)** — 심리 14개 + `/counsel`
- **[toc-agents](https://github.com/ironyjk/toc-agents)** — TOC 10개
- **[triz-agents](https://github.com/ironyjk/triz-agents)** — TRIZ 9개

## 라이선스

MIT

## 만든 사람

@ironyjk × Claude Code
