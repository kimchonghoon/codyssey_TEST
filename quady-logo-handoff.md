# 쿼디 로고 빌드 패키지 — Claude Design 핸드오프

> 채팅에서 SVG를 손으로 짜는 대신, 이 파일을 **Claude Design**에 넣고 캔버스에서 시각적으로 다듬기 위한 자료.
> 구성: ① 로고 스펙 ② 바로 쓰는 SVG 3종 ③ Claude Design 붙여넣기 프롬프트 ④ 환경 세팅 순서

---

## ① 로고 스펙 (Symbol Spec)

**컨셉:** 돋보기 모양의 Q. 렌즈로 학생의 성향을 *들여다본다*. 렌즈 안은 4분할 = 4가지 학습유형(Quad).

**기하 구조** (viewBox 0 0 100 100 기준)
| 요소 | 값 |
|---|---|
| 렌즈 중심 | (42, 42) |
| 림(테두리) 반지름 | 27, 획 두께 8 |
| 유리(클립) 반지름 | 21.5 |
| 4분할 십자 간격 | 3 (중심 42 기준 ±1.5) |
| 반사광 | 좌상단 호, 흰색, 두께 3.4, 투명도 0.92 |
| 손잡이(=Q 꼬리) | (61.5,61.5)→(83,83), 두께 10.5, 둥근 끝, 45° |

**임시 컬러** *(BI 단계에서 확정)*
| 이름 | HEX | 용도 |
|---|---|---|
| Coral | `#F4795B` | 좌상 / 메인 |
| Amber | `#F2B03D` | 우상 |
| Green | `#5BB98C` | 좌하 |
| Blue | `#5B9BD9` | 우하 |
| Ink | `#3E3733` | 림·손잡이·텍스트 |
| Cream | `#FBF7F2` | 배경 |

**규칙**
- 작은 크기(파비콘 등)에서는 4색이 안 보이므로 **단색 버전** 사용
- 여백(clear space): 심볼 사방으로 림 반지름(=27)만큼 비우기
- 워드마크: 한글 **쿼디** + 라틴 **QuadY** 병기, 태그라인 「자기주도 학습의 시작과 끝」

---

## ② 바로 쓰는 SVG (텍스트 파일로 저장하면 그대로 .svg 파일)

### 기본 (풀컬러)
```xml
<svg width="512" height="512" viewBox="0 0 100 100" xmlns="http://www.w3.org/2000/svg">
  <defs><clipPath id="lens"><circle cx="42" cy="42" r="21.5"/></clipPath></defs>
  <g clip-path="url(#lens)">
    <rect x="14"   y="14"   width="26.5" height="26.5" fill="#F4795B"/>
    <rect x="43.5" y="14"   width="26.5" height="26.5" fill="#F2B03D"/>
    <rect x="14"   y="43.5" width="26.5" height="26.5" fill="#5BB98C"/>
    <rect x="43.5" y="43.5" width="26.5" height="26.5" fill="#5B9BD9"/>
  </g>
  <path d="M29 45 A15 15 0 0 1 39 29.5" fill="none" stroke="#FFFFFF" stroke-width="3.4" stroke-linecap="round" opacity="0.92"/>
  <circle cx="42" cy="42" r="27" fill="none" stroke="#3E3733" stroke-width="8"/>
  <line x1="61.5" y1="61.5" x2="83" y2="83" stroke="#3E3733" stroke-width="10.5" stroke-linecap="round"/>
</svg>
```

### 단색 (작은 크기·단일색용)
```xml
<svg width="512" height="512" viewBox="0 0 100 100" xmlns="http://www.w3.org/2000/svg">
  <circle cx="42" cy="42" r="27" fill="none" stroke="#F4795B" stroke-width="8"/>
  <line x1="42" y1="22.5" x2="42" y2="61.5" stroke="#F4795B" stroke-width="3"/>
  <line x1="22.5" y1="42" x2="61.5" y2="42" stroke="#F4795B" stroke-width="3"/>
  <line x1="61.5" y1="61.5" x2="83" y2="83" stroke="#F4795B" stroke-width="10.5" stroke-linecap="round"/>
</svg>
```

