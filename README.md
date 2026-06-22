# AI Native 미션 3 — 노코드 자동화 (Make · n8n)

> 동일한 워크플로우를 **두 개의 자동화 도구로 구현·비교**하고, **자유주제 자동화 파이프라인**을 설계·구현한 결과물입니다.

---

## 📋 개요

노코드 자동화 도구의 Trigger·Action·조건 분기 작동 원리를 이해하고, 도구별 특성을 근거 있게 비교하며, 실제 동작하는 자동화 워크플로우를 구축하는 것을 목표로 합니다.

- **Project 1** — 동일 워크플로우를 **Make**와 **n8n** 두 도구로 구현하고 비교 분석
- **Project 2** — **n8n**으로 자유주제 자동화: 매일 자동 실행되는 상담 신청 요약 브리핑 (AI 요약 포함)

---

## 🗂 저장소 구성

```
.
├── README.md                       # 현재 문서
├── docs/
│   ├── project1-make-vs-n8n.md     # Project 1 비교 분석 보고서
│   └── project2-design.md          # Project 2 설계 문서
└── images/                         # 구현·실행 화면 캡처
```

---

## 🛠 사용 도구

| 구분 | 도구 |
|---|---|
| 자동화 | Make (클라우드), n8n (자가호스팅) |
| 데이터 | Google Forms, Google Sheets |
| 알림 | Slack |
| AI | Google Gemini (요약 생성) |

---

## 🔹 Project 1 — 자동화 도구 비교 구현 (Make vs n8n)

**워크플로우**: 구글 폼 상담 신청 → 응답 시트 새 행 → **학년 기준 분기(중등/고등)** → 상담관리 시트 기록 + Slack 알림

동일한 구조를 Make와 n8n으로 각각 구현하고, 설정 난이도·UI·분기 방식·무료 범위 등 **8개 항목**으로 비교했습니다.

📄 **상세 보고서: [docs/project1-make-vs-n8n.md](docs/project1-make-vs-n8n.md)**

![Make 전체 시나리오](images/p1-make-scenario.png)
*Make — 전체 시나리오 (트리거 → Router → 시트/Slack)*

![n8n 전체 워크플로우](images/p1-n8n-workflow.png)
*n8n — 전체 워크플로우 (Trigger → Switch → 시트/Slack)*

![실행 결과](images/p1-result.png)
*실행 결과 — 상담관리 시트 기록 + Slack 알림*

**핵심 비교 요약**: 진입장벽·시작 속도는 **Make**(관리형 OAuth)가 우세, 무료·무제한 실행과 데이터 자체 통제는 **n8n**(자가호스팅)이 우세.

---

## 🔸 Project 2 — 자유주제: 일일 상담 신청 요약 브리핑 (n8n)

**반복 업무**: 매일 아침 누적된 학습상담 신청 현황을 요약해 Slack에 공유하는 일을 자동화.

**흐름**
```
Schedule(매일 09:00, 자동)
  → Google Sheets 상담관리 읽기
  → Code 집계(건수/중등/고등/목록)
  → Gemini 자연어 요약  ← AI 보너스
  → IF: 건수 > 0 ?
       ├─ true  → Slack 브리핑 + 브리핑로그 기록
       └─ false → Slack "오늘 신규 없음"
```

📄 **상세 설계 문서: [docs/project2-design.md](docs/project2-design.md)**

![n8n 일일 브리핑 워크플로우](images/p2-n8n-workflow.png)
*n8n — 일일 브리핑 워크플로우*

![브리핑 결과](images/p2-result.png)
*실행 결과 — Slack 브리핑 + 브리핑로그 시트(AI 요약)*

---

## ✅ 미션 요건 충족 체크

| 요건 | Project 1 | Project 2 |
|---|---|---|
| 실제 동작하는 워크플로우 | ✓ | ✓ |
| 트리거 1개 이상 | ✓ | ✓ (Schedule) |
| 액션 2개 이상 | ✓ (시트+Slack) | ✓ (Slack+시트) |
| 조건 분기 1개 이상 | ✓ (학년) | ✓ (건수) |
| 각 분기 경로 1회 이상 실행 | ✓ | ✓ |
| 2개 이상 도구 사용 | ✓ (Make·n8n) | — |
| 자동 실행 | — | ✓ (Schedule + Active) |
| 보너스 — AI 액션 | — | ✓ (Gemini 요약) |

---

## 🔐 보안

- 자격증명(Google OAuth Client Secret, Gemini API 키, Slack 봇 토큰)은 비공개로 관리하고 캡처 시 마스킹했습니다.
- 테스트에는 실제 개인정보 대신 더미 데이터를 사용했습니다.

---

## 🚀 향후 확장

검사 완료 시 학부모에게 **카카오 알림톡**으로 결과 페이지를 자동 발송하고, 일정 시간 뒤 상담 안내 메시지로 자연스럽게 상담 전환하는 **QuadY 상담 퍼널**로 확장 예정.
