# 🎬 쿼디 광고 — 프롬프트 패키지 v2 (10씬)

> 캠페인 A "들여다보다" · **약 58초** · 16:9
> 인물: **민준**(중3 남·원칙주의형) · **서아**(동생, 초등 고학년 여·전체주의형) · **코치A**(원칙주의형) · **코치B**(전체주의형)
> 기준: **Google Flow** (Veo 3.1 영상 + Nano Banana/Imagen 4 이미지 + Scenebuilder). 영상 프롬프트는 영어, 내레이션은 한국어.

---

## 0. 공통 세팅

### ① 캐릭터 Ingredient 4종 — 먼저 각각 생성·저장
```
[Minjun] Photorealistic reference of a calm, ordinary Korean boy ~15, short neat
black hair, plain heather-grey crewneck. Front + 3/4 view. Cozy home study room,
warm soft light, neutral calm expression. 16:9.
```
```
[Seoa] Photorealistic reference of a cheerful, curious Korean girl ~11–12,
shoulder-length black hair, soft light-blue cardigan. Front + 3/4 view. Same home
study setting, warm light, bright friendly expression. 16:9.
```
```
[CoachA] Warm, trustworthy Korean adult mentor ~30s, neat casual, approachable
smile, subtle coral-toned shirt. Front + 3/4 view. Cozy study room. 16:9.
```
```
[CoachB] Warm, friendly Korean adult mentor ~30s, neat casual, encouraging look,
subtle blue-toned shirt. Front + 3/4 view. Cozy study room. 16:9.
```

### ② 공통 블록 (모든 프롬프트에 append)
```
[STYLE] warm cozy Korean home study room; cream + warm ink-brown palette with
subtle coral/amber/green/blue accents; soft filmic look; shallow DOF; gentle
grain; realistic; 16:9; no on-screen text.
[CHARACTER] use the matching Ingredient(s); keep face, hair, wardrobe identical
across all clips.
```

### ③ 규칙
- 영상은 **키프레임 이미지 → Frames to Video(Veo)**. Veo Ingredients는 **컷당 레퍼런스 최대 3장** → 4인 동시 등장은 피하고 **쌍/개별로 생성 후 편집에서 합침**(특히 S8).
- **렌즈·4색·유형명·자막·5분 배지·그래프·로고는 벡터 후반 합성**(생성 X).
- 연속 컷은 Scenebuilder Extend로 인물·방 일관성 유지.

---

## 1. S1 — 막막함 (0:00–0:05)  · [Minjun]
```
IMG: Minjun seen from behind at his desk at night, shoulders slumped, head lowered,
piles of books, desk lamp, muted desaturated tones, lonely quiet mood. 16:9.
VID: Slow push-in toward Minjun from behind; shoulders slumped, a small tired sigh;
still room, dust motes in lamp light; muted palette.
```
카메라 느린 push-in · 오디오 시계 초침·한숨 · Kling 모션 낮게, 무드 조명.

## 2. S2 — 흐릿함 / 문제 (0:05–0:09) · [Minjun]
```
IMG: Over-the-shoulder POV of Minjun at an open textbook; printed letters and math
formulas; warm desk lamp. 16:9.
VID: POV onto the textbook; letters and formulas drift out of focus, blur and
scatter; faint camera unsteadiness; rising unease.
```
카메라 rack focus(선명→흐림) · 오디오 음악 정지(텐션) · Kling 포커스풀 또렷.

## 3. S3 — 5분 학습 MBTI 검사 (0:09–0:15) · [Minjun]
```
IMG: Minjun at his desk holding a smartphone, tapping a simple clean quiz interface
(a few option bars), warm hopeful light. Hands and screen in focus. 16:9.
VID: Minjun taps quickly through a short quiz on his phone, a few light taps then a
completion check; light turns warmer and hopeful.
```
카메라 손·화면 클로즈업 · 오디오 경쾌한 탭·완료음 · **후반** "학습 MBTI · 5분" 배지 + 쿼디 렌즈 합성(벡터) · Kling 탭 모션 깔끔하게.

## 4. ⭐ S4 — 민준 성향 발견 (0:15–0:21) · [Minjun]
```
IMG: Minjun now in crisp sharp focus, warm bright light, lifting his head with a
faint hopeful look; clean composition with empty space on one side for overlay. 16:9.
VID: The blurred scene snaps into crisp focus; warm light blooms; Minjun lifts his
head, faint hopeful look; gentle radiant glow.
```
카메라 focus snap + 가벼운 push · 오디오 맑은 차임·음악 상승 · **후반** 렌즈+4색 블룸, **Coral(원칙주의형) 점등** + 자막 "감각형·순차형 → 원칙주의형"(벡터) · 히어로 컷 고화질.

## 5. S5 — 민준 맞춤 공부법 / 단계적 (0:21–0:27) · [Minjun]
```
IMG: Minjun studying methodically, an open notebook with clearly numbered steps
1, 2, 3; orderly tidy desk; calm focus; subtle coral accent. 16:9.
VID: Minjun works through the steps in order, ticking step 1 then 2 then 3; calm and
methodical; close-ups of the numbered steps and his steady hand.
```
카메라 단계 따라 슬라이드·노트 클로즈업 · 오디오 단계 진행 SFX · **후반** 1›2›3 그래픽 + 자막 "구체적·사실적·단계적"(벡터) · Kling 순차 클로즈업 연결.

## 6. S6 — 동생 다른 성향 (0:27–0:33) · [Seoa]
```
IMG: Seoa (younger girl) doing the same quick test on a tablet, curious bright
expression, warm light. 16:9.
VID: Seoa taps the quiz with curiosity; the scene brightens; a fresh hopeful beat
as her result appears.
```
카메라 동생 클로즈업 → reveal · 오디오 차임(다른 톤) · **후반** 렌즈 + **Blue(전체주의형) 점등** + 자막 "직관형·총체형 → 전체주의형"(벡터).

