# 경험 인터뷰 (experience-interview)

"쓸 만한 경험이 없다"는 사람에게서 실제 사건을 끌어내, **면접에서 재현 가능한 형태**로 기록하는 Claude Code 스킬.

자소서를 대신 써주는 스킬이 아니다. **질문을 던지는 쪽**이다.

## 무엇이 다른가

대부분의 이력서·자소서 도구는 이미 정리된 경험을 입력으로 받는다. 그런데 정리하지 못해서 막히는 경우가 대부분이다. 이 스킬은 그 앞 단계를 맡는다.

질문 문구와 금지 규칙을 면담·기억 연구에서 가져왔고, **모든 질문에 출처를 붙였다.** 근거의 검증 상태(원문 대조 / 2차 자료 / 확인 실패)도 함께 표시한다.

### 전제를 하나 뒤집었다

경험을 캐묻는 도구는 보통 "과장을 걸러내는 것"을 목표로 한다. 근거상 그건 잘 안 된다.

- 면접관의 진위 판별 정확도는 평균 **54%** — 동전 던지기 수준
- 지원자의 과장 전술 탐지율 **12~19%**, 면접 경력 9.6년이어도 나아지지 않음
- 그리고 **후속 질문이 오히려 과장을 늘렸다** (Levashina & Campion 2007)

그래서 이 스킬의 목적은 진위 판별이 아니라 **검증 가능한 형태로 문장을 다시 쓰게 만드는 것**이다. 오염된 진술은 서류를 통과하고 면접에서 터진다. 유도 질문을 금지하는 이유는 윤리가 아니라 손실 회피다.

## 어떻게 묻는가

| 단계 | 하는 일 | 대표 질문 |
|---|---|---|
| 0 | 평가 프레임 해제 + 사전 규칙 | "정답도 오답도 없습니다" / "모르면 모른다고 해 주세요. 추측하지 마세요" |
| 1 | 사건 찾기 (예시를 주지 않는다) | "지금까지를 한 권의 책이라 생각하고 각 장에 제목을 붙인다면?" |
| 2 | 맥락 복원 | "그 공간을 머릿속에 그려 보세요 … 누가 있었는지 …(멈춤) 무엇이 들렸는지" |
| 3 | "우리"에서 "나" 꺼내기 | "그 순간 **구체적으로 무엇을 말했거나 했나요**?" |
| 4 | 수치 발굴 | "그게 몇 명인지 **어떻게 기억해내셨어요**?" → "얼마나 확신하세요?" |
| 5 | 분야별 심화 | AI·인프라·백엔드·데이터·프론트·로봇·마케팅·기획·대외활동 |
| 6 | 의미 부여와 확인 | "이 장면이 당신에 대해 무엇을 말해 주나요?" / "제가 빠뜨린 게 있나요?" |

## 하지 않는 것 (근거 있는 금지 규칙 12가지)

| 금지 | 검증된 효과 |
|---|---|
| 말하지 않은 것을 전제로 깔기 | 없던 물건을 봤다는 응답 **53% vs 35%** |
| 숫자 선택지 제시 ("3명? 5명? 10명?") | 평균 응답 **3.3 → 5.2**로 이동 (성인, 본인의 과거 경험 대상) |
| 강도 부사 ("자주 하셨죠?") | 주 **2.2회 vs 0.7회** |
| 칭찬·감탄 ("오 그거 좋네요!") | 허위 주장 **35% vs 12%**, 강화를 끊어도 유지 |
| 예시 먼저 보여주기 | 보고 내용의 **53%**가 그 예시 범주로 쏠림 |
| 상상·가정 ("만약 팀장이었다면?") | 상상 팽창 — 위험은 있는데 회상 이득은 없음 |

전체 목록과 근거는 `references/금지규칙.md`.

## 결과물

`templates/경험블록.md` 형식. 에피소드마다 **상황 / 문제 / 내 판단 / 행동 / 결과 / 그때 생각·느낌**이 채워지고, 수치에는 **분모·기간·측정 환경·정의 4종 세트**와 출처 플래그(`[측정]` `[추정]` `[내부]`)가 붙는다.

기록에 항상 남기는 세 가지: **역할 경계(내가 하지 않은 것)**, **⚠️ 확인 필요**, **면접 공격 포인트**.

그리고 인터뷰 중 "어… 생각해 보니 그런 것 같네요"로 나온 문장은 `🔁 재확인 필요`로 따로 표시한다. 기존 기억의 인출은 놀라움이 아니라 **재인의 느낌**을 동반하기 때문이다(Grunert & Grunert 1995).

## 의존성 없음