### 반전 (어두운 배경용)
```xml
<svg width="512" height="512" viewBox="0 0 100 100" xmlns="http://www.w3.org/2000/svg">
  <rect width="100" height="100" fill="#3E3733"/>
  <defs><clipPath id="lensR"><circle cx="42" cy="42" r="21.5"/></clipPath></defs>
  <g clip-path="url(#lensR)">
    <rect x="14" y="14" width="26.5" height="26.5" fill="#F4795B"/>
    <rect x="43.5" y="14" width="26.5" height="26.5" fill="#F2B03D"/>
    <rect x="14" y="43.5" width="26.5" height="26.5" fill="#5BB98C"/>
    <rect x="43.5" y="43.5" width="26.5" height="26.5" fill="#5B9BD9"/>
  </g>
  <circle cx="42" cy="42" r="27" fill="none" stroke="#FFFFFF" stroke-width="8"/>
  <line x1="61.5" y1="61.5" x2="83" y2="83" stroke="#FFFFFF" stroke-width="10.5" stroke-linecap="round"/>
</svg>
```
> 💾 메모장에 붙여넣고 `quady-logo.svg`로 저장하면 바로 쓰는 벡터 파일입니다. (Claude Design은 SVG로 내보내기가 안 되니, 이 SVG가 사실상 마스터 벡터예요.)

---

## ③ Claude Design 붙여넣기 프롬프트 (복사해서 사용)

> Claude Design은 *목표·레이아웃·내용·대상* 4가지를 명확히 적을수록 잘 만듭니다. 아래를 그대로 붙여넣으세요.

```
[대상] 학부모(1차), 학생, 학습코치를 위한 에듀테크 브랜드 '쿼디(QuadY)'의 로고.
[목표] 첨부한 SVG와 스펙을 캔버스에 정밀하게 재현하고, 변형 세트와 아트보드를 만든다.

[심볼 컨셉]
- 돋보기 모양의 알파벳 Q. 렌즈로 학생의 성향을 '들여다본다'는 의미.
- 렌즈 안은 4분할(빨강·노랑·초록·파랑) = 4가지 학습유형.
- 렌즈 좌상단에 흰색 반사광 곡선(유리 신호).
- 오른쪽 아래 45도로 굵고 둥근 손잡이 = Q의 꼬리.
- 따뜻하고 친근한 느낌. 둥근 형태.

[정확한 값]
- 림 반지름 27 / 획 8, 유리 반지름 21.5, 4분할 십자 간격 3
- 손잡이 두께 10.5, 둥근 끝, 45도
- 색: Coral #F4795B, Amber #F2B03D, Green #5BB98C, Blue #5B9BD9, Ink #3E3733, 배경 #FBF7F2

[만들 아트보드]
1. 심볼 단독 (512×512)
2. 가로 조합: 심볼 + '쿼디 QuadY' + 태그라인 '자기주도 학습의 시작과 끝'
3. 세로(스택) 조합
4. 단색 버전 / 반전(어두운 배경) 버전
5. 파비콘 (64×64) — 단색 단순화
6. 앱 아이콘 (1024×1024)

[타이포]
- 한글: 나눔스퀘어라운드(또는 Pretendard) 굵게
- 라틴: Quicksand 또는 Poppins (둥근 지오메트릭)

먼저 1번 심볼부터 캔버스에 그린 뒤, 내 피드백을 받아 반사광 위치·손잡이 각도·획 두께를 조절 노브로 다듬자.
```

---

## ④ Claude Design 환경 세팅 순서

1. **진입** — Claude 좌측 메뉴에서 **Design** 선택 (Pro/Max/Team/Enterprise 필요, 리서치 프리뷰).
2. **새 프로젝트 + 컨텍스트 업로드**
   - 이 파일(스펙) + 옛 특허 로고 PNG/캡처 + 앞서 만든 *브랜드 파운데이션 v3* 문서를 업로드.
   - (선택) GitHub `kimchonghoon` 저장소 연결 → 디자인 시스템 추출.
3. **디자인 시스템 등록** ← 가장 중요
   - 위 6색 + 한글/라틴 폰트를 **브랜드 컬러·타이포**로 저장.
   - 이렇게 하면 이후 홈페이지·비품·영상 프레임이 **자동으로 같은 브랜드**로 생성됨.
4. **로고 생성** — ③ 프롬프트 붙여넣기 → 캔버스 확인.
5. **정밀 조정**
   - 큰 방향 변경 = 채팅 / 특정 요소 = 인라인 코멘트 / 색·간격·획 = 조절 노브.
6. **내보내기 / 핸드오프**
   - 이미지·문서: **PNG / PDF / PPTX / HTML / Canva**로 내보내기.
   - 추가 편집은 **Canva 핸드오프**(편집 가능 상태로 열림), 구현은 **Claude Code 핸드오프 번들**.
   - ⚠️ **벡터(SVG) 마스터는 위 ②번 코드**를 그대로 보관 (Claude Design은 SVG 내보내기 미지원).

---

## ⑤ 다음 단계 연결
로고가 캔버스에서 확정되면 → 같은 프로젝트에서 **STEP 3(컬러·타이포 BI 확정) → STEP 4(홈페이지·비품) → STEP 5(영상 프레임)**을 이어서 만들면 전부 한 브랜드로 통일됩니다.