## 7. S7 — 동생 맞춤 공부법 / 전체흐름·연결 (0:33–0:39) · [Seoa]
```
IMG: Seoa looking at a big-picture mind-map: a central idea with branches; bright,
lively; subtle blue accent. 16:9.
VID: Seoa starts from the central big-picture node; branches expand outward and
connect one by one; lively curiosity, a small confident smile.
```
카메라 중심→바깥 펼침 · 오디오 부드러운 확장음 · **후반** 마인드맵 그래픽(블루) + 자막 "전체 흐름 먼저 · 연결하며 확장"(벡터) · Kling 확장 모션.

## 8. S8 — 동일 성향 코치 매칭 (0:39–0:46) · [쌍별 생성]
> 4인 동시 X → **2개 쇼트로 따로 생성 후 편집에서 교차**.
```
VID-a [Minjun + CoachA]: Minjun and a warm coach study together at a desk, the coach
points encouragingly at the notebook, Minjun nods; warm tone, subtle coral accent.
VID-b [Seoa + CoachB]: Seoa and a friendly coach explore a big-picture diagram
together, smiling; warm tone, subtle blue accent.
```
카메라 두 쌍 교차편집 · 오디오 따뜻한 음악 · 자막 "동일 성향 코치와 함께"(벡터) · Kling 투샷 학습 장면.

## 9. ⭐ S9 — 결과 2배 / 돋보기 변화 (0:46–0:53) · [Minjun + Seoa]
```
IMG: The two siblings looking confident and proud at their desks, bright warm room,
clean space for a graphic overlay. 16:9.
VID: Both kids look up confident and proud; bright uplifting mood; sense of growth
and momentum.
```
카메라 렌즈 너머 그래프 상승, 전→후 디졸브 · 오디오 상승 차임·음악 절정 · **후반** 돋보기 + 막대그래프 "2배↑" + 자막 "학습 결과 2배 이상"(벡터) · 페이오프 컷 고화질.

## 10. S10 — 브랜드 인지 (0:53–0:58) · 생성 X
- 렌즈→로고 모핑 + 워드마크 + 태그라인 + www.quady.kr. **전부 벡터/모션그래픽.**
- 오디오 음악 레졸브 + 사운드 로고 + 마지막 내레이션.

---

## 11. ⭐ 프롬프트 전/후 (S4 핵심 컷) — 과제 필수
**❌ 전 (약한 프롬프트)**
```
A boy takes a test and finds his learning type. A magnifying glass shows 4 colors
and the QuadY logo. He is happy and his grades double. Make it inspiring.
```
문제: 인물 미고정 / 한 컷에 비트 과다(검사+유형+로고+성적) / 카메라·조명·스타일 없음 / 로고·4색·텍스트·그래프를 모델에 그리게 함(뭉개짐) / "inspiring"뿐.

**✅ 후 (개선)** = 위 S4 IMG+VID + 공통 블록
개선: Ingredient(Minjun)로 인물 고정 / 한 컷=한 동작(흐림→선명+고개 듦) / 카메라·조명·STYLE·16:9 명시 / 로고·4색·자막은 후반 벡터 합성(여백 확보) / 구체 묘사로 결과 예측.

## 12. 내레이션 (ElevenLabs · 한국어 여성 · 따뜻·차분)
- S1 "같은 시간, 같은 책상 앞에 앉아도…"
- S2 "우리 아이는, 왜 안 될까?"
- S3 "학습 MBTI로, 5분이면 우리 아이 성향을 찾습니다."
- S4 "민준이는 감각형·순차형, 원칙주의형이에요."
- S5 "구체적인 내용을 단계적으로 — 넘나드는 방식은 금물."
- S6 "동생은 정반대 — 직관형·총체형, 전체주의형이에요."
- S7 "큰 그림을 먼저 잡고, 연결하며 확장하죠."
- S8 "그리고 같은 성향의 코치를 만납니다."
- S9 "맞는 방법으로, 결과는 두 배 이상."
- S10 "성향마다 다른 공부법, 쿼디가 찾아줍니다."

## 13. Suno BGM (약 58초)
```
Warm, hopeful, gentle instrumental — soft piano, light acoustic guitar, subtle
strings. Sparse and quiet at the start; a bright discovery lift around 0:09–0:21;
steady warm middle for the learning scenes; an uplifting swell near 0:46 for the
"2x results" payoff; resolves warmly at the end. No vocals. ~58 seconds. Family /
education brand ad.
```

## 14. 제작 순서 (Flow)
1. **Ingredient 4종 생성·저장**(Minjun·Seoa·CoachA·CoachB)
2. 씬별 키프레임 → Frames to Video(Veo). **S8은 쌍별로 따로 생성**.
3. Scenebuilder로 10컷 타임라인 조립(연속 컷은 Extend)
4. 네이티브 오디오 끄고 영상만 → CapCut/DaVinci에서 **Suno BGM + ElevenLabs 내레이션 10줄 + SFX** 믹스
5. **벡터 합성:** 렌즈(S3·S4·S6·S9), 4색·유형명(S4·S6), 단계 1›2›3(S5), 마인드맵(S7), 그래프 2배(S9), 로고(S10), 한글 자막
6. 4K 업스케일 → **광고 MP4(약 58초)**

> 크레딧: 인물·컷이 늘었으니 초안은 Lite/Fast로 확정 → 히어로(S4·S9·S10)만 고화질 최종.