다른 스킬, MCP 서버, 파이썬 스크립트, 네트워크 호출에 **의존하지 않는다.** 마크다운 파일 7개가 전부다. 클론해서 스킬 폴더에 넣으면 바로 동작하고, 오프라인에서도 동작한다.

결과물을 자소서·이력서 스킬로 넘길 수는 있지만 선택 사항이며, 그쪽 스킬이 없어도 기록은 그대로 남는다.

## 예시

["쓸 만한 경험이 없어요"에서 시작해 수치가 붙은 경험 블록이 나오기까지](examples/샘플세션.md) — 가상 인물로 만든 전체 세션과 결과물, 그리고 각 순간에 쓴 기법의 출처.

## 설치

**Claude Code — 모든 프로젝트에서 사용**
```bash
git clone https://github.com/OWNER/REPO.git ~/.claude/skills/experience-interview
```

**특정 프로젝트에서만 사용**
```bash
git clone https://github.com/OWNER/REPO.git <프로젝트>/.claude/skills/experience-interview
```

**Codex 등 다른 에이전트**
스킬 폴더를 지원하면 `~/.codex/skills/` 아래에 같은 방식으로 두고, 지원하지 않으면 대화에서 `SKILL.md` 경로를 직접 가리킨다.

설치 후 Claude Code를 다시 시작하면 목록에 나타난다.

## 쓰는 법

```
경험 정리해줘
자소서에 쓸 게 없는 것 같아
이번 프로젝트 끝났어, 기록해줘
이거 이력서에 쓸 만한가?
```

`/experience-interview`로 직접 부를 수도 있다.

## 파일

```
experience-interview/
├── SKILL.md                          진행 흐름과 원칙
├── references/
│   ├── 질문문구.md                    단계별 질문 34개 + 보조 문구 + 실행 비율 규칙 (출처 표시)
│   ├── 금지규칙.md                    하면 안 되는 12가지와 근거 수치
│   ├── 기법과근거.md                  기법별 요약·한계, 출처 목록, 인용 금지 항목
│   └── 분야별_질문과표현.md            분야 9개: 심화질문, 과장↔안전 대체표, 반박 질문
└── templates/경험블록.md              출력 형식
```

## 근거로 삼은 것

인지 면담(Fisher & Geiselman) · 결정적 사건 기법(Flanagan 1954) · 행동사건면접(McClelland, Boyatzis) · 생애사 면담(McAdams) · 래더링(Reynolds & Gutman) · 레퍼토리 그리드(Kelly) · 인지적 사전검사(Willis) · 동기면담(MITI, SAMHSA TIP 35) · NICHD 프로토콜 · 영국 법무부 ABE 지침 · 유도 질문과 기억 왜곡 연구(Loftus 등) · 한국산업인력공단 능력중심채용 가이드북 · SFIA·NCS 역량 프레임워크

출처와 접근 경로는 `references/기법과근거.md`에 정리되어 있고, **확인하지 못한 수치는 "인용 금지"로 따로 표시했다.**

## 한계

- 근거의 다수가 **법정 면담·아동 대상** 연구다. 성인·채용 맥락에서는 효과가 작아질 수 있다. 다만 숫자 앵커링과 강도 부사 실험(Loftus 1975)은 **성인이 본인의 과거 경험을 답한** 설계라 그대로 적용된다
- **인지 면담을 채용·HR에 적용한 연구를 찾지 못했다**
- 근거가 전부 영어권이다. 한국어의 어미·조사가 만드는 전제("-았잖아요", "그 ○○")가 같게 작동하는지는 검증되지 않았다
- 이 스킬은 기억을 정확하게 만들지 못한다. **다만 기억을 오염시키지 않으려 한다**

## 라이선스

MIT — 양재우 (Jaewoo Yang)

인용한 연구·지침의 저작권은 각 저작자·발행처에 있다. 이 저장소는 그 내용을 요약하고 출처를 표시했을 뿐이며, 원문의 재배포가 아니다.

---

### In short (English)

A Claude Code skill that **interviews you** to surface real experiences for résumés and cover letters, instead of writing them for you. Question wording and prohibition rules are drawn from interview and memory research — cognitive interviewing, the critical incident technique, behavioral event interviews, life-story interviews, laddering, repertory grids, cognitive pretesting, motivational interviewing, and the leading-question literature — with sources and verification status attached to every claim.

Its premise: probing does not detect exaggeration (interviewers score ~54% at detecting deception, and probing has been shown to *increase* faking). So the goal is not lie detection but **rewriting statements into a form that can be verified in an interview**. Korean-language prompts; the underlying method is language-independent.
